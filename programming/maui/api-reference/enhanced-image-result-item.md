---
layout: default-layout
title: EnhancedImageResultItem - Dynamsoft Document Normalizer MAUI SDK API Reference
description: The class EnhancedImageResultItem of DCV MAUI represents a captured result item whose type is a enhanced image. It stores the enhanced image information.
keywords: enhanced image result item, csharp, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# EnhancedImageResultItem

The `EnhancedImageResultItem` class is an extension of [`CapturedResultItem`]({{ site.dcv_maui_api }}core/basic-structures/captured-result-item.html) that represents a enhanced image. This is the most basic unit of the enhanced image result, one of the captured result types that the Capture Vision Router can output. 

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftCaptureVisionBundle.aar

```csharp
class EnhancedImageResultItem extends CapturedResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`ImageData`](#imagedata) | *ImageData* | Returns an `ImageData` object as the enhanced image. |
| [`OriginalToLocalMatrix`](#originaltolocalmatrix) | *Matrix* | Returns the transformation matrix from the original image coordinate system to the local coordinate system. |

The following properties are inherited from [`CapturedResultItem`]({{ site.dcv_maui_api }}core/captured-result-item.html).

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Type`]({{ site.dcv_maui_api }}core/captured-result-item.html#type) | *[EnumCapturedResultItemType]({{ site.dcv_maui_api }}core/enum/captured-result-item-type.html)* | Get the type of the captured result item, indicating what kind of data it represents. |
| [`TargetROIDefName`]({{ site.dcv_maui_api }}core/captured-result-item.html#targetroidefname) | *string* | Gets the name of the [`TargetROIDef`]({{ site.dcv_parameters_reference }}target-roi-def/) object which includes a task that generated the result. |
| [`TaskName`]({{ site.dcv_maui_api }}core/captured-result-item.html#taskname) | *string* | The name of the task that generated the result. |

### ImageData

Returns an [`ImageData`]({{ site.dcv_maui_api }}core/basic-structures/image-data.html) object for the enhanced image.

```csharp
ImageData ImageData { get; }
```

### OriginalToLocalMatrix

Returns the transformation matrix from the original image coordinate system to the local coordinate system.

```csharp
Matrix OriginalToLocalMatrix { get; }
```
