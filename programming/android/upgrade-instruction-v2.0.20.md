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

`DynamsoftDocumentNormalizer` SDK has been revamped to integrate with `DynamsoftCaptureVision (DCV)` architecture. To upgrade from version 1.x to 2.x, we recommend that you follow the [`User Guide`](user-guide.md) and re-write your code to match what is in the guide.

Here are some of the main actions you may take:

### Update the Dependencies

Since the SDK architecture has changed, you have to change your `build.gradle` to include the following libraries:

```groovy
dependencies {
    implementation 'com.dynamsoft:dynamsoftcapturevisionrouter:{version-number}'
    implementation 'com.dynamsoft:dynamsoftdocumentnormalizer:{version-number}'
    implementation 'com.dynamsoft:dynamsoftcameraenhancer:{version-number}'
    implementation 'com.dynamsoft:dynamsoftcore:{version-number}'
    implementation 'com.dynamsoft:dynamsoftlicense:{version-number}'
    implementation 'com.dynamsoft:dynamsoftimageprocessing:{version-number}'
    implementation 'com.dynamsoft:dynamsoftutility:{version-number}'
}
```

>Note: Please view [user guide](user-guide.md#add-the-library-via-maven) for the most up-to-date version number.

### Migrate from Class DocumentNormalizer to Class CaptureVisionRouter

The `CaptureVisionRouter` class serves as the central class of DCV's execution flow. It encompasses the following functionalities:

- Retrieving images from the `ImageSourceAdapter`.
- Updating templates and configuring settings.
- Dynamically loading the `DynamsoftDocumentNormalizer` module for document detection and normalization.
- Dispatching the results to registered receivers of type `CapturedResultReceiver`.

### Convert Parameter Templates

The parameter system has been restructured and the template you used for v1.x cannot be directly recognized by v2.x (and beyond). Please <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a> to upgrade your parameter template.

### Update Your Codes

#### Single Image Processing

You should now utilize the provided `capture` API methods instead of the previous `detectQuad` and `normalize` API methods. These `capture` API methods directly return results for boundary detection or document normalization.

```java
CapturedResult capture(String filePath, String templateName) throws CaptureVisionRouterException
CapturedResult capture(byte[] fileBytes, String templateName) throws CaptureVisionRouterException 
CapturedResult capture(Bitmap bitmap, String templateName) throws CaptureVisionRouterException 
CapturedResult capture(ImageData imageData, String templateName) throws CaptureVisionRouterException 
```

#### Batch Image Processing

The DCV architecture allows you to conveniently and continuously obtain frames from the `CameraEnhancer`, and then detect or normalize them. The key steps are as follows:

- Set a `CameraEnhancer` object as the input of the `CaptureVisionRouter` object via the `setInput` API method.
- Register a `CapturedResultReceiver` object as the output of the `CaptureVisionRouter` object via the `addResultReceiver` API method.
- Open/Close camera via `CameraEnhancer.open` and `CameraEnhancer.close` API methods.
- Start/Stop capturing via `CaptureVisionRouter.startCapturing` and `CaptureVisionRouter.stopCapturing` API methods.

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
