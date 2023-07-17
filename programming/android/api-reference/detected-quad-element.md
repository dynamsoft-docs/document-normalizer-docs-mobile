---
layout: default-layout
Title: DetectedQuadElement - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class DetectedQuadElement of Dynamsoft Document Normalizer module represents a detected quadrilateral element, which is an intermediate result in the document scanning process.
Keywords: detected quad, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DetectedQuadElement

The `DetectedQuadElement` class represents a detected quadrilateral element, which is an intermediate result in the document scanning process. It is a subclass of `RegionObjectElement`.

## Definition

*Assembly:* package com.dynamsoft.ddn

```java
class DetectedQuadElement extends RegionObjectElement
```

## Attributes

| Methods | Description |
| ------- | ----------- |
| [`getConfidenceAsDocumentBoundary`](#getconfidenceasdocumentboundary) | Get the confidence of the quadrilateral to be a document boundary. |

## getConfidenceAsDocumentBoundary

Get the confidence of the quadrilateral to be a document boundary.

```java
int getConfidenceAsDocumentBoundary();
```
