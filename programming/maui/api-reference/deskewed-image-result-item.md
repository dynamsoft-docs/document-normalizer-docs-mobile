---
layout: default-layout
title: DeskewedImageResultItem - Dynamsoft Document Normalizer Android SDK API Reference
description: The class DeskewedImageResultItem represents a captured result item whose type is a deskewed image. It stores the deskewed image information.
keywords: deskewed image result item, csharp, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DeskewedImageResultItem

The `DeskewedImageResultItem` class is an extension of [`CapturedResultItem`]({{ site.dcv_maui_api }}core/basic-structures/captured-result-item.html) that represents a deskewed image. This is the most basic unit of the deskewed image result, one of the captured result types that the Capture Vision Router can output. 

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftCaptureVisionBundle.aar

```csharp
class DeskewedImageResultItem extends CapturedResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`ImageData`](#imagedata) | *ImageData* | Represents an `ImageData` object as the deskewed image. |
| [`SourceDeskewQuad`](#location) | *Quadrilateral* | Represents the quadrilateral from which you get the deskewed image result item. |
| [`CrossVerificationStatus`](#crossverificationstatus) | *EnumCrossVerificationStatus* | Represents the cross verification status of the result item. |
| [`OriginalToLocalMatrix`](#originaltolocalmatrix) | *Matrix* | Represents the transformation matrix from the original image coordinate system to the local coordinate system. |

The following properties are inherited from [`CapturedResultItem`]({{ site.dcv_maui_api }}core/captured-result-item.html).

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Type`]({{ site.dcv_maui_api }}core/captured-result-item.html#type) | *[EnumCapturedResultItemType]({{ site.dcv_maui_api }}core/enum/captured-result-item-type.html)* | Get the type of the captured result item, indicating what kind of data it represents. |
| [`TargetROIDefName`]({{ site.dcv_maui_api }}core/captured-result-item.html#targetroidefname) | *string* | Gets the name of the [`TargetROIDef`]({{ site.dcv_parameters_reference }}target-roi-def/) object which includes a task that generated the result. |
| [`TaskName`]({{ site.dcv_maui_api }}core/captured-result-item.html#taskname) | *string* | The name of the task that generated the result. |

### ImageData

Represents an [`ImageData`]({{ site.dcv_maui_api }}core/basic-structures/image-data.html) object for the deskewed image.

```csharp
ImageData ImageData { get; }
```

### SourceDeskewQuad

Represents the soure [Quadrilateral]({{ site.dcv_maui_api }}core/basic-structures/quadrilateral.html) that used to deskew the image.

```csharp
Quadrilateral Location { get; }
```

### CrossVerificationStatus

Represents the cross verification status of the result item. The cross verification status determines whether the result item is approved by the multi-frame cross verification mechanism. If approved, the cross verification status is `CVS_PASSED`. Otherwise, it is `CVS_FAILED`.

```csharp
EnumCrossVerificationStatus CrossVerificationStatus { get; }
```

### OriginalToLocalMatrix

Represents the transformation matrix from the original image coordinate system to the local coordinate system.

```csharp
Matrix OriginalToLocalMatrix { get; }
```
