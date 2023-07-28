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
   | `DynamsoftDocumentNormalizer.xcframework` | The Dynamsoft Document Normalizer SDK, including document normalizer related APIs. |
   | `DynamsoftCore.xcframework`  | The core library of Dynamsoft's capture vision SDKs, including basic structures and intermediate result related APIs. |
   | `DynamsoftCaptureVisionRouter.xcframework` | The CaptureVisionRouter is what a user uses to interact with image-processing and semantic-processing products in their applications. It accepts an image source and returns processing results which may contain Final results or Intermediate Results. |
   | `DynamsoftImageProcessing.xcframework` | The image processing library of Dynamsoft's capture vision SDKs, including image processing algorithms and APIs. |
   | `DynamsoftLicense.xcframework` | The module includes the licensing APIs. |
   | `DynamsoftCameraEnhancer.xcframework` | The Dynamsoft Camera Enhancer SDK, including camera control and frame preprocessing APIs. |
   | `DynamsoftUtility.xcframework (Optional)` | The module includes functional APIs that support you to integrate the input, filtering the results, generating result images, etc. |

2. Drag and drop the above five **frameworks** into your Xcode project. Make sure to check Copy items if needed and Create groups to copy the framework into your project's folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for DynamsoftDocumentNormalizer and DynamsoftCameraEnhancer.

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
   #import <DynamsoftLicense/DynamsoftLicense.h>
   #import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
   ```
   2. 
   ```swift
   import DynamsoftCore
   import DynamsoftCameraEnhancer
   import DynamsoftDocumentNormalizer
   import DynamsoftCaptureVisionRouter
   import DynamsoftUtility
   ```

#### Initialize License

Initialize the license first. It is suggested to initialize the license in `AppDelegate` file.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
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
      dce.enableEnhancedFeatures(.frameFilter)
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
   NSError *cvrError;
}
```
2. 
```swift
let cvr:CaptureVisionRouter = .init()
private var data:ImageData!
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
   ...
   [_cvr setInput:_dce error:&cvrError];
}
```
2. 
```swift
func setUpDCV() {
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
             _implementCapture = false;
             dispatch_async(dispatch_get_main_queue(), ^{
                NSLog(@"Captured");
                ImageViewController *imageViewController = [[ImageViewController alloc] init];
                NSError * coreError;
                imageViewController.resultUIImage = [result.items[0].imageData toUIImage:&coreError];
                NSLog(@"ToUIImage:%@", coreError);
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
             DispatchQueue.main.async(execute: {
                self.cvr.stopCapturing()
             })
             let resultView = ImageViewController()
             resultView.data = data
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
      // _cvr = [[DSCaptureVisionRouter alloc] init];
      // NSError *cvrError;
      // [_cvr setInput:_dce error:&cvrError];
      [_cvr addResultReceiver:self error:&cvrError];
   }
   ```
   2. 
   ```swift

   ```

#### Add a Capture Button

Add a capture button. When the button is clicked, the image will be capture and normalized.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   -(void)setCapture
   {
      _implementCapture = true;
      NSLog(@"Implement Capture  = true");
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
   private var confirmCapture = false
   ...
   @objc func capture() {
      confirmCapture = true
   }
   func configUI() {
      let w = UIScreen.main.bounds.size.width
      let h = UIScreen.main.bounds.size.height
      let SafeAreaBottomHeight: CGFloat = UIApplication.shared.statusBarFrame.size.height > 20 ? 34 : 0
      let photoButton = UIButton(frame: CGRect(x: w / 2 - 60, y: h - 100 - SafeAreaBottomHeight, width: 120, height: 60))
      photoButton.setTitle("Capture", for: .normal)
      photoButton.backgroundColor = UIColor.green
      photoButton.addTarget(self, action: #selector(capture), for: .touchUpInside)
      DispatchQueue.main.async(execute: { [self] in
             view.addSubview(photoButton)
      })
   }
   ```

&nbsp;

#### Display the Normalized Image

1. Create a new class `UIViewController` and name it `ImageViewController`.

2. Add an `resultUIImage` property to the header of `ImageViewController` to receive the normalized image as a UIImage.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   @property (nonatomic, strong) UIImage * resultUIImage;
   ```
   2. 
   ```swift
   ```

3. Go back to the `onNormalizedImagesReceived` method. Add code to send the normalized image to the result view.

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
             _implementCapture = false;
             dispatch_async(dispatch_get_main_queue(), ^{
                NSLog(@"Captured");
                ImageViewController *imageViewController = [[ImageViewController alloc] init];
                NSError * coreError;
                imageViewController.resultUIImage = [result.items[0].imageData toUIImage:&coreError];
                NSLog(@"ToUIImage:%@", coreError);
                [self.navigationController pushViewController:imageViewController animated:YES];
             });
      }
   }
   ```
   2. 
   ```swift
   ```

&nbsp;

### Build and Run the Project

1. Select the device that you want to run your app on.
2. Run the project, then your app will be installed on your device.

> Note:
>
> - You can get the source code of the HelloWord app from the following link
>   - [Objective-C](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Objective-C/HelloWorld).
>   - [Swift](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/ios/Swift/HelloWorld).
