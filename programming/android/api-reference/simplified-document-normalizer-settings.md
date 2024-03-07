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

The `SimplifiedDocumentNormalizerSettings` class represents the simplified document normalizer settings.

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class SimplifiedDocumentNormalizerSettings
```

## Attributes

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

### grayscaleTransformationModes

Defines the grayscale transformation mode with an array of [`EnumGrayscaleTransformationMode`]({{ site.dcv_enumerations }}core/grayscale-transformation-mode.html?lang=android). It controls whether to detect the inverted document boundary.

```java
EnumGrayscaleTransformationMode[] grayscaleTransformationModes;
```

### grayscaleEnhancementModes

Defines the grayscale enhancement mode with an array of [`EnumGrayscaleEnhancementModes`]({{ site.dcv_enumerations }}core/grayscale-enhancement-modes.html?lang=android).

```java
EnumGrayscaleEnhancementMode[] grayscaleEnhancementModes;
```

### colourMode

Defines the colour mode of the normalized image with an [`EnumImageColourMode`]({{ site.dcv_enumerations }}core/image-colour-mode.html?lang=android) member.

```java
EnumImageColourMode colourMode;
```

### pageSize

Defines the page size of the normalized image with the width and height in an int array.

```java
int[] pageSize;
```

### brightness

Defines the brightness of the normalized image with an integer.

```java
int brightness;
```

### contrast

Defines the contrast of the normalized image with an integer.

```java
int contrast;
```

### maxThreadsInOneTask

Defines the maximum number of threads in one task.

```java
int maxThreadsInOneTask;
```

### scaleDownThreshold

Defines the scale down threshold. If the image size is larger than the scale down threshold, the image is scaled down by half.

```java
int scaleDownThreshold;
```
