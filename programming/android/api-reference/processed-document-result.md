---
layout: default-layout
title: ProcessedDocumentResult - Dynamsoft Document Normalizer Android SDK API Reference
description: The class ProcessedDocumentResult represents a collection of captured result items whose types are detected boundaries, deskew images or enhanced images.
keywords: detected boundaries, deskew images, enhanced images, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# ProcessedDocumentResult

The class `ProcessedDocumentResult` represents a collection of captured result items whose types are detected boundaries, deskew images or enhanced images.

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class ProcessedDocumentResult
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getDeskewedImageResultItems`](#getdeskewedimageresultitems) | Gets the deskew images with an array of [`DeskewedImageResultItem`](deskewed-image-result-item.md). |
| [`getDetectedQuadResultItems`](#getdetectedquadresultitems) | Gets the detected boundaries with an array of [`DetectedImageResultItem`](detected-image-result-item.md). |
| [`getEnhancedImageResultItems`](#getenhancedimageresultitems) | Gets the enhanced images with an array of [`EnhancedImageResultItem`](enhanced-image-result-item.md). |

The following methods are inherited from [`CapturedResultBase`]({{ site.dcv_android_api }}core/basic-structures/captured-result-base.html):

| Method | Description |
| ------ | ----------- |
| [`getOriginalImageHashId`]({{ site.dcv_android_api }}core/basic-structures/captured-result-base.html#getoriginalimagehashid) | Gets the hash id of the original image. |
| [`getOriginalImageTag`]({{ site.dcv_android_api }}core/basic-structures/captured-result-base.html#getoriginalimagetag) | Gets the [ImageTag](image-tag.md) of the original image. |
| [`getRotationTransformMatrix`]({{ site.dcv_android_api }}core/basic-structures/captured-result-base.html#getrotationtransformmatrix) | Gets the rotation transformation matrix of the original image relative to the rotated image. |
| [`getErrorCode`]({{ site.dcv_android_api }}core/basic-structures/captured-result-base.html#geterrorcode) | Gets the error code of this result. |
| [`getErrorMessage`]({{ site.dcv_android_api }}core/basic-structures/captured-result-base.html#geterrormessage) | Gets the error message of this result. |

### getDeskewedImageResultItems

Returns an array of [`DeskewedImageResultItem`](deskewed-image-result-item.md) objects, where each `DeskewedImageResultItem` represents a single deskewed image.

```java
DeskewedImageResultItem[] getDeskewedImageResultItems();
```

**Return Value**

The array of the deskewed image result items.

### getDetectedQuadResultItems

Returns an array of [`DetectedQuadResultItem`](detected-quad-result-item.md) objects, where each `DetectedQuadResultItem` represents a single detected boundary.

```java
DetectedQuadResultItem[] getDetectedQuadResultItems();
```

**Return Value**

The array of the detected quad result items.

### getEnhancedImageResultItems

Returns an array of [`EnhancedImageResultItem`](enhanced-image-result-item.md) objects, where each `EnhancedImageResultItem` represents a single enhnanced image.

```java
EnhancedImageResultItem[] getEnhancedImageResultItems();
```

**Return Value**

The array of the enhanced image result items.
