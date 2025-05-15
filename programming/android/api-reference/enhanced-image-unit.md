---
layout: default-layout
title: EnhancedImagesUnit - Dynamsoft Document Normalizer Android SDK API Reference
description: The class EnhancedImagesUnit represents an intermediate result unit whose type is enhanced images.
keywords: enhanced images, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# EnhancedImagesUnit

The `EnhancedImagesUnit` class represents an intermediate result unit whose type is enhanced images.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftCaptureVisionBundle.aar

```java
class EnhancedImagesUnit extends IntermediateResultUnit
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getEnhancedImage`](#getenhancedimage) | Gets the enhanced image of type [`EnhancedImageElement`](enhanced-image-element.md). |
| [`setEnhancedImage`](#setenhancedimage) | Sets the enhanced image with a [`EnhancedImageElement`](enhanced-image-element.md) object |

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getEnhancedImage

Gets a enhanced image.

```java
EnhancedImageElement getEnhancedImage();
```

**Return Value**

A [`EnhancedImageElement`](enhanced-image-element.md) object that represents the enhanced image.

### setEnhancedImage

Sets a [`EnhancedImageElement`](enhanced-image-element.md) as the enhanced image.

```java
void setEnhancedImage(EnhancedImageElement element);
```

**Parameters**

`[in] element`: The enhanced image to be set.
