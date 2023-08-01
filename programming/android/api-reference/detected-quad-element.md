---
layout: default-layout
Title: DetectedQuadElement - Dynamsoft Document Normalizer module Android Edition API Reference
Description: The class DetectedQuadElement represents a detected quadrilateral element, which is an intermediate result in the document scanning process.
Keywords: detected quad, java, kotlin
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

## Methods Summary

| Methods | Description |
| ------- | ----------- |
| [`getConfidenceAsDocumentBoundary`](#getconfidenceasdocumentboundary) | Get the confidence of the quadrilateral to be a document boundary. |

## getConfidenceAsDocumentBoundary

Get the confidence of the quadrilateral to be a document boundary.

```java
int getConfidenceAsDocumentBoundary();
```

**Return Value**

The confidence as document boundary of current object.
