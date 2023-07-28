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
   | `DynamsoftDocumentNormalizer.framework` | The Dynamsoft Document Normalizer SDK, including document normalizer related APIs. |
   | `DynamsoftCore.framework`  | The core library of Dynamsoft's capture vision SDKs, including common basic structure and license related APIs. |
   | `DynamsoftIntermediateResult.framework` | The common intermediate result library of Dynamsoft's capture vision SDKs, including all intermediate results produced in the process of decoding a barcode, recognizing a label or normalizing a document. |
   | `DynamsoftImageProcessing.framework` | The image processing library of Dynamsoft's capture vision SDKs, including image processing algorithms and APIs. |
   | `DynamsoftCameraEnhancer.framework` | The Dynamsoft Camera Enhancer SDK, including camera control and frame preprocessing APIs. |

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
   #import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
   #import <DynamsoftDocumentNormalizer/DynamsoftDocumentNormalizer.h>
   #import <DynamsoftCaptureVisionRouter/DynamsoftCaptureVisionRouter.h>
   #import <DynamsoftUtility/DynamsoftUtility.h>
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
              if !isSuccess {
                  print("\(String(describing: error))")
              }
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
   @property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
   @property(nonatomic, strong) DCECameraView *dceView;
   ...
   - (void)configDCE{
          _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
          [self.view addSubview:_dceView];
          _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
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
   - (void)configDDN{
      [DDNDataManager instance].ddn = [DynamsoftDocumentNormalizer new];
      // Bind the DocumentNormalizer and CameraEnhancer instance
      [[DDNDataManager instance].ddn setImageSource:_dce];
   }
   ```
   2. 
   ```swift
   func setUpDCV() {
      try? cvr.setInput(dce)
      try? cvr.addResultReceiver(self)
   }
   ```

#### Set up CaptureResultReceiver to Receive Output

1. Add `CapturedResultReceiver` to your ViewController.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
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
   // Add detectResultCallback method in the view controller.
   - (void)onNormalizedImagesReceived:(DSNormalizedImagesResult)result
   {
      // We will add code here to deal with the detection result and open another view controller.
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

4. Add the methods to run when the view is loaded.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   ```
   2. 
   ```swift
   override func viewWillAppear(_ animated: Bool) {
      super.viewWillAppear(animated)
      configUI()
      dce.open()
      try? cvr.startCapturing("detect-and-normalize-document")
   }
   override func viewWillDisappear(_ animated: Bool) {
      super.viewWillDisappear(animated)
      dce.close()
   }
   ```

#### Add a Capture Button

Add the button to confirm the capture.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
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

#### Diplay the Normalized Image

1. Create a new empty activity named `ResultViewController`.

2. Display the normalized image.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   ```
   2. 
   ```swift
   import DynamsoftCore
   import DynamsoftCaptureVisionRouter
   import DynamsoftDocumentNormalizer
   class ImageViewController: UIViewController{
      var data:ImageData!
      var imageView:UIImageView!
      override func viewDidLoad() {
             super.viewDidLoad()
             // Do any additional setup after loading the view.
             setUpView()
      }
      func setUpView() {
             imageView = UIImageView.init(frame: view.bounds)
             view.addSubview(imageView)
             let image = try? data.toUIImage()
             DispatchQueue.main.async { [self] in
                imageView.image = image
             }
      }
   }
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
