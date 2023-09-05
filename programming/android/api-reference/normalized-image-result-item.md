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

The `NormalizedImageResultItem` class represents a captured result item whose type is a normalized image. It stores the normalized image information.

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

Gets an `ImageData` object as the normalized image.

```java
ImageData getImageData();
```

**Return Value**

The `ImageData` object as the normalized image.

### getLocation

Gets the quadrilateral from which you get the normalized image result item.

```java
Quadrilateral getLocation();
```

**Return Value**

The quadrilateral from which you get the normalized image result item.
