---
layout: default-layout
title: SimplifiedDocumentNormalizerSettings - Dynamsoft Capture Vision module MAUI Edition API Reference
description: The class SimplifiedDocumentNormalizerSettings of Dynamsoft Capture Vision module MAUI edition represents the simplified document normalizer settings.
keywords: document normalizer settings, MAUI, java
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# SimplifiedDocumentNormalizerSettings

The `SimplifiedDocumentNormalizerSettings` class represents a series of simple settings related to the Document Normalizer. Please note that this is not the full list of settings that can be utilized by the Document Normalizer, which you can find on the [DCV Parameters]({{ site.dcv_parameters_reference }}index.html) page.

## Definition

*Namespace:* Dynamsoft.DocumentNormalizer.Maui

*Assembly:* Dynamsoft.DocumentNormalizer.Maui

```csharp
class SimplifiedDocumentNormalizerSettings
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`GrayscaleTransformationModes`](#grayscaletransformationmodes) | *EnumGrayscaleTransformationMode[]* | An array of GrayscaleTransformationMode. It controls whether to detect the inverted document boundary. |
| [`GrayscaleEnhancementModes`](#grayscaleenhancementmodes) | *EnumGrayscaleEnhancementModes[]* | An array of GrayscaleEnhancementModes. |
| [`ColourMode`](#colourmode) | *EnumImageColourMode* | The grayscale transformation mode. It controls whether to decode the inverted text. |
| [`PageSize`](#pagesize) | *Size* | The page size. |
| [`Brightness`](#brightness) | *int* | The brightness. |
| [`Contrast`](#contrast) | *int* | The contrast. |
| [`MaxThreadsInOneTask`](#maxthreadsinonetask) | *int* | The maximum number of threads in one task. |
| [`ScaleDownThreshold`](#scaledownthreshold) | *int* | The scale down threshold. |
| [`MinQuadrilateralAreaRatio`](#minquadrilateralarearatio) | *int* | The minimum ratio between the target document area and the total image area. Only those exceeding this value will be outputted (measured in percentages). |
| [`ExpectedDocumentsCount`](#expecteddocumentscount) | *int* | The number of documents expected to be detected. |

### GrayscaleTransformationModes

Defines the grayscale transformation modes with an array of [`EnumGrayscaleTransformationMode`]({{ site.dcv_enumerations }}core/grayscale-transformation-mode.html?lang=maui) items. This parameter is important when working with inverted documents, and must be used in order to locate the inverted document boundary.

```csharp
EnumGrayscaleTransformationMode[] GrayscaleTransformationModes { get; set ; }
```

### GrayscaleEnhancementModes

Defines the grayscale enhancement modes with an array of [`EnumGrayscaleEnhancementModes`]({{ site.dcv_enumerations }}core/grayscale-enhancement-modes.html?lang=maui) items. This parameter can be quite powerful in increasing the border detection rate of your application should you experience any trouble in that area. To learn more about the `grayscaleEnhancementModes` and how they can be used, please visit the main [GrayscaleEnhancementModes]({{ site.dcv_parameters }}reference/image-parameter/grayscale-enhancement-modes.html) parameter page.

```csharp
EnumGrayscaleEnhancementMode[] GrayscaleEnhancementModes { get; set; }
```

### ColourMode

Defines the colour mode of the normalized image with an [`EnumImageColourMode`]({{ site.dcv_enumerations }}document-normalizer/image-colour-mode.html?lang=maui) member. By default, the normalized image will output in colour. In order to make the result image grayscale or binary, setting the `colourMode` to the corresponding pixel type will do the trick.

```csharp
EnumImageColourMode ColourMode { get; set; }
```

### PageSize

Defines the page size of the normalized image through an integer array.

```csharp
Size PageSize { get; set ; }
```

### Brightness

Defines the brightness of the normalized image result with an integer.

```csharp
// From -100 to 100
int Brightness { get; set ; }
```

### Contrast

Defines the contrast of the normalized image result with an integer.

```csharp
// contrast > 512
int Contrast { get; set ; }
```

### MaxThreadsInOneTask

Defines the maximum number of threads dedicated to a single task.

```csharp
int MaxThreadsInOneTask { get; set ; }
```

### ScaleDownThreshold

If the original image size is quite large, then the `scaledownThreshold` can be used to shrink the image and speed up the processing. If the shorter edge size is larger than the defined scale down threshold, the library will calculate the required width and height of the image and shrink it to that size before moving forward in the process.

```csharp
// Default = 2300
int ScaleDownThreshold { get; set ; }
```

### MinQuadrilateralAreaRatio

The minimum ratio between the target document area and the total image area. Only those exceeding this value will be outputted (measured in percentages).

```csharp
// If ExpectedDocumentsCount is 1 && documentType is Document, the range is from 20 to 100.
// Otherwise, 0 to 100
int MinQuadrilateralAreaRatio { get; set; }
```

### ExpectedDocumentsCount

The number of documents expected to be detected.

```csharp
// ExpectedDocumentsCount >0
int ExpectedDocumentsCount { get; set; }
```
