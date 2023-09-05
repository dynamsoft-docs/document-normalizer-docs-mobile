---
layout: default-layout
title: DetectedQuadResultItem - Dynamsoft Document Normalizer Android SDK API Reference
description: The class DetectedQuadResultItem represents a captured result item whose type is detected quads, which contains the location and confidence as a document boundary.
keywords: detected quads, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DetectedQuadResultItem

The `DetectedQuadResultItem` class represents a captured result item whose type is detected quad, which contains the location and confidence as a document boundary.

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class DetectedQuadResultItem extends CapturedResultItem
```

## Methods Summary

| Methods | Description |
| ------- | ----------- |
| [`getLocation`](#getlocation) | Get a Quadrilateral object as the location of current object. |
| [`getConfidenceAsDocumentBoundary`](#getconfidenceasdocumentboundary) | Get the confidence of current object as a document boundary. |

### getLocation

Get a Quadrilateral object as the location of current object.

```java
Quadrilateral getLocation();
```

**Return Value**

The location of current object.

### getConfidenceAsDocumentBoundary

Get the confidence of current object as a document boundary.

```java
int getConfidenceAsDocumentBoundary();
```

**Return Value**

The confidence as document boundary of current object.
