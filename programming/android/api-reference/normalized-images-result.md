---
layout: default-layout
title: NormalizedImagesResult - Dynamsoft Document Normalizer Android SDK API Reference
description: The class NormalizedImagesResult represents a collection of captured result items whose type are normalized images.
keywords: normalized images, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# NormalizedImagesResult

The `NormalizedImagesResult` class represents a collection of [`NormalizedImageResultItem`](normalized-image-result-item.md), the basic unit of a normalized image result.

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class NormalizedImagesResult
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getItems`](#getitems) | Gets an array of NormalizedImageResultItem. Each NormalizedImageResultItem is a result object of a single normalized image. |
| [`getRotationTransformMatrix`](#getrotationtransformmatrix) | Gets the rotation transformation matrix of the original image relative to the rotated image. |
| [`getOriginalImageHashId`](#getoriginalimagehashid) | Gets the hash id of the original image. You can use this ID to get the original image via IntermediateResultManager class. |
| [`getOriginalImageTag`](#getoriginalimagetag) | Gets the tag of the original image. |

### getItems

Returns an array of [`NormalizedImageResultItem`](normalized-image-result-item.md) objects, where each `NormalizedImageResultItem` represents a single normalized image.

```java
NormalizedImageResultItem[] getItems();
```

**Return Value**

The array of the normalized image result items.

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

**Return Value**

The hash id of the original image.

### getOriginalImageTag

Returns the [`ImageTag`]({{ site.dcv_android_api }}core/basic-structures/image-tag.html) of the original image, which contains various information about the image.

```java
ImageTag getOriginalImageTag();
```

**Return Value**

The tag of the original image.
