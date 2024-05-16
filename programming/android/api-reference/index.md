---
layout: default-layout
title: Dynamsoft Document Normalizer Android API Reference - Main Page
description: This is the main page of Dynamsoft Document Normalizer SDK API Reference for Android Language.
keywords: Document Normalizer, api reference, Android
---

# SDK Overview: Modules and Main APIs

This page provides an overview of the various modules and highlights the most essential APIs that form the backbone of Dynamsoft Document Normalizer SDK.

## Modules Summary

The Dynamsoft Document Normalizer (DDN) SDK is built on the Dynamsoft Capture Vision (DCV) framework, which includes multiple modules working together to achieve boundary detection or document normalization. The hierarchical structure diagram below illustrates the various modules of the DDN SDK (with modules at the top depending on those below).

<div align="center">
    <p><img src="../../assets/dcv-ddn-dependency.png" width="70%" alt="region-def"></p>
    <p>Modules hierarchical of the DDN SDK</p>
</div>

The table below describes details the functionalities of these modules:

| Module |Description | Mandatory/Optional|
|:--------|:------------|:---|
| `DynamsoftCaptureVisionRouter.aar`(CVR) | Provides APIs for single/multiple images processing, setting configurations, and other features. | Mandatory |
| `DynamsoftDocumentNormalizer.aar`(DDN) | This library mainly provides boundary detection & document normalization algorithms. It includes APIs for you to configure detection & normalization settings and obtaining the processing results. | Mandatory |
| `DynamsoftCore.aar`(Core) | Provides basic structures and intermediate result related APIs. | Mandatory |
| `DynamsoftImageProcessing.aar`(DIP) | This library mainly provides image processing algorithms. | Mandatory |
| `DynamsoftLicense.aar`(License) | Provides license activation or management APIs. | Mandatory |
| `DynamsoftCameraEnhancer.aar`(DCE) | The <a href="/camera-enhancer/docs/mobile/programming/android/" target="_blank">Dynamsoft Camera Enhancer (DCE) SDK</a> provides camera control, camera enhancements, and basic UI configuration features. | Optional |
| `DynamsoftUtility.aar`(Utility) | The utility library, which includes multiple implementations of image source adapters, result filter, image exporter, and other utility APIs etc.  | Optional |

## Main APIs

### Capture Vision Router

The main class [`CaptureVisionRouter`]({{ site.dcv_android_api }}capture-vision-router/capture-vision-router.html) acts as the SDK entry point and provides the following essential APIs:

- [Set input]({{ site.dcv_android_api }}capture-vision-router/multiple-file-processing.html#setinput)
- [Config capture settings]({{ site.dcv_android_api }}capture-vision-router/settings.html)
- [Add result receiver]({{ site.dcv_android_api }}capture-vision-router/multiple-file-processing.html#addresultreceiver)
- [Start video stream boundary detection or document normalization]({{ site.dcv_android_api }}capture-vision-router/multiple-file-processing.html#startcapturing)

### Image Source Adapter

The [`ImageSourceAdapter`]({{ site.dcv_android_api }}core/basic-structures/image-source-adapter.html) class is an abstract class representing an adapter for image sources, providing a framework for fetching, buffering, and managing images from various sources. It serves as the input for the [`CaptureVisionRouter`]({{ site.dcv_android_api }}capture-vision-router/capture-vision-router.html). You can either use the typical implementations of [`ImageSourceAdapter`]({{ site.dcv_android_api }}core/basic-structures/image-source-adapter.html) or implement your own.

Class [`CameraEnhancer`]({{ site.dce_android_api }}primary-api/camera-enhancer.html) is one of the typical implementations of [`ImageSourceAdapter`]({{ site.dcv_android_api }}core/basic-structures/image-source-adapter.html). It is a class that not only implements the video frame obtaining APIs but also enable you to improve the video quality by adjusting the camera settings.

### Captured Result Receiver

To receive the results of video streaming boundary detecting or document normalizing, you need to implement the [`CapturedResultReceiver`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html) with [`onDetectedQuadsReceived`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#ondetectedquadsreceived) or [`onNormalizedImagesReceived`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#onnormalizedimagesreceived).

Boundary detection related APIs:

- [`onDetectedQuadsReceived`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#ondetectedquadsreceived): The callback method for you to receive the boundary detetction results with a [`DetectedQuadsResult`](detected-quads-result.md) object.
- [`DetectedQuadsResult`](detected-quads-result.md): An object that contains all the [`DetectedQuadResultItem`](detected-quad-result-item.md) that obtained from a video frame.
- [`DetectedQuadResultItem`](detected-quad-result-item.md): The basic item that represents a single detected boundary as an quadrilateral with additional information.

Document Normalization related APIs:

- [`onNormalizedImagesReceived`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#onnormalizedimagesreceived): The callback method for you to receive the normalized image results with a [`NormalizedImagesResult`](normalized-images-result.md) object.
- [`NormalizedImagesResult`](normalized-images-result.md): An object that contains all the [`NormalizedImageResultItem`](normalized-image-result-item.md) that obtained from a video frame.
- [`NormalizedImageResultItem`](normalized-image-result-item.md): The basic item that represents a single normalized image with the image data and other information.

### Camera View

[`CameraView`]({{ site.dce_android_api }}auxiliary-api/dcecameraview.html) is a view class that design for visualizing the real time video streaming and the boundary detection result. If the [`CameraEnhancer`]({{ site.dce_android_api }}primary-api/camera-enhancer.html) is set as the input of your CVR, the detected boundaries will be highlighted automatically on the [`CameraView`]({{ site.dce_android_api }}auxiliary-api/dcecameraview.html).
