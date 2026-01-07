---
layout: default-layout
title: ProcessedDocumentResult - Dynamsoft Document Normalizer MAUI SDK API Reference
description: The class ProcessedDocumentResult represents a collection of captured result items whose types are detected boundaries, deskew images or enhanced images.
keywords: detected boundaries, deskew images, enhanced images, csharp, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# ProcessedDocumentResult

The class `ProcessedDocumentResult` represents a collection of captured result items whose types are detected boundaries, deskew images or enhanced images.

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftCaptureVisionBundle.aar

```csharp
class ProcessedDocumentResult : CapturedResultBase
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`DeskewedImageResultItems`](#deskewedimageresultitems) | Represents the deskew images with an array of [`DeskewedImageResultItem`](deskewed-image-result-item.md). |
| [`DetectedQuadResultItems`](#detectedquadresultitems) | Represents the detected boundaries with an array of [`DetectedImageResultItem`](detected-image-result-item.md). |
| [`EnhancedImageResultItems`](#enhancedimageresultitems) | Represents the enhanced images with an array of [`EnhancedImageResultItem`](enhanced-image-result-item.md). |

The following properties are inherited from [`CapturedResultBase`]({{ site.dcv_maui_api }}core/captured-result-base.html):

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`OriginalImageHashId`]({{ site.dcv_maui_api }}core/captured-result-base.html#originalimagehashid) | *string* | Represents the hash id of the original image. |
| [`RotationTransformMatrix`]({{ site.dcv_maui_api }}core/captured-result-base.html#rotationtransformmatrix) | *Matrix* | Represents the rotation transformation matrix of the original image relative to the rotated image. |
| [`ErrorCode`]({{ site.dcv_maui_api }}core/captured-result-base.html#errorcode) | *int* | Represents the error code of this result. |
| [`ErrorMessage`]({{ site.dcv_maui_api }}core/captured-result-base.html#errormessage) | *string* | Represents the error message of this result. |

### DeskewedImageResultItems

Represents an array of [`DeskewedImageResultItem`](deskewed-image-result-item.md) objects, where each `DeskewedImageResultItem` represents a single deskewed image.

```csharp
DeskewedImageResultItem[]? DeskewedImageResultItems { get; }
```

### DetectedQuadResultItems

Represents an array of [`DetectedQuadResultItem`](detected-quad-result-item.md) objects, where each `DetectedQuadResultItem` represents a single detected boundary.

```csharp
DetectedQuadResultItem[]? DetectedQuadResultItems { get; }
```

### EnhancedImageResultItems

Represents an array of [`EnhancedImageResultItem`](enhanced-image-result-item.md) objects, where each `EnhancedImageResultItem` represents a single enhnanced image.

```csharp
EnhancedImageResultItem[]? EnhancedImageResultItems { get; }
```
