---
layout: default-layout
title: NormalizedImagesUnit - Dynamsoft Document Normalizer Android SDK API Reference
description: The class NormalizedImagesUnit represents an intermediate result unit whose type is normalized images.
keywords: normalized images, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# NormalizedImagesUnit

The `NormalizedImagesUnit` class represents an intermediate result unit whose type is normalized images.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class NormalizedImagesUnit extends IntermediateResultUnit
```

## Methods Summary

| Methods | Description |
| ---------- | ----------- |
| [`getNormalizedImages`](#getnormalizedimages) | Gets an array of [`NormalizedImageElement`](./normalized-image-element.md). |

### getNormalizedImages

Gets an array of [`NormalizedImageElement`](./normalized-image-element.md).

```java
NormalizedImageElement[] getNormalizedImages();
```

**Return Value**

The array of [`NormalizedImageElement`](./normalized-image-element.md).
