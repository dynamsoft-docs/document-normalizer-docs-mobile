---
layout: default-layout
Title: NormalizedImageElement - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class NormalizedImageElement of Dynamsoft Document Normalizer module represents an intermediate result whose type is normalized image, It is inherited from RegionObjectElement and contains image data of normalized result as additional parameter.
Keywords: normalized image element, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# NormalizedImageElement

The `NormalizedImageElement` class represents an intermediate result whose type is normalized image. It is inherited from `RegionObjectElement` and contains image data of normalized result as an additional parameter.

## Definition

*Assembly:* package com.dynamsoft.ddn

```java
class NormalizedImageElement extends RegionObjectElement
```

## Attributes

| Attributes | Description |
| ---------- | ----------- |
| [`getImageData`](#getimagedata) | Get an `ImageData` object as the image data of a normalized image. |

### getImageData

get an `ImageData` object as the image data of a normalized image.

```java
ImageData getImageData();
```
