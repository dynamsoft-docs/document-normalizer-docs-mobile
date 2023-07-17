---
layout: default-layout
Title: NormalizedImageResultItem - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class NormalizedImageResultItem of Dynamsoft Document Normalizer module represents a captured result item whose type is a normalized image. It stores the normalized image information.
Keywords: normalized image result item, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# NormalizedImageResultItem

The `NormalizedImageResultItem` class represents a captured result item whose type is a normalized image. It stores the normalized image information.

## Definition

*Assembly:* package com.dynamsoft.ddn

```java
class NormalizedImageResultItem extends CapturedResultItem
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`getImageData`](#getimagedata) | *ImageData \** | Get an `ImageData` object as the image data of a normalized image. |
| [`getLocation`](#getlocation) | *Quadrilateral \** | The quadrilateral from which you get the normalized image result item. |

### getImageData

Get an `ImageData` object as the image data of a normalized image.

```java
ImageData getImageData();
```

### getLocation

Get the quadrilateral from which you get the normalized image result item.

```java
Quadrilateral getLocation();
```
