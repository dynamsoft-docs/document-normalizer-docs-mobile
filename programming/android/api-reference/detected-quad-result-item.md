---
layout: default-layout
Title: DetectedQuadResultItem - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class DetectedQuadResultItem of Dynamsoft Document Normalizer module represents a captured result whose type is detected quads, which contains the location and confidence as a document boundary.
Keywords: detected quads, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DetectedQuadResultItem

The `DetectedQuadResultItem` class represents a captured result whose type is detected quads, which contains the location and confidence as a document boundary.

## Definition

*Assembly:* package com.dynamsoft.ddn

```java
class DetectedQuadResultItem extends CapturedResultItem
```

## Attributes

| Methods | Description |
| ------- | ----------- |
| [`getLocation`](#getlocation) | Get a Quadrilateral object as the location of current object. |
| [`getConfidenceAsDocumentBoundary`](#getconfidenceasdocumentboundary) | Get the confidence of current object as a document boundary. |

### getLocation

Get a Quadrilateral object as the location of current object.

```java
Quadrilateral getLocation();
```

### getConfidenceAsDocumentBoundary

Get the confidence of current object as a document boundary.

```java
int getConfidenceAsDocumentBoundary();
```
