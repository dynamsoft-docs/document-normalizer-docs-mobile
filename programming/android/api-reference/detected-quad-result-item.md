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

The `DetectedQuadResultItem` class is an extension of the [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html) that represents a detected quadrilateral. This is the most basic unit of a detected quadrilateral, one of the captured result types that the Capture Vision Router can output.

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
| [`getConfidenceAsDocumentBoundary`](#getconfidenceasdocumentboundary) | Returns the confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document. |

### getLocation

Returns a [Quadrilateral]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html) object that represents the location of the detected quadrilateral within the image or frame.

```java
Quadrilateral getLocation();
```

**Return Value**

The location of current object.

### getConfidenceAsDocumentBoundary

Returns the confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document.

```java
int getConfidenceAsDocumentBoundary();
```

**Return Value**

The confidence as document boundary of current object.
