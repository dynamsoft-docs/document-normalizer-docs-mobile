---
layout: default-layout
title: ProcessedDocumentResult - Dynamsoft Capture Vision Flutter SDK API Reference
description: The class ProcessedDocumentResult represents a collection of captured result items whose types are detected boundaries, deskew images or enhanced images.
keywords: detected boundaries, deskew images, enhanced images, dart
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# ProcessedDocumentResult

The class `ProcessedDocumentResult` represents a collection of captured result items whose types are detected boundaries, deskew images or enhanced images.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class ProcessedDocumentResult extends CapturedResultBase
```

## Properties

| Property | Types | Description |
| -------- | ----- | ----------- |
| [`DeskewedImageResultItems`](#deskewedimageresultitems) | *List<DeskewedImageResultItem>* | An array of [`DeskewedImageResultItem`](deskewed-image-result-item.md) objects, where each `DeskewedImageResultItem` represents a single deskewed image. |
| [`DetectedQuadResultItems`](#detectedquadresultitems) | *List<DetectedQuadResultItem>* | An array of [`DetectedQuadResultItem`](detected-quad-result-item.md) objects, where each `DetectedQuadResultItem` represents a single detected boundary. |
| [`EnhancedImageResultItems`](#enhancedimageresultitems) | *List<EnhancedImageResultItem>* | A array of [`EnhancedImageResultItem`](enhanced-image-result-item.md) objects, where each `EnhancedImageResultItem` represents a single enhnanced image. |

The following properties are inherited from [`CapturedResultBase`]({{ site.dcv_flutter_api }}core/captured-result-base.html):

| Property | Types | Description |
| -------- | ----- | ----------- |
| [`originalImageHashId`](#originalimagehashid) | *String* | The hash id of the original image. |
| [`rotationTransformMatrix`](#rotationtransformmatrix) | *Matrix4* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`errorCode`](#errorcode) | *int* | The error code of this result. |
| [`errorMessage`](#errormessage) | *String* | The error message of this result. |

### deskewedImageResultItems

An array of [`DeskewedImageResultItem`](deskewed-image-result-item.md) objects, where each `DeskewedImageResultItem` represents a single deskewed image.

```dart
List<DeskewedImageResultItem>? deskewedImageResultItems;
```

### detectedQuadResultItems

An array of [`DetectedQuadResultItem`](detected-quad-result-item.md) objects, where each `DetectedQuadResultItem` represents a single detected boundary.

```dart
List<DetectedQuadResultItem>? detectedQuadResultItems;
```

### enhancedImageResultItems

A array of [`EnhancedImageResultItem`](enhanced-image-result-item.md) objects, where each `EnhancedImageResultItem` represents a single enhnanced image.

```dart
List<EnhancedImageResultItem>? enhancedImageResultItems;
```
