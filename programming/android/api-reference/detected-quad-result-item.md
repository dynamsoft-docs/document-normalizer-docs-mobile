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

*Assembly:* DynamsoftCaptureVisionBundle.aar

```java
class DetectedQuadResultItem extends CapturedResultItem
```

## Methods

| Methods | Description |
| ------- | ----------- |
| [`getLocation`](#getlocation) | Returns a Quadrilateral object as the location of current object. |
| [`getConfidenceAsDocumentBoundary`](#getconfidenceasdocumentboundary) | Returns the confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document. |
| [`getCrossVerificationStatus`](#getcrossverificationstatus) | Returns the cross verification status of the result item. |

The following methods are inherited from [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html).

| Method | Description |
| ------ | ----------- |
| [`getType`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#gettype) | Returns the type of the captured result item, indicating what kind of data it represents. |
| [`getReferencedItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#getreferenceditem) | Returns a property of type `CapturedResultItem` that represents a reference to another captured result item. |
| [`getTargetROIDefName`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#gettargetroidefname) | Returns the name of the [`TargetROIDef`]({{ site.dcv_parameters_reference }}target-roi-def/){:target="_blank"} object which includes a task that generated the result. |
| [`getTaskName`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#gettaskname) | Returns the name of the task that generated the result. |

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

### getCrossVerificationStatus

Returns the cross verification status of the result. The cross verification status determines whether the result item is approved by the multi-frame cross verification mechanism. If approved, the cross verification status is `CVS_PASSED`. Otherwise, it is `CVS_FAILED`.

```java
EnumCrossVerificationStatus getCrossVerificationStatus();
```

**Return Value**

Returns the cross verification status of type [`EnumCrossVerificationStatus`]({{ site.dcv_enumerations }}core/cross-verification-status.html).
