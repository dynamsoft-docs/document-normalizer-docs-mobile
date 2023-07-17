---
layout: default-layout
Title: NormalizedImagesResult - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class NormalizedImagesResult of Dynamsoft Document Normalizer module represents a collection of captured result items whose type are normalized images.
Keywords: normalized images, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# NormalizedImagesResult

The `NormalizedImagesResult` class represents a collection of captured result items whose type are normalized images.

## Definition

*Assembly:* package com.dynamsoft.ddn

```java
class NormalizedImagesResult
```

## Attributes

| Attributes | Description |
| ---------- | ----------- |
| [`items`](#getitems) | Get an array of NormalizedImageResultItem. Each NormalizedImageResultItem is a result object of a single normalized image. |
| [`rotationTransformMatrix`](#getrotationtransformmatrix) | Get the rotation transformation matrix of the original image relative to the rotated image. |
| [`sourceImageHashId`](#getsourceimagehashid) | Get the hash id of the source image. You can use this ID to get the source image via IntermediateResultManager class. |
| [`sourceImageTag`](#getsourceimagetag) | Get the tag of the original image, from which you get the normalized image. |

### getItems

Get an array of `NormalizedImageResultItem`. Each `NormalizedImageResultItem` is a result object of a single normalized image.

```java
NormalizedImageResultItem[] getItems();
```

### getRotationTransformMatrix

Get the rotation transformation matrix of the original image relative to the rotated image.

```java
Matrix getRotationTransformMatrix();
```

### getSourceImageHashId

Get the hash id of the source image. You can use this ID to get the source image via `IntermediateResultManager` class.

```java
String getSourceImageHashId();
```

### getSourceImageTag

Get the tag of the original image, from which you get the normalized image.

```java
ImageTag getSourceImageTag();
```
