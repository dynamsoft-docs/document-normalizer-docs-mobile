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

The `DetectedQuadsResult` class represents a captured result whose type is detected quads, which contains an array of `DetectedQuadResultItem` and the rotation transformation matrix of the original image relative to the rotated image.

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class DetectedQuadsResult
```

## Methods Summary

| Methods | Description |
| ---------- | ----------- |
| [`getItems`](#getitems) | An array of [`DetectedQuadResultItem`](./detected-quad-result-item.md), which are the detected quadrilateral items. |
| [`getRotationTransformMatrix`](#getrotationtransformmatrix) | The rotation transformation matrix of the original image relative to the rotated image. |
| [`getOriginalImageHashId`](#getoriginalimagehashid) | The hash id of the original image. You can use this ID to get the original image via `IntermediateResultManager` class. |
| [`getOriginalImageTag`](#getoriginalimagetag) | The tag of the original image, from which you get the detected quads result. |

### getItems

An array of [`DetectedQuadResultItem`](./detected-quad-result-item.md), which are the detected quadrilateral items.

```java
DetectedQuadResultItem[] getItems();
```

**Return Value**

The array of the detected quadrilateral items.

### getRotationTransformMatrix

The rotation transformation matrix of the original image relative to the rotated image.

```java
Matrix getRotationTransformMatrix();
```

**Return Value**

The rotation transformation matrix of the original image relative to the rotated image.

### getOriginalImageHashId

The hash id of the original image. You can use this ID to get the original image via `IntermediateResultManager` class.

```java
String getOriginalImageHashId();
```

**Return Value**

The hash id of the original image.

### getOriginalImageTag

The tag of the original image.

```java
ImageTag getOriginalImageTag();
```

**Return Value**

The tag of the original image.

**See Also**

* [ImageTag]({{ site.dcv_android_api }}core/basic-structures/image-tag.html)
