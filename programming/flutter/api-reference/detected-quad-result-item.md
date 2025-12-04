---
layout: default-layout
title: DetectedQuadResultItem - Dynamsoft Capture Vision Flutter SDK API Reference
description: The class DetectedQuadResultItem represents a captured result item whose type is detected quads, which contains the location and confidence as a document boundary.
keywords: detected quads, dart
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DetectedQuadResultItem

The `DetectedQuadResultItem` class is an extension of the [`CapturedResultItem`]({{ site.dcv_flutter_api }}core/captured-result-item.html) that represents a detected quadrilateral. This is the most basic unit of a detected quadrilateral, one of the captured result types that the Capture Vision Router can output.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class DetectedQuadResultItem extends CapturedResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`location`](#location) | *Quadrilateral* | A Quadrilateral object as the location of current object. |
| [`confidenceAsDocumentBoundary`](#confidenceasdocumentboundary) | *int* | The confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document. |
| [`crossVerificationStatus`](#crossverificationstatus) | *EnumCrossVerificationStatus* | The cross verification status of the result item. |

The following methods are inherited from [`CapturedResultItem`]({{ site.dcv_flutter_api }}core/captured-result-item.html).

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`targetROIDefName`]({{ site.dcv_flutter_api }}core/captured-result-item.html#targetroidefname) | *String* | The name of the target region of interest (ROI) where the captured result was found. |
| [`taskName`]({{ site.dcv_flutter_api }}core/captured-result-item.html#taskname) | *String* | The name of the recognition task that produced the CapturedResultItem. |
| [`type`]({{ site.dcv_flutter_api }}core/captured-result-item.html#type) | [*EnumCapturedResultItemType*]({{ site.dcv_flutter_api }}core/enum/captured-result-item-type.html) | The type of the captured result item. |

### location

Returns a [Quadrilateral]({{ site.dcv_flutter_api }}core/quadrilateral.html) object that represents the location of the detected quadrilateral within the image or frame.

```dart
Quadrilateral location;
```

### confidenceAsDocumentBoundary

Returns the confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document.

```dart
int confidenceAsDocumentBoundary;
```

### crossVerificationStatus

Returns the cross verification status of the result. The cross verification status determines whether the result item is approved by the multi-frame cross verification mechanism. If approved, the cross verification status is `CVS_PASSED`. Otherwise, it is `CVS_FAILED`.

```dart
EnumCrossVerificationStatus crossVerificationStatus;
```
