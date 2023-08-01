---
layout: default-layout
title: Dynamsoft Document Normalizer for iOS - User Guide
description: This is the user guide of Dynamsoft Document Normalizer for iOS SDK.
keywords: user guide, iOS
needAutoGenerateSidebar: true
needGenerateH4Content: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/ios/user-guide.html
---

# Getting Started with iOS

## Requirements

- Supported OS: **iOS 11.0** or higher.
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Xcode 7.1 and above (Xcode 13.0+ recommended).

## Build Your First Application

In this section, let's see how to create a HelloWorld app for normalizing documents from camera video input.

>Note:
>
> - Xcode 13.0 is used here in this guide.
> - You can get the source code of the HelloWord app from the following link
>   - [Objective-C](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Objective-C/HelloWorld).
>   - [Swift](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Swift/HelloWorld).

### Create a New Project

1. Open Xcode and select create a new project.

2. Select **iOS -> App** for your application.

3. Input your product name (Helloworld), interface (StoryBoard) and language (Objective-C/Swift). We currently do not support SwiftUI, so we apologize if this causes any inconvenience.

4. Click on the **Next** button and select the location to save the project.

5. Click on the **Create** button to finish.

### Add the SDK

There are two ways to add the SDK into your project - **Manually** and **CocoaPods**.

#### Add the Frameworks Manually

1. Download the SDK package from the <a href="https://download2.dynamsoft.com/ddn/dynamsoft-document-normalizer-ios-1.0.20.zip" target="_blank">Dynamsoft website</a>. After unzipping, you can find the following **Frameworks** under the **DynamsoftDocumentNormalizer\Frameworks** directory:

   | File | Description |
   | ---- | ----------- |
   | `DynamsoftDocumentNormalizer.xcframework` | The Dynamsoft Document Normalizer SDK which includes the document normalizer related APIs. |
   | `DynamsoftCore.xcframework`  | The core library of the Dynamsoft Capture Vision SDK which includes basic structures and intermediate result related APIs. |
   | `DynamsoftCaptureVisionRouter.xcframework` | The CaptureVisionRouter is used to coordinate the image-processing and semantic-processing products that are being used in the application. It accepts an image source and returns processing results which may contain final results or intermediate results. |
   | `DynamsoftImageProcessing.xcframework` | The image processing library of the Dynamsoft Capture Vision SDK, including image processing algorithms and APIs. |
   | `DynamsoftLicense.xcframework` | This module includes the licensing API. |
   | `DynamsoftCameraEnhancer.xcframework` | The Dynamsoft Camera Enhancer SDK defines the camera control and frame preprocessing API. |
   | `DynamsoftUtility.xcframework (Optional)` | The module includes functional APIs that support you to integrate the input, filtering the results, generating result images, etc. |

2. Drag and drop the above five **frameworks** into your Xcode project. Make sure to check *Copy items if needed* and *Create groups* to properly copy the framework into your project's folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for all of the imported frameworks.

#### Add the Frameworks via CocoaPods

1. Add the frameworks in your **Podfile**.

   ```sh
   target 'HelloWorld' do
      use_frameworks!

   pod 'DynamsoftCaptureVisionRouter','2.0.0'
   pod 'DynamsoftDocumentNormalizer','2.0.0'
   pod 'DynamsoftCore','2.0.0'
   pod 'DynamsoftCameraEnhancer','4.0.0'
   pod 'DynamsoftImageProcessing','2.0.0'
   pod 'DynamsoftLicense','1.0.0'
   pod 'DynamsoftUtility','1.0.0'

   end
   ```

2. Execute the pod command to install the frameworks and generate workspace(**HelloWorld.xcworkspace**):

   ```sh
   pod install
   ```

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

#### Initialize License

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
   [DSLicenseManager initLicense:@"Put your" verificationDelegate:self];
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
>- If the license has expired, you can go to the <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=docs" target="_blank">customer portal</a> to request for an extension.

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
let dce:CameraEnhancer = .init()
...
func setUpCamera() {
   // Create a camera view and add it as a sub view of the current view.
   cameraView = .init(frame: view.bounds)
   cameraView.autoresizingMask = [.flexibleWidth, .flexibleHeight]
   view.insertSubview(cameraView, at: 0)
   // Bind the camera enhancer with the camera view.
   dce.cameraView = cameraView
   // Additional step: Highlight the detected document boundary.
   let layer = cameraView.getDrawingLayer(DrawingLayerId.DDN.rawValue)
   layer?.visible = true
   // You can enable the frame filter feature of Dynamsoft Camera Enhancer.
   // dce.enableEnhancedFeatures(.frameFilter)
}
```

#### Initialize Capture Vision Router

Declare and create an instance of `CaptureVisionRouter`.

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
let cvr:CaptureVisionRouter = .init()
```

#### Set the CameraEnhancer as the Input

Include and initialize the `DynamsoftDocumentNormalizer`, bind to the created `CameraEnhancer` instance.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setUpCvr
{
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
   - (void) onNormalizedImagesReceived:(DSNormalizedImagesResult *)result
   {
      if (_implementCapture != false && result != nil && result.items[0].imageData != nil)
      {
             /** Initialize a new UIView to display the normalized image.*/
             ImageViewController *imageViewController = [[ImageViewController alloc] init];
             NSError * coreError;
             imageViewController.normalizedImage = [result.items[0].imageData toUIImage:&coreError];
             dispatch_async(dispatch_get_main_queue(), ^{
                [self.navigationController pushViewController:imageViewController animated:YES];
             });
      }
   }
   ```
   2. 
   ```swift
   func onNormalizedImagesReceived(_ result: NormalizedImagesResult)
   {
      if let items = result.items, items.count > 0 {
             guard let data = items[0].imageData else {
                return
             }
             /** Initialize a new UIView to display the normalized image.*/
             let resultView = ImageViewController()
             resultView.normalizedImage = try? data.toUIImage
             DispatchQueue.main.async {
                self.present(resultView, animated: true)
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
      NSError *cvrError;
      [_cvr setInput:_dce error:&cvrError];
      [_cvr addResultReceiver:self error:&cvrError];
   }
   ```
   2. 
   ```swift
   func setUpCvr() {
      try? cvr.setInput(dce)
      try? cvr.addResultReceiver(self)
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
}
override func viewWillAppear(_ animated: Bool) {
   super.viewWillAppear(animated)
   dce.open() // open the camera
   try? cvr.startCapturing(PresetTemplate.detectAndNormalizeDocument.rawValue)
}
override func viewWillDisappear(_ animated: Bool) {
   super.viewWillDisappear(animated)
   dce.close() // close the camera and release resources
}
```

#### Display the Normalized Image

1. Create a new `UIViewController` class `ImageViewController`. To do that, please add a new Swift/Objective-C file and name it `ImageViewController`.

  > Note:  **Objective-C only** Add a property `normalizedImage` to the header file of `ImageViewController` (`ImageViewController.h`).

   ```objc
   @property (nonatomic, strong) UIImage * normalizedImage;
   ```

3. Configure the `ImageViewController` to display the normalized image..

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
   import Foundation
   import UIKit

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

### Configure the Signing & Capabilities and the Info.plist

1. Before running the project, please make sure that the *Signing & Capabilities* section is properly set.

2. Make sure that the *Privacy - Camera Usage Description* key is added to the Info.plist of the project along with a message that the user will see when the app asks for camera permission.

### Build and Run the Project

1. Select the device that you want to run your app on.
2. Run the project, then your app will be installed on your device.

> Note:
>
> - You can get the source code of the HelloWord app from the following link
>   - [Objective-C](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Objective-C/HelloWorld).
>   - [Swift](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Swift/HelloWorld).
