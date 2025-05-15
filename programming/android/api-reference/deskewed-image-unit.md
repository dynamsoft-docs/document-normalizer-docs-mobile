---
layout: default-layout
title: DeskewedImagesUnit - Dynamsoft Document Normalizer Android SDK API Reference
description: The class DeskewedImagesUnit represents an intermediate result unit whose type is deskewed images.
keywords: deskewed images, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DeskewedImagesUnit

The `DeskewedImagesUnit` class represents an intermediate result unit whose type is deskewed images.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftCaptureVisionBundle.aar

```java
class DeskewedImagesUnit extends IntermediateResultUnit
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getDeskewedImage`](#getdeskewedimage) | Gets the deskewed image of type [`DeskewedImageElement`](deskewed-image-element.md). |
| [`setDeskewedImage`](#setdeskewedimage) | Sets the deskewed image with a [`DeskewedImageElement`](deskewed-image-element.md) object |

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getDeskewedImage

Gets a deskewed image.

```java
DeskewedImageElement getDeskewedImage();
```

**Return Value**

A [`DeskewedImageElement`](deskewed-image-element.md) object that represents the deskewed image.

### setDeskewedImage

Sets a [`DeskewedImageElement`](deskewed-image-element.md) as the deskewed image.

```java
void setDeskewedImage(DeskewedImageElement element, Matrix matrixToOriginalImage);
```

**Parameters**

`[in] element`: The deskewed image to be set.

`[in] matrixToOriginalImage`: The matrix to the original image.
