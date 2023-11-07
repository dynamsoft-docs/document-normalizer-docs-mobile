---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - Camera Methods
description: This page shows Camera methods of Dynamsoft Document Normalizer for Android SDK.
keywords: Camera methods, DocumentNormalizer, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
pageStartVer: 1.0
permalink: /programming/android/api-reference/document-normalizer-video.html
---


# Video Detecting Methods

> You are viewing a history document page of Dynamsoft Document Normalizer v1.0.30.

## How to Implement Video Detecting

This code snippet displays a complete code on how to configure camera module, start detecting and get detection results from the video streaming.

```java
DocumentNormalizer normalizer;
CameraEnhancer mCameraEnhancer;

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    // Be sure that you have added a cameraView in the layout file.
    DCECameraView cameraView = findViewById(R.id.cameraView);

    try {
        // Create an instance of Dynamsoft Document Normalizer.
        normalizer = new DocumentNormalizer();
    } catch (DocumentNormalizerException e) {
        e.printStackTrace();
    }
    mCameraEnhancer = new CameraEnhancer(MainActivity.this);
    mCameraEnhancer.setCameraView(cameraView);

    // Bind the Camera Enhancer instance to the Document Normalizer instance.
    normalizer.setImageSource(mCameraEnhancer);

    // Result callback configurations
    DetectResultListener mDetectResultListener = new DetectResultListener() {
        // Obtain the detected quad detection results and display.
        @Override
        public void detectResultCallback(int id, ImageData imageData, DetectedQuadResult[] detectedResults) {
            // Add your code to execute when quad detection results are returned.
        }
    };

    normalizer.setDetectResultListener(mDetectResultListener);
}

@Override
public void onResume() {
    // Open the camera and start video quad detecting 
    try {
        mCameraEnhancer.open();
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
    normalizer.startDetecting();
    super.onResume();
}

@Override
public void onPause() {
    // Stop video quad detecting 
    try {
        mCameraEnhancer.close();
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
    normalizer.stopDetecting();
    super.onPause();
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

Sets an instance of ImageSource to get images. `CameraEnhancer` is a specific implementation of ImageSource, which can help the Document Normalizer to acquire video frames continuously for recognition.

```java
void setImageSource(ImageSource source)
```

**Parameters**

`[in] source`: An instance of ImageSource. If you are using `Dynamsoft Camera Enhancer`(DCE) to capture camera frames, pass an instance of `CameraEnhancer`.

**Code Snippet**

```java
// Create an instance of DynamsoftCameraEnhancer and set it as the image source.
DCECameraView cameraView = findViewById(R.id.cameraView);
CameraEnhancer mCameraEnhancer; = new CameraEnhancer(MainActivity.this);
mCameraEnhancer.setCameraView(cameraView);
normalizer.setImageSource(mCameraEnhancer);
```

### startDetecting

Start the document quad detection thread in the video streaming scenario. Please be sure that you have bound a Camera Enhancer to the document normalizer before you trigger `startDetecting`.

```java
void startDetecting()
```

**Code Snippet**

```java
normalizer.startDetecting();
```

### stopDetecting

Stop the document quad detection thread in the video streaming scenario.

```java
void stopDetecting()
```

**Code Snippet**

```java
normalizer.startDetecting();
```

### setDetectResultListener

Set the callback interface to process detection results generated during frame detecting.

```java
void setDetectResultListener(DetectResultListener detectResultListener)
```

**Parameters**

`[in] detectResultListener`: The Callback interface.

**Code Snippet**

```java
// Result callback configurations
DetectResultListener mDetectResultListener = new DetectResultListener() {
    // Obtain the detected quad detection results and display.
    @Override
    public void detectResultCallback(int id, ImageData imageData, DetectedQuadResult[] detectedResults) {
        // Add your code to execute when quad detection results are returned.
    }
};
normalizer.setDetectResultListener(mDetectResultListener);
```
