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

## Table Of Contents

- [System Requirememts](#system-requirements)
- [Build Your First Application](#build-your-first-application)
   - [Create a New Project](#create-a-new-project)
   - [Add the SDK](#add-the-sdk)
   - [Implementing ViewController for Realtime Detection of Quads](#implementing-viewcontroller-for-realtime-detection-of-quads)

   

## System Requirements

- Supported OS: **iOS 11.0** or higher.
- Supported ABI: **arm64** and **x86_64**.
- Development Environment: Xcode 13.0 and above (Xcode 14.1+ recommended).

## Build Your First Application

This guide will walk you through the process of creating a HelloWorld app for normalizing documents via a camera video input.

>Note:
>
> - Xcode 14.0 is used in this guide.
> - You can get the source code of the HelloWord app from the following link
>   - [Objective-C](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Objective-C/HelloWorld){:target="_blank"}.
>   - [Swift](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Swift/HelloWorld){:target="_blank"}.

### Create a New Project

1. Open Xcode and select create a new project.

2. Select **iOS -> App** for your application.

3. Input your product name (HelloWorld), interface (StoryBoard), and language (Objective-C/Swift). We currently do not support SwiftUI and we apologize if this causes any inconvenience.

4. Click on the **Next** button and select the location to save the project.

5. Click on the **Create** button to finish.

### Add the SDK

There are three ways to add the SDK into your project - **Manually**, via **CocoaPods**, or via **Swift Package Manager**.

#### Add the Frameworks Manually

1. Download the SDK package from the <a href="https://download2.dynamsoft.com/ddn/dynamsoft-document-normalizer-ios-2.0.10.zip" target="_blank">Dynamsoft website</a>. After unzipping, you can find the following **Frameworks** under the **Dynamsoft\Frameworks** directory:

   | File | Description |
   | ---- | ----------- |
   | `DynamsoftDocumentNormalizer.xcframework` | The Dynamsoft Document Normalizer SDK which includes the document normalizer related APIs. |
   | `DynamsoftCore.xcframework`  | The core library of the Dynamsoft Capture Vision SDK which includes basic structures and intermediate result related APIs. |
   | `DynamsoftCaptureVisionRouter.xcframework` | The CaptureVisionRouter is used to coordinate the image-processing and semantic-processing products that are being used in the application. It accepts an image source and returns processing results which may contain final results or intermediate results. |
   | `DynamsoftImageProcessing.xcframework` | The image processing library of the Dynamsoft Capture Vision SDK, and so includes the image processing algorithms and APIs. |
   | `DynamsoftLicense.xcframework` | This module includes the licensing API. |
   | `DynamsoftCameraEnhancer.xcframework` | The Dynamsoft Camera Enhancer SDK defines the camera control and frame preprocessing API. |
   | `DynamsoftUtility.xcframework (Optional)` | The module includes functional APIs that support you to integrate the input, filtering the results, generating result images, etc. |

2. Drag and drop the above six (seven if the Utility framework is included) **frameworks** into your Xcode project. Make sure to check *Copy items if needed* and *Create groups* to properly copy the framework into your project's folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for all of the imported frameworks.

#### Add the Frameworks via CocoaPods

1. Create a **Podfile** in your project directory

2. Add the frameworks in your **Podfile**. Please note that not every framework listed above is mentioned in the **Podfile**, but they will still get installed as they are dependencies of the main frameworks listed in the **Podfile**.

   ```sh
   target 'HelloWorld' do
      use_frameworks!

   pod 'DynamsoftCaptureVisionRouter','2.0.10'
   pod 'DynamsoftDocumentNormalizer','2.0.10'
   pod 'DynamsoftCameraEnhancer','4.0.0'
   pod 'DynamsoftUtility','1.0.10'

   end
   ```

3. Execute the `pod command` to install the frameworks and generate workspace(**HelloWorld.xcworkspace**):

   ```sh
   pod install
   ```

> If the `pod install` command fails, please try running `pod update` instead.

#### Add the xcframeworks via Swift Package Manager

1. In your Xcode project, go to **File --> Add Packages**.

2. In the top-right section of the window, search "https://github.com/Dynamsoft/document-normalizer-spm"

3. Select `document-normalizer-spm`, then click **Add Package**.

4. Check all the frameworks and add.

&nbsp;

### Implementing ViewController for Realtime Detection of Boundaries

The main operation of this Hello World app is to scan documents via video. In the main *ViewController*, we will implement this abilty as well as a display for the detected boundaries of the document(s). First off, import the headers in the *ViewController* file:

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

Before we dive into the code to implement the scanning , we should initialize the license first. We suggest to initialize the license in the `AppDelegate` file. Please remember to add `LicenseVerificationListener` to the interface.

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
      // Only the first func application(...) needs to be implemented. The UISceneSession Lifecycle marked functions are not needed.
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
>- To request your own trial license, you can go to the <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=docs" target="_blank">customer portal</a>. You are allowed two 15-day extensions of the trial once the 30-day trial expires.

#### Configure the Camera Module

Now back to the `ViewController`, it's time to create the instances of `CameraEnhancer` and `CameraView`.

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
var dce:CameraEnhancer!
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
var cvr:CaptureVisionRouter!
...
func setUpDCV() {
   cvr = CaptureVisionRouter()
}
```

#### Set the CameraEnhancer as the Input

Include and initialize the `DynamsoftDocumentNormalizer`, bind to the created `CameraEnhancer` instance.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setUpCVR
{
   NSError *cvrError;
   [_cvr setInput:_dce error:&cvrError];
}
```
2. 
```swift
func setUpCVR() {
   try? cvr.setInput(dce)
}
```

#### Set up Result Receiver

In order to receive results, the corresponding `CapturedResultReceiver` must be implemented. The `CapturedResultReceiver` that is implemented depends on which functional product of the Capture Vision suite is being used. In this case, since the Document Normalizer is the one being used, the `onNormalizedImagesReceived` callback should be implemented.

1. Add `CapturedResultReceiver` to the interface.

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

2. Implement `onNormalizedImagesReceived` method to receive the final normalized images as the captured results.

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
      NSError *cvrError;
      [_cvr setInput:_dce error:&cvrError];
      [_cvr addResultReceiver:self error:&cvrError];
      DSMultiFrameResultCrossFilter *filter = [[DSMultiFrameResultCrossFilter alloc] init];
      [filter enableResultCrossVerification:DSCapturedResultItemTypeNormalizedImage isEnabled:true];
      [_cvr addResultFilter:filter error:&cvrError];
   }
   ```
   2. 
   ```swift
   func setUpCvr() {
      try? cvr.setInput(dce)
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
   dce.open() // open the camera
   try? cvr.startCapturing(PresetTemplate.detectAndNormalizeDocument.rawValue)
}
override func viewWillDisappear(_ animated: Bool) {
   super.viewWillDisappear(animated)
   dce.close() // close the camera and release resources
}
```

#### Display the Normalized Image

1. Create a new `UIViewController` class, `ImageViewController`. To do that, please add a new Swift/Objective-C file and name it `ImageViewController`.

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

### Configure the Signing and the Info.plist

1. Before running the project, please make sure that the *Signing & Capabilities* section is properly set.

2. Make sure that the *Privacy - Camera Usage Description* key is added to the Info.plist of the project along with a message that the user will see when the app asks for camera permission.

### Build and Run the Project

1. Select the device that you want to run your app on.
2. Run the project, then your app will be installed on your device.

> Note:
>
> - You can get the source code of the HelloWord app from the following link
>   - [Objective-C](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Objective-C/HelloWorld){:target="_blank"}.
>   - [Swift](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Swift/HelloWorld){:target="_blank"}.
