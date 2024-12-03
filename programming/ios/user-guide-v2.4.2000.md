---
layout: default-layout
title: Detect and Normalize Document - iOS User Guide
description: This page introduce how to detect and normalize document with Dynamsoft Capture Vision iOS SDK.
keywords: user guide, iOS, document scanner
needAutoGenerateSidebar: true
needGenerateH4Content: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
---

# iOS User Guide for Document Scanner Integration

- [iOS User Guide for Document Scanner Integration](#ios-user-guide-for-document-scanner-integration)
	- [System Requirements](#system-requirements)
	- [Add the SDK](#add-the-sdk)
		- [Add the xcframeworks via CocoaPods](#add-the-xcframeworks-via-cocoapods)
		- [Add the xcframeworks via Swift Package Manager](#add-the-xcframeworks-via-swift-package-manager)
	- [Build Your First Application](#build-your-first-application)
		- [Create a New Project](#create-a-new-project)
		- [Include the Library](#include-the-library)
		- [Initialize License](#initialize-license)
		- [Main ViewController for Realtime Detection of Quads](#main-viewcontroller-for-realtime-detection-of-quads)
			- [Get Prepared with the Camera Module](#get-prepared-with-the-camera-module)
			- [Initialize Capture Vision Router](#initialize-capture-vision-router)
			- [Set up Result Receiver](#set-up-result-receiver)
			- [Configure the methods viewDidLoad, viewWillAppear, and viewWillDisappear](#configure-the-methods-viewdidload-viewwillappear-and-viewwilldisappear)
			- [Display the Normalized Image](#display-the-normalized-image)
		- [Configure Camera Permissions](#configure-camera-permissions)
		- [Additional Steps for iOS 12.x or Lower Versions](#additional-steps-for-ios-12x-or-lower-versions)
		- [Build and Run the Project](#build-and-run-the-project)

## System Requirements

- Supported OS: iOS 11 or higher (iOS 13 and higher recommended).
- Supported ABI: arm64 and x86_64.
- Development Environment: Xcode 13 and above (Xcode 14.1+ recommended).

## Add the SDK

There are two ways to add the SDK into your project - **CocoaPods**, or via **Swift Package Manager**.

### Add the xcframeworks via CocoaPods

1. Add the frameworks in your **Podfile**.

   ```sh
   target 'HelloWorld' do
      use_frameworks!

   pod 'DynamsoftCaptureVisionBundle','2.4.2000'

   end
   ```

2. Execute the pod command to install the frameworks and generate workspace(**HelloWorld.xcworkspace**):

   ```sh
   pod install
   ```

### Add the xcframeworks via Swift Package Manager

1. In your Xcode project, go to **File --> AddPackages**.

2. In the top-right section of the window, search "https://github.com/Dynamsoft/capture-vision-spm"

3. Select `capture-vision-spm`, choose `Exact version`, enter **2.4.2000**, then click **Add Package**.

4. Check all the frameworks and add.

&nbsp;

## Build Your First Application

This guide will walk you through the process of creating a HelloWorld app for detecting and normalizing documents via a camera video input.

>Note:
>
> - Xcode 14.0 is used in this guide.
> - You can get the source code of the HelloWorld app from the following link
>   - [Objective-C](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/ios/DocumentScanner/AutoNormalizeObjc){:target="_blank"}.
>   - [Swift](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/ios/DocumentScanner/AutoNormalize){:target="_blank"}.

### Create a New Project

1. Open Xcode and select create a new project.

2. Select **iOS -> App** for your application.

3. Input your product name (HelloWorld), interface (StoryBoard) and language (Objective-C/Swift).

4. Click on the **Next** button and select the location to save the project.

5. Click on the **Create** button to finish.

### Include the Library

Add the SDK to your new project. Please read [Add the SDK](#add-the-sdk) section for more details.

### Initialize License

Initialize the license first. It is suggested to initialize the license in `AppDelegate` file.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Import the DynamsoftLicense module to init license
#import <DynamsoftLicense/DynamsoftLicense.h>
// Add LicenseVerificationListener to the interface
@interface AppDelegate ()<LicenseVerificationListener>
@end
@implementation AppDelegate
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
   // Override point for customization after application launch.
   [DSLicenseManager initLicense:@"Put your license key here." verificationDelegate:self];
   return YES;
}
-(void)onLicenseVerified:(BOOL)isSuccess error:(NSError *)error
{
   // Add your code to do when license server returns.
}
...
@end
```
2. 
```swift
// Import the DynamsoftLicense module to init license
import DynamsoftLicense
// Add LicenseVerificationListener to the interface
class AppDelegate: UIResponder, UIApplicationDelegate, LicenseVerificationListener {
   var window: UIWindow?
   func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
          // Override point for customization after application launch.
          LicenseManager.initLicense("Put your license key here.", verificationDelegate: self)
          return true
   }
   // Implement the callback method of LicenseVerificationListener.
   func onLicenseVerified(_ isSuccess: Bool, error: Error?) {
          // Add your code to do when license server returns.
   }
   ...
}
```

>Note:  
>  
>- Network connection is required for the license to work.
>- The license string here will grant you a time-limited trial license.
>- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=ddn&utm_source=guide&package=ios){:target="_blank"} link

&nbsp;

### Main ViewController for Realtime Detection of Quads

In the main view controller, your app will scan documents via video streaming and display the detect quadrilateral area on the screen. First of all, import the headers in the ViewController file.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   #import <DynamsoftCore/DynamsoftCore.h>
   #import <DynamsoftCaptureVisionRouter/DynamsoftCaptureVisionRouter.h>
   #import <DynamsoftDocumentNormalizer/DynamsoftDocumentNormalizer.h>
   #import <DynamsoftImageProcessing/DynamsoftImageProcessing.h>
   #import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
   ```
   2. 
   ```swift
   import DynamsoftCore
   import DynamsoftCaptureVisionRouter
   import DynamsoftDocumentNormalizer
   import DynamsoftUtility
   import DynamsoftCameraEnhancer
   ```

#### Get Prepared with the Camera Module

Create the instances of `CameraEnhancer` and `CameraView`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, strong) DSCameraEnhancer *dce;
@property (nonatomic, strong) DSCameraView *cameraView;
...
- (void)setUpCamera
{
   _cameraView = [[DSCameraView alloc] initWithFrame:self.view.bounds];
   [_cameraView setAutoresizingMask:UIViewAutoresizingFlexibleWidth];
   [self.view addSubview:_cameraView];
   [_cameraView addSubview:_captureButton];
   _dce = [[DSCameraEnhancer alloc] init];
   [_dce setCameraView:_cameraView];
   DSDrawingLayer * layer = [_cameraView getDrawingLayer:DSDrawingLayerIdDDN];
   [layer setVisible:true];
   // You can enable the frame filter feature of Dynamsoft Camera Enhancer.
   //[_dce enableEnhancedFeatures:DSEnhancerFeatureFrameFilter];
}
```
2. 
```swift
var cameraView:CameraView!
let dce:CameraEnhancer!
...
func setUpCamera() {
   // Create a camera view and add it as a sub view of the current view.
   cameraView = .init(frame: view.bounds)
   cameraView.autoresizingMask = [.flexibleWidth, .flexibleHeight]
   view.insertSubview(cameraView, at: 0)
   // Bind the camera enhancer with the camera view.
   dce = CameraEnhancer()
   dce.cameraView = cameraView
   // Additional step: Highlight the detected document boundary.
   let layer = cameraView.getDrawingLayer(DrawingLayerId.DDN.rawValue)
   layer?.visible = true
   // You can enable the frame filter feature of Dynamsoft Camera Enhancer.
   // dce.enableEnhancedFeatures(.frameFilter)
}
```

#### Initialize Capture Vision Router

Once the camera component is set up, declare and create an instance of `CaptureVisionRouter` and set its input to the Camera Enhancer object you created in the last step.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, strong) DSCaptureVisionRouter *cvr;
...
- (void)setUpCvr
{
   _cvr = [[DSCaptureVisionRouter alloc] init];
}
```
2. 
```swift
let cvr:CaptureVisionRouter!
func setUpDCV() {
   cvr = CaptureVisionRouter()
}
```

Bind your `CaptureVisionRouter` instance with the created `CameraEnhancer` instance.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setUpCvr
{
   ...
   NSError *cvrError;
   [_cvr setInput:_dce error:&cvrError];
}
```
2. 
```swift
func setUpCvr() {
   try? cvr.setInput(dce)
}
```

#### Set up Result Receiver

1. Add `CapturedResultReceiver` to your ViewController.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @interface ViewController ()<DSCapturedResultReceiver>
   ```
   2. 
   ```swift
   class ViewController: UIViewController, CapturedResultReceiver {
      ...
   }
   ```

2. Implement `onNormalizedImagesReceived` method to receive the normalized images as the captured results.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   -(void)onNormalizedImagesReceived:(DSNormalizedImagesResult *)result
   {
      if (_implementCapture && result!=nil && result.items[0].imageData!=nil)
      {
             _implementCapture = false;
             ImageViewController *imageViewController = [[ImageViewController alloc] init];
             NSError * error;
             imageViewController.resultUIImage = [result.items[0].imageData toUIImage:&error];
             dispatch_async(dispatch_get_main_queue(), ^{            [self.navigationController pushViewController:imageViewController animated:YES];
             });
      }
   }
   ```
   2. 
   ```swift
   func onNormalizedImagesReceived(_ result: NormalizedImagesResult) {
      print("Normalized image received")
      if let items = result.items, items.count > 0 {
             guard let data = items[0].imageData else {
                return
             }
             let resultView = ImageViewController()
             resultView.data = data
             if implementCapture
             {
                DispatchQueue.main.async {
                       self.present(resultView, animated: true)
                }
             }
      }
   }
   ```

3. Add the result receiver to the `CaptureVisionRouter`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   - (void)setUpCvr
   {
      ...
      NSError *cvrError;
      [_cvr addResultReceiver:self error:&cvrError];
      DSMultiFrameResultCrossFilter *filter = [[DSMultiFrameResultCrossFilter alloc] init];
      [filter enableResultCrossVerification:DSCapturedResultItemTypeNormalizedImage isEnabled:true];
      [_cvr addResultFilter:filter error:&cvrError];
   }
   ```
   2. 
   ```swift
   func setUpCvr() {
      try? cvr.addResultReceiver(self)
      let filter = MultiFrameResultCrossFilter.init()
      filter.enableResultCrossVerification(.normalizedImage, isEnabled: true)
      try? cvr.addResultFilter(filter)
   }
   ```

4. Add a `confirmCapture` button to confirm the result.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @property (nonatomic, strong) UIButton *captureButton;
   ...
   - (void)addCaptureButton {
      [self.view addSubview:self.captureButton];
   }
   - (UIButton *)captureButton {
      NSLog(@"Start adding button");
      CGFloat screenWidth = [UIScreen mainScreen].bounds.size.width;
      CGFloat screenHeight = [UIScreen mainScreen].bounds.size.height;
      if (!_captureButton) {
             _captureButton = [UIButton buttonWithType:UIButtonTypeCustom];
             _captureButton.frame = CGRectMake((screenWidth - 150) / 2.0, screenHeight - 100, 150, 50);
             _captureButton.backgroundColor = [UIColor grayColor];
             _captureButton.layer.cornerRadius = 10;
             _captureButton.layer.borderColor = [UIColor darkGrayColor].CGColor;
             [_captureButton setTitle:@"Capture" forState:UIControlStateNormal];
             [_captureButton setTitleColor:[UIColor whiteColor] forState:UIControlStateNormal];
             [_captureButton addTarget:self action:@selector(setCapture) forControlEvents:UIControlEventTouchUpInside];
      }
      return _captureButton;
   }
   ```
   2. 
   ```swift
   var captureButton:UIButton!
   var implementCapture:Bool = false
   ...
   func addCaptureButton()
   {
      let w = UIScreen.main.bounds.size.width
      let h = UIScreen.main.bounds.size.height
      let SafeAreaBottomHeight: CGFloat = UIApplication.shared.statusBarFrame.size.height > 20 ? 34 : 0
      let photoButton = UIButton(frame: CGRect(x: w / 2 - 60, y: h - 100 - SafeAreaBottomHeight, width: 120, height: 60))
      photoButton.setTitle("Capture", for: .normal)
      photoButton.backgroundColor = UIColor.green
      photoButton.addTarget(self, action: #selector(confirmCapture), for: .touchUpInside)
      DispatchQueue.main.async(execute: { [self] in
             view.addSubview(photoButton)
      })
   }
   @objc func confirmCapture()
   {
      implementCapture = true
   }
   ```

#### Configure the methods viewDidLoad, viewWillAppear, and viewWillDisappear

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)viewDidLoad {
   [super viewDidLoad];
   [self setUpCamera];
   [self setUpCvr];
   [self addCaptureButton];
}
- (void)viewWillAppear:(BOOL)animated
{
   [super viewWillAppear:animated];
   [_dce open];
   NSError *cvrError;
   [_cvr startCapturing:DSPresetTemplateDetectAndNormalizeDocument error:&cvrError];
}
- (void)viewWillDisappear:(BOOL)animated
{
   [super viewWillAppear:animated];
   [_dce close];
}
```
2. 
```swift
override func viewDidLoad() {
   super.viewDidLoad()
   setUpCamera()
   setUpCvr()
   addCaptureButton()
}
override func viewWillAppear(_ animated: Bool) {
   super.viewWillAppear(animated)
   dce.open()
   try? cvr.startCapturing(PresetTemplate.detectAndNormalizeDocument.rawValue)
}
override func viewWillDisappear(_ animated: Bool) {
   super.viewWillDisappear(animated)
   dce.close()
}
```

#### Display the Normalized Image

1. Create a new `UIViewController` class `ImageViewController`.

2. Add a property `normalizedImage` to the header file of `ImageViewController` (Objective-C only).

   ```objc
   @property (nonatomic, strong) UIImage * normalizedImage;
   ```

2. Configure the `ImageViewController` to display the normalized image..

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   #import "ImageViewController.h"
   #import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
   @interface ImageViewController()
   @property (nonatomic, strong) UIImageView *imageView;
   @end
   @implementation ImageViewController
   -(void)viewDidLoad
   {
      NSLog(@"ImageViewController loaded");
      [super viewDidLoad];
      [self setUpView];
   }
   - (void)setUpView
   {
      _imageView = [[UIImageView alloc] initWithFrame:self.view.bounds];
      [self.view addSubview:_imageView];
      NSError *coreError;
      [_imageView setContentMode:UIViewContentModeScaleAspectFit];
      [_imageView setImage:self.normalizedImage];
   }
   @end
   ```
   2. 
   ```swift
   class ImageViewController: UIViewController{
      var normalizedImage:UIImage!
      var imageView:UIImageView!
      override func viewDidLoad() {
             super.viewDidLoad()
             setUpView()
      }
      func setUpView() {
             imageView = UIImageView.init(frame: view.bounds)
             imageView.contentMode = .scaleAspectFit
             view.addSubview(imageView)
             DispatchQueue.main.async { [self] in
                imageView.image = normalizedImage
             }
      }
   }
   ```

&nbsp;

### Configure Camera Permissions

Add **Privacy - Camera Usage Description** to the `info.plist` of your project to request camera permission. An easy way to do this is to access your project settings, go to *Info* and then add this Privacy property to the iOS target properties list.

### Additional Steps for iOS 12.x or Lower Versions

If your iOS version is 12.x or lower, please add the following additional steps:

1. Remove the methods `application:didDiscardSceneSessions:` and `application:configurationForConnectingSceneSession:options:` from your `AppDelegate` file.
2. Remove the `SceneDelegate.Swift` file (`SceneDelegate.h` & `SceneDelegate.m` for Objective-C).
3. Remove the `Application Scene Manifest` from your info.plist file.
4. Declaire the window in your `AppDelegate.Swift` file (`AppDelegate.h` for Objective-C).

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @interface AppDelegate : UIResponder <UIApplicationDelegate>
   @property (strong, nonatomic) UIWindow *window;
   @end
   ```
   2. 
   ```swift
   import UIKit
   @main
   class AppDelegate: UIResponder, UIApplicationDelegate {
      var window: UIWindow?
   }
   ```

### Build and Run the Project

1. Select the device that you want to run your app on.
2. Run the project, then your app will be installed on your device.

> Note:
>
> - You can get the source code of the HelloWorld app from the following link
>   - [Objective-C](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/ios/DocumentScanner/AutoNormalizeObjc){:target="_blank"}.
>   - [Swift](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/ios/DocumentScanner/AutoNormalize){:target="_blank"}.
