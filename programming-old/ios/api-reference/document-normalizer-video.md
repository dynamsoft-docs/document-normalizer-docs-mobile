---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - Video Detecting Methods
description: This page shows Video Detecting methods of Dynamsoft Document Normalizer for iOS SDK.
keywords: Video Detecting methods, DynamsoftCameraEnhancer, api reference, ios
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
pageStartVer: 1.0
permalink: /programming/ios/api-reference/document-normalizer-video.html
---


# Video Detecting Methods

> You are viewing a history document page of Dynamsoft Document Normalizer v1.0.30.

## How to Implement Video Detecting

This code snippet displays a complete code on how to configure camera module, start detecting and get detection results from the video streaming.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface ViewController ()<DetectResultListener>
@property(nonatomic, strong) DynamsoftDocumentNormalizer *ddn;
@property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
@property(nonatomic, strong) DCECameraView *dceView;
@end
@implementation ViewController
- (void)viewDidLoad{
   [super viewDidLoad];
   [self configurationDDN];
}
- (void)configurationDDN{
   _ddn =  [[DynamsoftDocumentNormalizer alloc] init];
   _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
   [self.view addSubview:_dceView];
   _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   [_dce open];
   [_ddn setImageSource:_dce];
   [_ddn setDetectResultListener:self];
   [_ddn startDetecting];
}
- (void)detectResultCallback:(NSInteger)frameId imageData:(iImageData *)imageData results:(NSArray<iDetectQuadResult *> *)results{
    // Add your code to do when barcode result is returned.
}
```
2. 
```swift
class ViewController: UIViewController, DetectResultListener{
   var SafeAreaBottomHeight:CGFloat = UIApplication.shared.statusBarFrame.size.height > 20 ? 34 : 0
   var mainHeight = UIScreen.main.bounds.height
   var mainWidth = UIScreen.main.bounds.width
   var dce:DynamsoftCameraEnhancer! = nil
   var dceView:DCECameraView! = nil
   var ddn:DynamsoftDocumentNormalizer! = nil
   override func viewDidLoad() {
          super.viewDidLoad()
          configurationDDN()
   }
   func configurationDDN(){
          ddn = DynamsoftDocumentNormalizer()
          var barHeight = self.navigationController?.navigationBar.frame.height
          if UIApplication.shared.statusBarFrame.size.height <= 20 {
             barHeight = 20
          }
          dceView = DCECameraView(frame: CGRect(x: 0, y: barHeight!, width: mainWidth, height: mainHeight - SafeAreaBottomHeight - barHeight!))
          self.view.addSubview(dceView)
          dce = DynamsoftCameraEnhancer(view: dceView)
          dce.open()
          ddn.setImageSource(dce)
          ddn.setDetectResultListener(self)
          ddn.startDetecting()
   }
   func detectResultCallback(_ frameId: Int, imageData: iImageData, results: [iDetectQuadResult]?){
          // Add your code
   }
}
```

> Note:
>  
> - `DynamsoftCameraEnhancer` library is included when implementing **Video Quad Detecting**. It provides APIs that help you quickly deploy a camera module and capture video streaming for document normalizer.

## Methods

Use the following methods to control the start/stop of video streaming document detecting and get the detection results.

| Method | Description |
|--------|-------------|
| [`setImageSource`](#setimagesource) | Sets an instance of ImageSource to get images.  |
| [`startDetecting`](#startdetecting) | Start the document quad detection thread in the video streaming scenario. |
| [`stopDetecting`](#stopdetecting) | Stop the document quad detection thread in the video streaming scenario. |
| [`setDetectResultListener`](#setdetectresultlistener) | Set callback interface to process detection results generated during frame detecting. |

---

### setImageSource

Sets an instance of ImageSource to get images. `DynamsoftCameraEnhancer` is a specific implementation of ImageSource, which can help the Document Normalizer to acquire video frames continuously for recognition.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setImageSource:(ImageSource* _Nonnull)source;
```
2. 
```swift
func setImageSource(_ source: ImageSource?)
```

**Parameters**

`[in] source`: An instance of ImageSource. If you are using `Dynamsoft Camera Enhancer`(DCE) to capture camera frames, pass an instance of `DynamsoftCameraEnhancer`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)configurationDDN{
   _ddn =  [[DynamsoftDocumentNormalizer alloc] init];
   _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   [_ddn setImageSource:_dce];
}
```
2. 
```swift
func configurationDDN(){
   ddn = DynamsoftDocumentNormalizer()
   dce = DynamsoftCameraEnhancer(view: dceView)
   ddn.setImageSource(dce)
}
```

### startDetecting

Start the document quad detection thread in the video streaming scenario. Please be sure that you have bound a Camera Enhancer to the document normalizer before you trigger `startDetecting`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(void)startDetecting
```
2. 
```swift
func startDetecting()
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_ddn startDetecting];
```
2. 
```swift
ddn.startDetecting()
```

### stopDetecting

Stop the document quad detection thread in the video streaming scenario.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(void)stopDetecting
```
2. 
```swift
func stopDetecting()
```

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_ddn stopDetecting];
```
2. 
```swift
ddn.stopDetecting()
```

### setDetectResultListener

Set the callback interface to process detection results generated during frame detecting.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(void)setDetectResultListener:(id<DetectResultListener>)detectResultListener;
```
2. 
```swift
func setDetectResultListener(_ listener: DetectResultListener)
```

**Parameters**

`[in] detectResultListener`: The Callback interface.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface ViewController ()<DetectResultListener>
- (void)configurationDDN{
   [_ddn setDetectResultListener:self];
}
- (void)detectResultCallback:(NSInteger)frameId imageData:(iImageData *)imageData results:(NSArray<iDetectQuadResult *> *)results{
    // Add your code to do when barcode result is returned.
}
```
2. 
```swift
class ViewController: UIViewController, DetectResultListener{
   func configurationDDN(){
          ddn.setDetectResultListener(self)
   }
   func detectResultCallback(_ frameId: Int, imageData: iImageData, results: [iDetectQuadResult]?){
          // Add your code
   }
}
```
