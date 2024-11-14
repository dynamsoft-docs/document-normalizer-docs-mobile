---
layout: default-layout
title: SimplifiedDocumentNormalizerSettings - Dynamsoft Document Normalizer module Android Edition API Reference
description: The class SimplifiedDocumentNormalizerSettings of Dynamsoft Document Normalizer module Android edition represents the simplified document normalizer settings.
keywords: document normalizer settings, Android, java
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# SimplifiedDocumentNormalizerSettings

The `SimplifiedDocumentNormalizerSettings` class represents a series of simple settings related to the Document Normalizer. Please note that this is not the full list of settings that can be utilized by the Document Normalizer, which you can find on the [Dynamsoft Document Normalizer Parameters]({{ site.parameters }}reference/index.html){:target="_blank"} page.

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class SimplifiedDocumentNormalizerSettings
```

## Methods & Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *EnumGrayscaleTransformationMode[]* | An array of GrayscaleTransformationMode. It controls whether to detect the inverted document boundary. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *EnumGrayscaleEnhancementModes[]* | An array of GrayscaleEnhancementModes. |
| [`colourMode`](#colourmode) | *EnumImageColourMode* | The grayscale transformation mode. It controls whether to decode the inverted text. |
| [`pageSize`](#pagesize) | *int[]* | The page size. |
| [`brightness`](#brightness) | *int* | The brightness. |
| [`contrast`](#contrast) | *int* | The contrast. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *int* | The maximum number of threads in one task. |
| [`scaleDownThreshold`](#scaledownthreshold) | *int* | The scale down threshold. |

| Methods | Description |
| [`toJson`](#tojson) | Generate a JSON string from this `SimplifiedDocumentNormalizerSettings` object. |
| [`fromJson`](#fromjson) | Create a `SimplifiedDocumentNormalizerSettings` object from a JSON string. |

### grayscaleTransformationModes

Defines the grayscale transformation modes with an array of [`EnumGrayscaleTransformationMode`]({{ site.dcv_enumerations }}core/grayscale-transformation-mode.html?lang=android) items. This parameter is important when working with inverted documents, and must be used in order to locate the inverted document boundary.

```java
EnumGrayscaleTransformationMode[] grayscaleTransformationModes;
```

### grayscaleEnhancementModes

Defines the grayscale enhancement modes with an array of [`EnumGrayscaleEnhancementModes`]({{ site.dcv_enumerations }}core/grayscale-enhancement-mode.html?lang=android) items. This parameter can be quite powerful in increasing the border detection rate of your application should you experience any trouble in that area. To learn more about the `grayscaleEnhancementModes` and how they can be used, please visit the main [GrayscaleEnhancementModes]({{ site.dcv_parameters }}reference/image-parameter/grayscale-enhancement-modes.html) parameter page.

```java
EnumGrayscaleEnhancementMode[] grayscaleEnhancementModes;
```

### colourMode

Defines the colour mode of the normalized image with an [`EnumImageColourMode`]({{ site.dcv_enumerations }}document-normalizer/image-colour-mode.html?lang=android) member. By default, the normalized image will output in colour. In order to make the result image grayscale or binary, setting the `colourMode` to the corresponding pixel type will do the trick.

```java
EnumImageColourMode colourMode;
```

### pageSize

Defines the page size of the normalized image through an integer array.

```java
int[] pageSize;
```

### brightness

Defines the brightness of the normalized image result with an integer.

```java
int brightness;
```

### contrast

Defines the contrast of the normalized image result with an integer.

```java
int contrast;
```

### maxThreadsInOneTask

Defines the maximum number of threads dedicated to a single task.

```java
int maxThreadsInOneTask;
```

### scaleDownThreshold

If the original image size is quite large, then the `scaledownThreshold` can be used to shrink the image and speed up the processing. If the shorter edge size is larger than the defined scale down threshold, the library will calculate the required width and height of the image and shrink it to that size before moving forward in the process.

```java
int scaleDownThreshold;
```

### toJson

Generate a JSON string from this `SimplifiedDocumentNormalizerSettings` object.

```java
String toJson()
```

**Return Value**

A JSON string that contains all the information of this object.

### fromJson

Create a `SimplifiedDocumentNormalizerSettings` object from a JSON string.

```java
static SimplifiedDocumentNormalizerSettings fromJson(String json);
```

**Parameters**

* `json`: A JSON string that contains all `SimplifiedDocumentNormalizerSettings` required information.

**Return Value**

A `SimplifiedDocumentNormalizerSettings` object.
