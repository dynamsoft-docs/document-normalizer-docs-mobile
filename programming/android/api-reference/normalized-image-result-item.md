---
layout: default-layout
title: NormalizedImageResultItem - Dynamsoft Document Normalizer Android SDK API Reference
description: The class NormalizedImageResultItem represents a captured result item whose type is a normalized image. It stores the normalized image information.
keywords: normalized image result item, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# NormalizedImageResultItem

The `NormalizedImageResultItem` class is an extension of [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html) that represents a normalized image. This is the most basic unit of the normalized image result, one of the captured result types that the Capture Vision Router can output. 

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class NormalizedImageResultItem extends CapturedResultItem
```

## Methods Summary

| Methods | Description |
| ---------- | ----------- |
| [`getImageData`](#getimagedata) | Gets an `ImageData` object as the normalized image. |
| [`getLocation`](#getlocation) | The quadrilateral from which you get the normalized image result item. |

### getImageData

Returns an [`ImageData`]({{ site.dcv_android_api }}core/basic-structures/image-data.html) object for the normalized image.

```java
ImageData getImageData();
```

**Return Value**

The `ImageData` object as the normalized image.

### getLocation

Returns the [Quadrilateral]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html) that represents the location of the normalized image within the original image or frame.

```java
Quadrilateral getLocation();
```

**Return Value**

The quadrilateral from which you get the normalized image result item.
