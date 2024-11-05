---
layout: default-layout
title: NormalizedImagesResult - Dynamsoft Capture Vision MAUI SDK API Reference
description: The class NormalizedImagesResult represents a collection of captured result items whose type are normalized images.
keywords: normalized images, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# NormalizedImagesResult

The `NormalizedImagesResult` class represents a collection of [`NormalizedImageResultItem`](normalized-image-result-item.md), the basic unit of a normalized image result.

## Definition

*Namespace:* Dynamsoft.DocumentNormalizer.Maui

*Assembly:* Dynamsoft.DocumentNormalizer.Maui

```csharp
class NormalizedImagesResult
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Items`](#items) | *IList<NormalizedImageResultItem>* | An array of NormalizedImageResultItem. Each NormalizedImageResultItem is a result object of a single normalized image. |
| [`RotationTransformMatrix`](#rotationtransformmatrix) | *Matrix* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`ErrorCode`](#errorcode) | *int* | The error code of the normalized images result, if an error occurred. |
| [`ErrorMessage`](#errormessage) | *String* | The error message of the normalized images result, if an error occurred. |

### Items

An array of [`NormalizedImageResultItem`](normalized-image-result-item.md) objects, where each `NormalizedImageResultItem` represents a single normalized image.

```csharp
IList<NormalizedImageResultItem> Items { get; }
```

### RotationTransformMatrix

The rotation transformation matrix of the original image relative to the rotated image. Please see [Matrix](https://learn.microsoft.com/en-us/dotnet/api/microsoft.maui.controls.shapes.matrix?view=net-maui-8.0){:target="_blank"} for more info.

```csharp
Matrix RotationTransformMatrix { get; }
```

### ErrorCode

The error code of the normalized images result, if an error occurred.

```csharp
int ErrorCode { get; }
```

### ErrorMessage

The error message of the normalized images result, if an error occurred.

```csharp
String ErrorMessage { get; }
```
