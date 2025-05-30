---
layout: default-layout
title: DetectedQuadsResult - Dynamsoft Capture Vision MAUI SDK API Reference
description: The class DetectedQuadsResult represents a captured result whose type is detected quads, which contains an array of DetectedQuadResultItems and the rotation transformation matrix of the original image relative to the rotated image.
keywords: detected quads result, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
ignore: true
---

# DetectedQuadsResult

The `DetectedQuadsResult` class represents a collection of [`DetectedQuadResultItems`](detected-quad-result-item.md), the basic unit of a detected quad result.

## Definition

*Namespace:* Dynamsoft.DocumentNormalizer.Maui

*Assembly:* Dynamsoft.DocumentNormalizer.Maui

```csharp
class DetectedQuadsResult
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Items`](#items) | *IList<DetectedQuadResultItem>* | An array of [`DetectedQuadResultItem`](./detected-quad-result-item.md), which are the detected quadrilateral items. |
| [`RotationTransformMatrix`](#rotationtransformmatrix) | *Matrix* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`OriginalImageHashId`](#originalimagehashid) | *string* | The hash id of the original image. You can use this ID to get the original image via `IntermediateResultManager` class. |
| [`ErrorCode`](#errorcode) | *int* | The error code of the detected quads result, if an error occurred. |
| [`ErrorMessage`](#errormessage) | *String* | The error message of the detected quads result, if an error occurred. |

### Items

An array of [`DetectedQuadResultItem`](./detected-quad-result-item.md), which represents the basic unit of the captured result, in this case, a detected quadrilateral.

```csharp
IList<DetectedQuadResultItem> Items { get; }
```

### RotationTransformMatrix

The rotation transformation matrix of the original image relative to the rotated image. Please see [Matrix](https://learn.microsoft.com/en-us/dotnet/api/microsoft.maui.controls.shapes.matrix?view=net-maui-8.0){:target="_blank"} for more info.

```csharp
Matrix RotationTransformMatrix { get; }
```

### OriginalImageHashId

The hash ID of the original image. You can use this ID to get the original image via [`IntermediateResultManager`]({{ site.dcv_maui_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html) class.

```csharp
string OriginalImageHashId { get; }
```

### ErrorCode

The error code of the detected quads result, if an error occurred.

```csharp
int ErrorCode { get; }
```

### ErrorMessage

The error message of the detected quads result, if an error occurred.

```csharp
String ErrorMessage { get; }
```
