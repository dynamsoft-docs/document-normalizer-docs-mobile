---
layout: default-layout
title: DetectedQuadElement - Dynamsoft Document Normalizer module Android Edition API Reference
description: The class DetectedQuadElement represents a detected quadrilateral element, which is an intermediate result in the document scanning process.
keywords: detected quad, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DetectedQuadElement

The `DetectedQuadElement` class represents a detected quadrilateral element, which is an intermediate result in the document scanning process. It is a subclass of `RegionObjectElement`.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class DetectedQuadElement extends RegionObjectElement
```

## Methods

| Methods | Description |
| ------- | ----------- |
| [`getConfidenceAsDocumentBoundary`](#getconfidenceasdocumentboundary) | Returns the confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document. |

The following methods are inherited from class [`RegionObjectElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-android.md -%}

### getConfidenceAsDocumentBoundary

Returns the confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document.

```java
int getConfidenceAsDocumentBoundary();
```

**Return Value**

The confidence as document boundary of current object.
