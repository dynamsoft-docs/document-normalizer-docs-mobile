---
layout: default-layout
title: Detect and Normalize Document - MAUI User Guide
description: This page introduce how to detect and normalize document with Dynamsoft Capture Vision MAUI SDK.
keywords: user guide, maui
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# MAUI User Guide for Document Scanner Integration

## Table of Contents

- [MAUI User Guide for Document Scanner Integration](#maui-user-guide-for-document-scanner-integration)
	- [Table of Contents](#table-of-contents)
	- [System Requirements](#system-requirements)
		- [.Net](#net)
		- [Android](#android)
		- [iOS](#ios)
	- [Installation](#installation)
		- [Visual Studio for Mac](#visual-studio-for-mac)
		- [Visual Studio for Windows](#visual-studio-for-windows)
	- [Build Your Document Scanner App](#build-your-document-scanner-app)
		- [Set up Development Environment](#set-up-development-environment)
		- [Initialize the Project](#initialize-the-project)
			- [Visual Studio](#visual-studio)
			- [Visual Studio for Mac](#visual-studio-for-mac-1)
		- [Include the Library](#include-the-library)
		- [Initialize MauiProgram](#initialize-mauiprogram)
		- [License Activation](#license-activation)
		- [Initialize the Capture Vision SDK](#initialize-the-capture-vision-sdk)
		- [Add the CameraView control in the Main Page](#add-the-cameraview-control-in-the-main-page)
		- [Open the Camera and Start Document Detection and Normalization](#open-the-camera-and-start-document-detection-and-normalization)
		- [Obtaining Normalized Document Image](#obtaining-normalized-document-image)
		- [Add the Image control in the Image Page](#add-the-image-control-in-the-image-page)
		- [Display the Normalized Document Image](#display-the-normalized-document-image)
		- [Run the Project](#run-the-project)
	- [Licensing](#licensing)

## System Requirements

### .Net

- .NET 7.0 and above.

### Android

- Supported OS: **Android 5.0** (API Level 21) or higher.
- Supported ABI: **armeabi-v7a**, **arm64-v8a**, **x86** and **x86_64**.
- Development Environment: Visual Studio 2022 recommended.
- JDK: 1.8+

### iOS

- Supported OS: **iOS 11.0** or higher.
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Visual Studio 2022 for Mac and Xcode 14.3+ recommended.

## Installation

### Visual Studio for Mac

In the **NuGet Package Manager>Manage Packages for Solution** of your project, search for **Dynamsoft.CaptureVisionBundle.Maui**. Select it and click **install**.

### Visual Studio for Windows

You have to Add the library via the project file and do some additional steps to complete the installation.

1. Add the library in the project file:

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
        ...
        <ItemGroup>
            ...
            <PackageReference Include="Dynamsoft.CaptureVisionBundle.Maui" Version="2.4.2000" />
        </ItemGroup>
    </Project>
    ```

2. Open the **Package Manager Console** and run the following commands:

    ```bash
    dotnet build
    ```

> Note:
>
> - Windows system have a limitation of 260 characters in the path. If you don't use console to install the package, you will receive error "Could not find a part of the path 'C:\Users\admin\.nuget\packages\dynamsoft.imageprocessing.ios\2.2.300\lib\net7.0-ios16.1\Dynamsoft.ImageProcessing.iOS.resources\DynamsoftImageProcessing.xcframework\ios-arm64\dSYMs\DynamsoftImageProcessing.framework.dSYM\Contents\Resources\DWARF\DynamsoftImageProcessing'"
> - The library only support Android & iOS platform. Be sure that you remove the other platforms like Windows, maccatalyst, etc.

## Build Your Document Scanner App

Now you will learn how to create a SimpleDocumentScanner using Dynamsoft Capture Vision MAUI SDK.

>Note:
>
> - You can get the similar source code of the SimpleDocumentScanner app from the following link
>   - [C#](https://github.com/Dynamsoft/capture-vision-maui-samples/tree/main/DocumentScanner/AutoNormalize){:target="_blank"}.

### Set up Development Environment

If you are a beginner with MAUI, please follow the guide on the <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation" target="_blank">.Net MAUI official website</a> to set up the development environment.

### Initialize the Project

#### Visual Studio

1. Open the Visual Studio and select **Create a new project**.
2. Select **.Net MAUI App** and click **Next**.
3. Name the project **SimpleDocumentScanner**. Select a location for the project and click **Next**.
4. Select **.Net 7.0** and click **Create**.

#### Visual Studio for Mac

1. Open Visual Studio and select **New**.
2. Select **Multiplatform > App > .Net MAUI App > C#** and click **Continue**.
3. Select **.Net 7.0** and click **Continue**.
4. Name the project **SimpleDocumentScanner** and select a location, click **Create**.

### Include the Library

Add NuGet package **Dynamsoft.CaptureVisionBundle.Maui** to your project. You can view the [installation section](#installation) on how to add the library.

### Initialize MauiProgram

In **MauiProgram.cs**, add a custom handler for the `CameraView` control. Specifically, it maps the `CameraView` type to the `CameraViewHandler` type.

```c#
namespace SimpleDocumentScanner;
using Microsoft.Extensions.Logging;
using Dynamsoft.CameraEnhancer.Maui;
using Dynamsoft.CameraEnhancer.Maui.Handlers;

public static class MauiProgram
{
    public static MauiApp CreateMauiApp()
    {
        var builder = MauiApp.CreateBuilder();
        builder
            .UseMauiApp<App>()
            .ConfigureFonts(fonts =>
            {
                fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
                fonts.AddFont("OpenSans-Semibold.ttf", "OpenSansSemibold");
            })
            .ConfigureMauiHandlers(handlers =>
            {
                handlers.AddHandler(typeof(CameraView), typeof(CameraViewHandler));
            });

#if DEBUG
        builder.Logging.AddDebug();
#endif

        return builder.Build();
    }
}
```

### License Activation

The Dynamsoft Capture Vision SDK needs a valid license to work. Please refer to the [Licensing](#licensing) section for more info on how to obtain a license.

Go to **MainPage.xaml.cs**. Add the following code to activate the license:

```c#
namespace SimpleDocumentScanner;
using Dynamsoft.License.Maui;
using System.Diagnostics;

public partial class MainPage : ContentPage, ILicenseVerificationListener
{
    public MainPage()
    {
        InitializeComponent();
        LicenseManager.InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", this);
    }
    public void OnLicenseVerified(bool isSuccess, string message)
    {
        if (!isSuccess)
        {
            Debug.WriteLine(message);
        }
    }
}
```

### Initialize the Capture Vision SDK

In the **MainPage.xaml.cs**, add the following code to initialize the Capture Vision SDK:

```c#
......
using Dynamsoft.CaptureVisionRouter.Maui;
using Dynamsoft.CameraEnhancer.Maui;
using Dynamsoft.Core.Maui;
using Dynamsoft.Utility.Maui;

public partial class MainPage : ContentPage, ILicenseVerificationListener, ICapturedResultReceiver
{
    CameraEnhancer enhancer;
    CaptureVisionRouter router;

    public MainPage()
    {
        ......

        // Create an instance of CameraEnhancer
        enhancer = new CameraEnhancer();
        // Create an instance of CaptureVisionRouter
        router = new CaptureVisionRouter();
        // Bind the router with the created CameraEnhancer
        router.SetInput(enhancer);
        // Add the result receiver to receive the document normalized image
        router.AddResultReceiver(this);
        // Add the result filter to verify the result across multiple frames
        var filter = new MultiFrameResultCrossFilter();
        filter.EnableResultCrossVerification(EnumCapturedResultItemType.CRIT_NORMALIZED_IMAGE, true);
        router.AddResultFilter(filter);
    }
}
```

### Add the CameraView control in the Main Page

In the **MainPage.xaml**, add a `CameraView` control:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:controls="clr-namespace:Dynamsoft.CameraEnhancer.Maui;assembly=Dynamsoft.CaptureVisionRouter.Maui"
             x:Class="SimpleDocumentScanner.MainPage"
             Title="MainPage">
    <AbsoluteLayout>
        <controls:CameraView x:Name="cameraView"
                             AbsoluteLayout.LayoutBounds="0,0,1,1"
                             AbsoluteLayout.LayoutFlags="All"/>
    </AbsoluteLayout>
</ContentPage>
```

### Open the Camera and Start Document Detection and Normalization

In this section, we are going to add code to start document detection and normalization in the **MainPage.xaml.cs**.

```c#
......

public partial class MainPage : ContentPage, ILicenseVerificationListener, ICapturedResultReceiver, ICompletionListener
{
    ......
   protected override void OnHandlerChanged()
    {
        base.OnHandlerChanged();

        if (this.Handler != null)
        {
            enhancer.SetCameraView(cameraView);
        }
    }

    protected override async void OnAppearing()
    {
        base.OnAppearing();
        // Request camera permission
        await Permissions.RequestAsync<Permissions.Camera>();
        // Open camera
        enhancer?.Open();
        // Start document detection and normalization
        router?.StartCapturing(EnumPresetTemplate.PT_DETECT_AND_NORMALIZE_DOCUMENT, this);
    }

    protected override void OnDisappearing()
    {
        base.OnDisappearing();
        // Close camera
        enhancer?.Close();
        // Stop document detection and normalization
        router?.StopCapturing();
    }

    // It is called when StartCapturing is successful
    public void OnSuccess()
    {
        Debug.WriteLine("Success");
    }

    // It is called when StartCapturing is failed
    public void OnFailure(int errorCode, string errorMessage)
    {
        Debug.WriteLine(errorMessage);
    }
}
```

Open the **Info.plist** file under the **Platforms/iOS/** folder (Open with XML Text Editor). Add the following lines to request camera permission on iOS platform:

```xml
<key>NSCameraUsageDescription</key>
<string>The sample needs to access your camera.</string>
```

### Obtaining Normalized Document Image

In **MainPage.xaml.cs**, implement `ICapturedResultReceiver` to receive normalized images result in  `OnNormalizedImagesReceived` callback function.

```c#
......
using Dynamsoft.DocumentNormalizer.Maui;

public partial class MainPage : ContentPage, ILicenseVerificationListener, ICapturedResultReceiver, ICompletionListener
{
    ......
    public void OnNormalizedImagesReceived(NormalizedImagesResult result)
    {
        if (result?.Items?.Count > 0)
        {
            router?.StopCapturing();
            enhancer?.ClearBuffer();
            var data = result.Items[0].ImageData;
            MainThread.BeginInvokeOnMainThread(async () =>
            {
                await Navigation.PushAsync(new ImagePage(data));
            });
        }
    }
}
```

### Add the Image control in the Image Page

In the **ImagePage.xaml**, add a `Image` control and three buttons:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="SimpleDocumentScanner.ImagePage"
             Title="ImagePage">
    <StackLayout Padding="10">
        <Image   
            x:Name="image"
            Aspect="AspectFit"/>
    </StackLayout>
</ContentPage>
```

### Display the Normalized Document Image

```c#
namespace SimpleDocumentScanner;
using Dynamsoft.Core.Maui;

public partial class ImagePage : ContentPage
{
    ImageData data;
    
    public ImagePage(ImageData data)
    {
        InitializeComponent();
        this.data = data;
    }

    protected override void OnHandlerChanged()
    {
        base.OnHandlerChanged();
        image.Source = data.ToImageSource();
    }
}
```

### Run the Project

Select your device and run the project.

You can get the similar source code of the SimpleDocumentScanner app from the following link:

- [C#](https://github.com/Dynamsoft/capture-vision-maui-samples/tree/main/DocumentScanner/AutoNormalize){:target="_blank"}.

> Note: If you are running Android only on Visual Studio Windows, please manually exclude iOS and Windows platforms. Otherwise, the Visual Studio will report type or namespace not found errors.

![Exclude iOS and Windows from targets](../assets/maui-exclude.png)

## Licensing

- A one-day trial license is available by default for every new device to try Dynamsoft Capture Vision SDK.
- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dcv&package=mobile&utm_source=docs){:target="_blank"} link.
- [Contact us](https://www.dynamsoft.com/company/contact/){:target="_blank"} to purchase a full license.
