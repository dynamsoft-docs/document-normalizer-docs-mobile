---
layout: default-layout
title: NormalizedImageResultItem - Dynamsoft Capture Vision MAUI SDK API Reference
description: The class NormalizedImageResultItem represents a captured result item whose type is a normalized image. It stores the normalized image information.
keywords: normalized image result item, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# NormalizedImageResultItem

The `NormalizedImageResultItem` class is an extension of [`CapturedResultItem`]({{ site.dcv_maui_api }}core/captured-result-item.html) that represents a normalized image. This is the most basic unit of the normalized image result, one of the captured result types that the Capture Vision Router can output. 

## Definition

*Namespace:* Dynamsoft.DocumentNormalizer.Maui

*Assembly:* Dynamsoft.DocumentNormalizer.Maui

```csharp
class NormalizedImageResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`ImageData`](#imagedata) | *ImageData* | An `ImageData` object as the normalized image. |
| [`Location`](#location) | *Quadrilateral* | The quadrilateral from which you get the normalized image result item. |

The following properties are inherited from [`CapturedResultItem`]({{ site.dcv_maui_api }}core/captured-result-item.html).

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Type`]({{ site.dcv_maui_api }}core/captured-result-item.html#type) | *[EnumCapturedResultItemType]({{ site.dcv_maui_api }}core/enum/captured-result-item-type.html)* | Get the type of the captured result item, indicating what kind of data it represents. |
| [`TargetROIDefName`]({{ site.dcv_maui_api }}core/captured-result-item.html#targetroidefname) | *string* | The name of the [`TargetROIDef`]({{ site.dcv_parameters_reference }}target-roi-def/){:target="_blank"} object which includes a task that generated the result. |
| [`TaskName`]({{ site.dcv_maui_api }}core/captured-result-item.html#taskname) | *string* | The name of the task that generated the result. |

### ImageData

An [`ImageData`]({{ site.dcv_maui_api }}core/image-data.html) object for the normalized image.

```csharp
ImageData ImageData { get; }
```

### Location

The [Quadrilateral]({{ site.dcv_maui_api }}core/quadrilateral.html) that represents the location of the normalized image within the original image or frame.

```csharp
Quadrilateral Location { get; }
```
