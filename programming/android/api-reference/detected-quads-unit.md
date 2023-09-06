---
layout: default-layout
title: DetectedQuadsUnit - Dynamsoft Document Normalizer Android SDK API Reference
description: The class DetectedQuadsUnit represents an intermediate result unit whose type is detected quads. It is inherited from the IntermediateResultUnit class.
keywords: detected quads, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DetectedQuadsUnit

The `DetectedQuadsUnit` class represents an intermediate result unit whose type is detected quads. It is inherited from the `IntermediateResultUnit` class.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class DetectedQuadsUnit extends IntermediateResultUnit
```

## Methods Summary

| Methods | Description |
| ---------- | ----------- |
| [`getDetectedQuads`](#getdetectedquads) | Gets an array of `DetectedQuadElement` objects, each containing the information of a single detected quadrilateral. |

### getDetectedQuads

Gets an array of `DetectedQuadElement` objects, each containing the information of a single detected quadrilateral.

```java
DetectedQuadElement[] getDetectedQuads()
```

**Return Value**

The array of [`DetectedQuadElement`](./detected-quad-element.md).
