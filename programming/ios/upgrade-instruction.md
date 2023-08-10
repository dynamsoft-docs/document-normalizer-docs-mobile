---
layout: default-layout
title: Upgrade Instructions - Dynamsoft Document Normalizer Android Edition
keywords: android, document normalizer, upgrade
description: This page introduces how to upgrade Dynamsoft Document Normalizer Android Edition from 1.x to 2.x
needAutoGenerateSidebar: false
permalink: /programming/android/upgrade-instruction.html
---

# How to Upgrade

## From version 1.x to 2.x

`DynamsoftDocumentNormalizer` SDK has been refactored to integrate with `DynamsoftCaptureVision (DCV)` architecture. To upgrade from version 1.x to 2.x, we recommend you to follow the [`User Guide`](user-guide.md) and re-write your codes.

Here are some of the main actions you may take:

### Update the Dependencies

Since the SDK architecture is changed, you have to change your build.gradle for including the following libraries:

```groovy
pod 'DynamsoftDocumentNormalizer','2.0.10'
pod 'DynamsoftCaptureVisionRouter','2.0.10'
pod 'DynamsoftCameraEnhancer','4.0.0'
pod 'DynamsoftUtility','1.0.10'
```

### Migrate from Class DocumentNormalizer to Class CaptureVisionRouter

The `CaptureVisionRouter` class serves as the central class of the DCV framework's execution flow. It encompasses the following functionalities:

- Retrieving images from the `ImageSourceAdapter`.
- Updating templates and configuring settings.
- Dynamically loading the `DynamsoftDocumentNormalizer` module for document detection and normalization.
- Dispatching the results to registered receivers of type `CapturedResultReceiver`.

### Convert Parameter Templates

The parameter system is restructured and the template you used for v1.x can't be directly recognized by the new version. Please <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a> to upgrade your parameter template.

### Update Your Codes

#### Single Image Processing

You should now utilize the provided `Capture` APIs instead of the previous `DetectQuad` and `Normalize` APIs. These `Capture` APIs directly return results for boundary detection or document normalization.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (nullable DSCapturedResult *)captureFromFile:(NSString *)file
                              templateName:(nonnull NSString*)templateName
                                     error:(NSError *_Nullable *_Nullable)error;
- (nullable DSCapturedResult *)captureFromFileBytes:(NSData *)fileBytes
                                              templateName:(nonnull NSString*)templateName
                                                     error:(NSError *_Nullable *_Nullable)error;
- (nullable DSCapturedResult *)captureFromBuffer:(DSImageData *)buffer
                                templateName:(nonnull NSString*)templateName
                                       error:(NSError * _Nullable * _Nullable)error;
- (nullable DSCapturedResult *)captureFromImage:(UIImage *)image
                                templateName:(nonnull NSString*)templateName
                                        error:(NSError *_Nullable *_Nullable)error;
```
2. 
```swift
func captureFromFile(_ file:String, templateName:String) throws -> CaptureResult
func captureFromFileBytes(_ fileBytes:Data, templateName:String) throws -> CaptureResult
func captureFromBuffer(_ buffer:DSImageData, templateName:String) throws -> CaptureResult
func captureFromBuffer(_ image:UIImage, templateName:String) throws -> CaptureResult
```

#### Batch Image Processing

The DCV architecture allows you to conveniently and continuously obtain frames from `CameraEnhancer`, and detect or normalize them. The key steps are as follows:

- Set a `CameraEnhancer` object as the input of the `CaptureVisionRouter` object via `setInput` API.
- Register a `CapturedResultReceiver` object as the output of the `CaptureVisionRouter` object via `addResultReceiver` API.
- Open/Close camera via `CameraEnhancer.open` and `CameraEnhancer.close` API.
- Start/Stop capturing via `CaptureVisionRouter.startCapturing` and `CaptureVisionRouter.stopCapturing` API.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface ViewController ()<DSCapturedResultReceiver>
@property (nonatomic, strong) DSCaptureVisionRouter *cvr;
@property (nonatomic, strong) DSCameraEnhancer *dce;
@property (nonatomic, strong) DSCameraView *cameraView;
@end
@implementation ViewController
- (void)viewDidLoad {
    NSLog(@"View Did load");
    [super viewDidLoad];
    [self setUpCamera];
    [self setUpCvr];
    _implementCapture = false;
    [self setUpUI];
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
}
- (void)setUpCvr
{
    _cvr = [[DSCaptureVisionRouter alloc] init];
    _allCornersInOneScan = [[NSMutableArray alloc] init];
    NSError *cvrError;
    [_cvr setInput:_dce error:&cvrError];
    [_cvr addResultReceiver:self error:&cvrError];
    DSMultiFrameResultCrossFilter *filter = [[DSMultiFrameResultCrossFilter alloc] init];
    [filter enableResultCrossVerification:DSCapturedResultItemTypeNormalizedImage isEnabled:true];
    [_cvr addResultFilter:filter error:&cvrError];
}
- (void)setUpUI {
    [self.view addSubview:self.captureButton];
}
-(void)onNormalizedImagesReceived:(DSNormalizedImagesResult *)result
{
   // Add your code to do when NormalizedImagesResult is receive.
}
@end
```
2. 
```swift
class ViewController: UIViewController, CapturedResultReceiver {
    var cameraView:CameraView!
    var dce:CameraEnhancer!
    var cvr:CaptureVisionRouter!
    override func viewDidLoad() {
        super.viewDidLoad()
        setUpCamera()
        setUpDCV()
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
    func setUpCamera() {
        cameraView = .init(frame: view.bounds)
        cameraView.autoresizingMask = [.flexibleWidth, .flexibleHeight]
        view.insertSubview(cameraView, at: 0)
        // Bind the camera enhancer with the camera view.
        dce = CameraEnhancer()
        dce.cameraView = cameraView
        // Additional step: Highlight the detected document boundary.
        let layer = cameraView.getDrawingLayer(DrawingLayerId.DDN.rawValue)
        layer?.visible = true
    }
    func setUpDCV() {
        cvr = CaptureVisionRouter()
        try? cvr.setInput(dce)
        try? cvr.addResultReceiver(self)
    }
    func onNormalizedImagesReceived(_ result: NormalizedImagesResult) {
        // Add your code to do when NormalizedImagesResult is receive.
    }
}
```
