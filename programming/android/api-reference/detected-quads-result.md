---
layout: default-layout
Title: DetectedQuadsResult - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class DetectedQuadsResult of Dynamsoft Document Normalizer module represents a captured result whose type is detected quads, which contains an array of DetectedQuadResultItems and the rotation transformation matrix of the original image relative to the rotated image.
Keywords: detected quads result, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DetectedQuadsResult

The `DetectedQuadsResult` class represents a captured result whose type is detected quads, which contains an array of `DetectedQuadResultItems` and the rotation transformation matrix of the original image relative to the rotated image.

## Definition

*Assembly:* package com.dynamsoft.ddn

```java
class DetectedQuadsResult
```

## Attributes

| Attributes | Description |
| ---------- | ----------- |
| [`getItems`](#getitems) | An array of `DetectedQuadResultItems`, which are the basic unit of the captured results. |
| [`getRotationTransformMatrix`](#getrotationtransformmatrix) | The rotation transformation matrix of the original image relative to the rotated image. |
| [`getSourceImageHashId`](#getsourceimagehashid) | The hash id of the source image. You can use this ID to get the source image via `IntermediateResultManager` class. |
| [`getSourceImageTag`](#getsourceimagetag) | The tag of the original image, from which you get the normalized image. |

### getItems

An array of `DetectedQuadResultItems`, which are the basic unit of the captured results.

```java
DetectedQuadResultItem[] getItems();
```

### getRotationTransformMatrix

The rotation transformation matrix of the original image relative to the rotated image.

```java
Matrix getRotationTransformMatrix();
```

### getSourceImageHashId

The hash id of the source image. You can use this ID to get the source image via `IntermediateResultManager` class.

```java
String getSourceImageHashId();
```

### getSourceImageTag

The tag of the original image, from which you get the normalized image.

```java
ImageTag getSourceImageTag();
```
