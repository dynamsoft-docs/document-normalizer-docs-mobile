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

`DynamsoftDocumentNormalizer` SDK has been revamped to integrate with `DynamsoftCaptureVision (DCV)` architecture. To upgrade from version 1.x to 2.x, we recommend you to follow the [`User Guide`](user-guide.md) and re-write your codes.

Here are some of the main actions you may take:

### Update the Dependencies

Since the SDK architecture is changed, you have to change your `build.gradle` for including the following libraries:

```groovy
dependencies {
    implementation 'com.dynamsoft:dynamsoftcapturevisionrouter:2.0.21'
    implementation 'com.dynamsoft:dynamsoftdocumentnormalizer:2.0.20'
    implementation 'com.dynamsoft:dynamsoftcameraenhancer:4.0.2'
    implementation 'com.dynamsoft:dynamsoftcore:3.0.20'
    implementation 'com.dynamsoft:dynamsoftlicense:3.0.30'
    implementation 'com.dynamsoft:dynamsoftimageprocessing:2.0.21'
    implementation 'com.dynamsoft:dynamsoftutility:1.0.21'
}
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

You should now utilize the provided `capture` APIs instead of the previous `detectQuad` and `normalize` APIs. These `capture` APIs directly return results for boundary detection or document normalization.

```java
CapturedResult capture(String filePath, String templateName) throws CaptureVisionRouterException
CapturedResult capture(byte[] fileBytes, String templateName) throws CaptureVisionRouterException 
CapturedResult capture(Bitmap bitmap, String templateName) throws CaptureVisionRouterException 
CapturedResult capture(ImageData imageData, String templateName) throws CaptureVisionRouterException 
```

#### Batch Image Processing

The DCV architecture allows you to conveniently and continuously obtain frames from `CameraEnhancer`, and detect or normalize them. The key steps are as follows:

- Set a `CameraEnhancer` object as the input of the `CaptureVisionRouter` object via `setInput` API.
- Register a `CapturedResultReceiver` object as the output of the `CaptureVisionRouter` object via `addResultReceiver` API.
- Open/Close camera via `CameraEnhancer.open` and `CameraEnhancer.close` API.
- Start/Stop capturing via `CaptureVisionRouter.startCapturing` and `CaptureVisionRouter.stopCapturing` API.

```java
public class MainActivity extends AppCompatActivity {

    private CaptureVisionRouter mRouter;
    private CameraView mCameraView;
    private CameraEnhancer mCamera;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Add camera view for previewing video.
        mCameraView = findViewById(R.id.camera_view);

        // Create an instance of Dynamsoft Camera Enhancer for video streaming.
        mCamera = new CameraEnhancer(mCameraView, this);

        PermissionUtil.requestCameraPermission(MainActivity.this);

        // Create an instance of Capture Vision Router.
        mRouter = new CaptureVisionRouter(this);

        try {
            mRouter.setInput(mCamera);
        } catch (CaptureVisionRouterException e) {
            e.printStackTrace();
        }

        mRouter.addResultReceiver(new CapturedResultReceiver() {
            @Override
            public void onNormalizedImagesReceived(NormalizedImagesResult result) {
              //TODO:...
            }
        });
    }

    @Override
    public void onResume() {
        super.onResume();
        try {
            mCamera.open();
            mRouter.startCapturing(EnumPresetTemplate.PT_DETECT_AND_NORMALIZE_DOCUMENT);
        } catch (CameraEnhancerException | CaptureVisionRouterException e) {
            e.printStackTrace();
        }
    }

    @Override
    public void onPause() {
        super.onPause();
        try {
            mCamera.close();
        } catch (CameraEnhancerException e) {
            e.printStackTrace();
        }

        mRouter.stopCapturing();
    }
}
```
