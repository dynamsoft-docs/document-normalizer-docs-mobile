---
layout: default-layout
title: DetectedQuadsResult - Dynamsoft Document Normalizer Android SDK API Reference
description: The class DetectedQuadsResult represents a captured result whose type is detected quads, which contains an array of DetectedQuadResultItems and the rotation transformation matrix of the original image relative to the rotated image.
keywords: detected quads result, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DetectedQuadsResult

The `DetectedQuadsResult` class represents a collection of [`DetectedQuadResultItems`](detected-quad-result-item.md), the basic unit of a detected quad result.

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class DetectedQuadsResult
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getItems`](#getitems) | An array of [`DetectedQuadResultItem`](./detected-quad-result-item.md), which are the detected quadrilateral items. |
| [`getRotationTransformMatrix`](#getrotationtransformmatrix) | The rotation transformation matrix of the original image relative to the rotated image. |
| [`getOriginalImageHashId`](#getoriginalimagehashid) | The hash id of the original image. You can use this ID to get the original image via `IntermediateResultManager` class. |
| [`getOriginalImageTag`](#getoriginalimagetag) | The tag of the original image, from which you get the detected quads result. |

### getItems

Returns an array of [`DetectedQuadResultItem`](./detected-quad-result-item.md), which represents the basic unit of the captured result, in this case, a detected quadrilateral.

```java
DetectedQuadResultItem[] getItems();
```

**Return Value**

The array of the detected quadrilateral items.

### getRotationTransformMatrix

Returns the rotation transformation matrix of the original image relative to the rotated image. Please see [Matrix](https://developer.android.com/reference/android/opengl/Matrix){:target="_blank"} for more info.

```java
Matrix getRotationTransformMatrix();
```

**Return Value**

The rotation transformation matrix of the original image relative to the rotated image.

### getOriginalImageHashId

Returns the hash ID of the original image. You can use this ID to get the original image via [`IntermediateResultManager`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-manager.html) class.

```java
String getOriginalImageHashId();
```

### getOriginalImageTag

Returns the [`ImageTag`]({{ site.dcv_android_api }}core/basic-structures/image-tag.html) of the original image, which contains various information about the image.

```java
ImageTag getOriginalImageTag();
```

**Return Value**

The tag of the original image.

**See Also**

* [ImageTag]({{ site.dcv_android_api }}core/basic-structures/image-tag.html)
