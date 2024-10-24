---
layout: default-layout
title: DetectedQuadResultItem - Dynamsoft Document Normalizer MAUI SDK API Reference
description: The class DetectedQuadResultItem of DCV MAUI represents a captured result item whose type is detected quads, which contains the location and confidence as a document boundary.
keywords: detected quads, MAUI
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DetectedQuadResultItem

The `DetectedQuadResultItem` class is an extension of the [`CapturedResultItem`]({{ site.dcv_maui_api }}core/captured-result-item.html) that represents a detected quadrilateral. This is the most basic unit of a detected quadrilateral, one of the captured result types that the Capture Vision Router can output.

## Definition

*Namespace:* Dynamsoft.DocumentNormalizer.Maui

*Assembly:* Dynamsoft.DocumentNormalizer.Maui

```csharp
class DetectedQuadResultItem : CapturedResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Location`](#location) | *Quadrilateral* | A Quadrilateral object as the location of current object. |
| [`ConfidenceAsDocumentBoundary`](#confidenceasdocumentboundary) | *int* | The confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document. |

The following properties are inherited from [`CapturedResultItem`]({{ site.dcv_maui_api }}core/captured-result-item.html).

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Type`]({{ site.dcv_maui_api }}core/captured-result-item.html#type) | *[EnumCapturedResultItemType]({{ site.dcv_maui_api }}core/enum/captured-result-item-type.html)* | Get the type of the captured result item, indicating what kind of data it represents. |
| [`TargetROIDefName`]({{ site.dcv_maui_api }}core/captured-result-item.html#targetroidefname) | *string* | Gets the name of the [`TargetROIDef`]({{ site.dcv_parameters_reference }}target-roi-def/) object which includes a task that generated the result. |
| [`TaskName`]({{ site.dcv_maui_api }}core/captured-result-item.html#taskname) | *string* | The name of the task that generated the result. |

### Location

A [Quadrilateral]({{ site.dcv_maui_api }}core/quadrilateral.html) object that represents the location of the detected quadrilateral within the image or frame.

```csharp
Quadrilateral Location { get; }
```

### ConfidenceAsDocumentBoundary

The confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document.

```csharp
int ConfidenceAsDocumentBoundary { get; }
```
