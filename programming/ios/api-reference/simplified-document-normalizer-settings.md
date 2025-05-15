---
layout: default-layout
title: DSSimplifiedDocumentNormalizerSettings - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSSimplifiedDocumentNormalizerSettings of Dynamsoft Document Normalizer module represents the simplified document normalizer settings.
keywords: document normalizer settings, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSSimplifiedDocumentNormalizerSettings

The `DSSimplifiedDocumentNormalizerSettings` class represents a series of simple settings related to the Document Normalizer. Please note that this is not the full list of settings that can be utilized by the Document Normalizer, which you can find on the [Dynamsoft Document Normalizer Parameters]({{ site.parameters }}reference/index.html){:target="_blank"} page.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSSimplifiedDocumentNormalizerSettings: NSObject
```
2. 
```swift
class SimplifiedDocumentNormalizerSettings: NSObject
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *NSArray<NSNumber>* \* | An array of DSGrayscaleTransformationMode. It controls whether to detect the inverted document boundary. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *NSArray<NSNumber>* \* | An array of DSGrayscaleEnhancementModes. |
| [`colourMode`](#colourmode) | *DSImageColourMode \* | The grayscale transformation mode. It controls whether to decode the inverted text. |
| [`pageSize`](#pagesize) | *CGSize \* | The page size. |
| [`brightness`](#brightness) | *NSInteger \* | The brightness. |
| [`contrast`](#contrast) | *NSInteger \* | The contrast. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *NSInteger \* | The maximum number of threads in one task. |
| [`scaleDownThreshold`](#scaledownthreshold) | *NSInteger \* | The scale down threshold. |
| [`minQuadrilateralAreaRatio`](#minquadrilateralarearatio) | *int* | The minimum ratio between the target document area and the total image area. Only those exceeding this value will be output (measured in percentages). |
| [`expectedDocumentsCount`](#expecteddocumentscount) | *int* | The number of documents expected to be detected. |

### grayscaleTransformationModes

Defines the grayscale transformation modes with an array of [`DSGrayscaleTransformationMode`]({{ site.dcv_enumerations }}core/grayscale-transformation-mode.html?lang=objc,swift) items. This parameter is important when working with inverted documents, and must be used in order to locate the inverted document boundary.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable, copy) NSArray<NSNumber>* grayscaleTransformationModes;
```
2. 
```swift
var grayscaleTransformationModes: [NSNumber]? { get set }
```

### grayscaleEnhancementModes

Defines the grayscale enhancement modes with an array of [`DSGrayscaleEnhancementModes`]({{ site.dcv_enumerations }}core/grayscale-enhancement-modes.html?lang=objc,swift) items. This parameter can be quite powerful in increasing the border detection rate of your application should you experience any trouble in that area. To learn more about the `grayscaleEnhancementModes` and how they can be used, please visit the main [GrayscaleEnhancementModes]({{ site.dcv_parameters }}reference/image-parameter/grayscale-enhancement-modes.html) parameter page.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable, copy) NSArray<NSNumber>* grayscaleEnhancementModes;
```
2. 
```swift
var grayscaleEnhancementModes: [NSNumber]? { get set }
```

### colourMode

Defines the colour mode (pixel type) of the normalized image with a [`DSImageColourMode`]({{ site.dcv_enumerations }}document-normalizer/image-colour-mode.html?lang=objc,swift) member. By default, the normalized image will output in colour. In order to make the result image grayscale or binary, setting the `colourMode` to the corresponding pixel type will do the trick.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) DSImageColourMode colourMode;
```
2. 
```swift
var colourMode: ImageColourMode { get set }
```

### pageSize

Defines the page size of the normalized image with a [`CGSize`](https://developer.apple.com/documentation/corefoundation/cgsize){:target="_blank"} object.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) CGSize pageSize;
```
2. 
```swift
var pageSize: CGSize { get set }
```

### brightness

Defines the brightness of the normalized image result with an integer.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger brightness;
```
2. 
```swift
var brightness: Int { get set }
```

### contrast

Defines the contrast of the normalized image result with an integer.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger contrast;
```
2. 
```swift
var contrast: Int { get set }
```

### maxThreadsInOneTask

Defines the maximum number of threads dedicated to a single task.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger maxThreadsInOneTask;
```
2. 
```swift
var maxThreadsInOneTask: Int { get set }
```

### scaleDownThreshold

If the original image size is quite large, then the `scaledownThreshold` can be used to shrink the image and speed up the processing. If the shorter edge size is larger than the defined scale down threshold, the library will calculate the required width and height of the image and shrink it to that size before moving forward in the process.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger scaleDownThreshold;
```
2. 
```swift
var scaleDownThreshold: Int { get set }
```

### minQuadrilateralAreaRatio

The minimum ratio between the target document area and the total image area. Only those exceeding this value will be output (measured in percentages).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger MinQuadrilateralAreaRatio;
```
2. 
```swift
var minQuadrilateralAreaRatio: Int { get set }
```

### expectedDocumentsCount

The number of documents expected to be detected.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger expectedDocumentsCount;
```
2. 
```swift
var expectedDocumentsCount: Int { get set }
```
