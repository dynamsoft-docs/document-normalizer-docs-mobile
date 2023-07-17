---
layout: default-layout
Title: DetectedQuadsUnit - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class DetectedQuadsUnit of Dynamsoft Document Normalizer module represents an intermediate result unit whose type is detected quads. It is inherited from the IntermediateResultUnit class.
Keywords: detected quads, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DetectedQuadsUnit

The `DetectedQuadsUnit` class represents an intermediate result unit whose type is detected quads. It is inherited from the `IntermediateResultUnit` class.

## Definition

*Assembly:* package com.dynamsoft.ddn

```java
class DetectedQuadsUnit extends IntermediateResultUnit
```

## Attributes

| Attributes | Description |
| ---------- | ----------- |
| [`getDetectedQuads`](#getdetectedquads) | Get an array of `DetectedQuadElement`. Each `DetectedQuadElement` contains the information of a single detected quadrilateral. |

### getDetectedQuads

Get an array of `DetectedQuadElement`. Each `DetectedQuadElement` contains the information of a single detected quadrilateral.

```java
DetectedQuadElement[] getDetectedQuads()
```
