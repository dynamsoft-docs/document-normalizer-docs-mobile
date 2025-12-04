---
layout: default-layout
title: SimplifiedDocumentNormalizerSettings - Dynamsoft Capture Vision Flutter Edition API Reference
description: The class SimplifiedDocumentNormalizerSettings of Dynamsoft Capture Vision Flutter edition represents the simplified document normalizer settings.
keywords: document normalizer settings, Flutter, dart
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# SimplifiedDocumentNormalizerSettings

The `SimplifiedDocumentNormalizerSettings` class represents a series of simple settings related to the document scanning.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class SimplifiedDocumentNormalizerSettings
```

## Properties

| Property | Types | Description |
| -------- | ----- | ----------- |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *List\<EnumGrayscaleTransformationMode\>* | An array of GrayscaleTransformationMode. It controls whether to detect the inverted document boundary. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *List\<EnumGrayscaleEnhancementMode\>* | An array of GrayscaleEnhancementModes. |
| [`colourMode`](#colourmode) | *EnumImageColourMode* | The grayscale transformation mode. It controls whether to decode the inverted text. |
| [`pageSize`](#pagesize) | *Size* | The page size. |
| [`brightness`](#brightness) | *int* | The brightness. |
| [`contrast`](#contrast) | *int* | The contrast. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *int* | The maximum number of threads in one task. |
| [`scaleDownThreshold`](#scaledownthreshold) | *int* | The scale down threshold. |
| [`minQuadrilateralAreaRatio`](#minquadrilateralarearatio) | *int* | The minimum ratio between the target document area and the total image area. Only those exceeding this value will be output (measured in percentages). |
| [`expectedDocumentsCount`](#expecteddocumentscount) | *int* | The number of documents expected to be detected. |

### grayscaleTransformationModes

Defines the grayscale transformation modes with an array of [`EnumGrayscaleTransformationMode`]({{ site.dcv_flutter_api }}core/enum/grayscale-transformation-mode.html) items. This parameter is important when working with inverted documents, and must be used in order to locate the inverted document boundary.

```dart
List<EnumGrayscaleTransformationMode> grayscaleTransformationModes;
```

### grayscaleEnhancementModes

Defines the grayscale enhancement modes with an array of [`EnumGrayscaleEnhancementModes`]({{ site.dcv_flutter_api }}core/enum/grayscale-enhancement-modes.html) items. This parameter can be quite powerful in increasing the border detection rate of your application should you experience any trouble in that area. To learn more about the `grayscaleEnhancementModes` and how they can be used, please visit the main [GrayscaleEnhancementModes]({{ site.dcv_parameters }}reference/image-parameter/grayscale-enhancement-modes.html) parameter page.

```dart
List<EnumGrayscaleEnhancementMode> grayscaleEnhancementModes;
```

### colourMode

Defines the colour mode of the normalized image with an [`EnumImageColourMode`]({{ site.dcv_flutter_api }}core/enum/image-colour-mode.html) member. By default, the normalized image will output in colour. In order to make the result image grayscale or binary, setting the `colourMode` to the corresponding pixel type will do the trick.

```dart
EnumImageColourMode colourMode;
```

### pageSize

The page size of the normalized image.

```dart
Size pageSize;
```

### brightness

The brightness of the normalized image result.

```dart
@IntRange
int brightness;
```

**Range**

[-100, 100]

### contrast

The contrast of the normalized image result.

```dart
int contrast;
```

**Range**

[-100,100]

### maxThreadsInOneTask

The maximum number of threads dedicated to a single task.

```dart
int maxThreadsInOneTask;
```

### scaleDownThreshold

If the original image size is quite large, then the `scaledownThreshold` can be used to shrink the image and speed up the processing. If the shorter edge size is larger than the defined scale down threshold, the library will calculate the required width and height of the image and shrink it to that size before moving forward in the process.

```dart
int scaleDownThreshold;
```

### minQuadrilateralAreaRatio

The minimum ratio between the target document area and the total image area. Only those exceeding this value will be output (measured in percentages).

```dart
int minQuadrilateralAreaRatio;
```

**Range**

[0, 100]

If expectedDocumentsCount is 1 && documentType is Document, the range is from 20 to 100.

### expectedDocumentsCount

The number of documents expected to be detected.

```dart
int expectedDocumentsCount;
```
