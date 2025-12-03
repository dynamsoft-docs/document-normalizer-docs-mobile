---
layout: default-layout
title: SimplifiedDocumentNormalizerSettings - Dynamsoft Capture Vision React Native Edition API Reference
description: Interface SimplifiedDocumentNormalizerSettings of Dynamsoft Capture Vision React Native edition represents the simplified document normalizer settings.
keywords: document normalizer settings, Flutter, js
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# SimplifiedDocumentNormalizerSettings

Interface `SimplifiedDocumentNormalizerSettings` represents a series of simple settings related to the document scanning.

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```js
interface SimplifiedDocumentNormalizerSettings
```

## Properties

| Property | Types | Description |
| -------- | ----- | ----------- |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *Array\<EnumGrayscaleTransformationMode\>* | An array of GrayscaleTransformationMode. It controls whether to detect the inverted document boundary. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *Array\<EnumGrayscaleEnhancementMode\>* | An array of GrayscaleEnhancementModes. |
| [`colourMode`](#colourmode) | *[EnumImageColourMode](enum/image-colour-mode.md)* | The grayscale transformation mode. It controls whether to decode the inverted text. |
| [`pageSize`](#pagesize) | *Size* | The page size. |
| [`brightness`](#brightness) | *int* | The brightness. |
| [`contrast`](#contrast) | *int* | The contrast. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *int* | The maximum number of threads in one task. |
| [`scaleDownThreshold`](#scaledownthreshold) | *int* | The scale down threshold. |
| [`minQuadrilateralAreaRatio`](#minquadrilateralarearatio) | *int* | The minimum ratio between the target document area and the total image area. Only those exceeding this value will be output (measured in percentages). |
| [`expectedDocumentsCount`](#expecteddocumentscount) | *int* | The number of documents expected to be detected. |

### grayscaleTransformationModes

Defines the grayscale transformation modes with an array of [`EnumGrayscaleTransformationMode`]({{ site.dcv_react_native_api }}core/enum/grayscale-transformation-mode.html) items. This parameter is important when working with inverted documents, and must be used in order to locate the inverted document boundary.

```js
grayscaleTransformationModes?: Int32Array | Array<EnumGrayscaleTransformationMode>
```

### grayscaleEnhancementModes

Defines the grayscale enhancement modes with an array of [`EnumGrayscaleEnhancementModes`]({{ site.dcv_react_native_api }}core/enum/grayscale-enhancement-modes.html) items. This parameter can be quite powerful in increasing the border detection rate of your application should you experience any trouble in that area. To learn more about the `grayscaleEnhancementModes` and how they can be used, please visit the main [GrayscaleEnhancementModes]({{ site.dcv_parameters }}reference/image-parameter/grayscale-enhancement-modes.html) parameter page.

```js
grayscaleEnhancementModes?: Int32Array | Array<EnumGrayscaleEnhancementMode>
```

### colourMode

Defines the colour mode of the normalized image with an [`EnumImageColourMode`](enum/image-colour-mode.md) member. By default, the normalized image will output in colour.

```js
colourMode?: number | EnumImageColourMode
```

### pageSize

The page size of the normalized image.

```js
pageSize?: [number, number]
```

### brightness

The brightness of the normalized image result.

```js
brightness?: number
```

**Range**

[-100, 100]

### contrast

The contrast of the normalized image result.

```js
contrast?: number
```

**Range**

[-100,100]

### maxThreadsInOneTask

The maximum number of threads dedicated to a single task.

```js
maxThreadsInOneTask?: number
```

### scaleDownThreshold

If the original image size is quite large, then the `scaledownThreshold` can be used to shrink the image and speed up the processing. If the shorter edge size is larger than the defined scale down threshold, the library will calculate the required width and height of the image and shrink it to that size before moving forward in the process.

```js
scaleDownThreshold?: number
```

### minQuadrilateralAreaRatio

The minimum ratio between the target document area and the total image area. Only those exceeding this value will be output (measured in percentages).

```js
minQuadrilateralAreaRatio?: number
```

**Range**

[0, 100]

If expectedDocumentsCount is 1 && documentType is Document, the range is from 20 to 100.

### expectedDocumentsCount

The number of documents expected to be detected.

```js
expectedDocumentsCount?: number
```
