---
layout: default-layout
title: NormalizedImagesUnit - Dynamsoft Document Normalizer Android SDK API Reference
description: The class NormalizedImagesUnit represents an intermediate result unit whose type is normalized images.
keywords: normalized images, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# NormalizedImagesUnit

The `NormalizedImagesUnit` class represents an intermediate result unit whose type is normalized images.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class NormalizedImagesUnit extends IntermediateResultUnit
```

## Methods Summary

| Methods | Description |
| ---------- | ----------- |
| [`getNormalizedImages`](#getnormalizedimages) | Gets an array of [`NormalizedImageElement`](normalized-image-element.md). |
| [`getCount`](#getcount) | Gets the number of normalized images. |
| [`getNormalizedImage`](#getnormalizedimage) | Gets a normalized image. |
| [`removeAllNormalizedImages`](#removeallnormalizedimages) | Removes all normalized images. |
| [`setNormalizedImage`](#setnormalizedimage) | Sets a normalized image. |

### getNormalizedImages

Gets an array of [`NormalizedImageElement`](normalized-image-element.md).

```java
NormalizedImageElement[] getNormalizedImages();
```

**Return Value**

The array of [`NormalizedImageElement`](normalized-image-element.md).

### getCount

Gets the number of normalized images.

```java
int getCount();
```

**Return Value**

The number of normalized images.

### getNormalizedImage

Gets a normalized image.

```java
NormalizedImageElement getNormalizedImage(int index);
```

**Return Value**

A [`NormalizedImageElement`](normalized-image-element.md) object that represents the normalized image.

### removeAllNormalizedImages

Removes all normalized images.

```java
void removeAllNormalizedImages();
```

### setNormalizedImage

Sets a [`NormalizedImageElement`](normalized-image-element.md) as the normalized image.

```java
int setNormalizedImage(NormalizedImageElement element, Matrix matrixToOriginalImage);
```

**Parameters**

`[in] element`: The normalized image to be set.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. otherwise, returns 0.
