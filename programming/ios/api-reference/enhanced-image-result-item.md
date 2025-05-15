---
layout: default-layout
title: DSEnhancedImageResultItem - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSEnhancedImageResultItem of Dynamsoft Document Normalizer module represents a captured result item whose type is a enhanced image. It stores the enhanced image information.
keywords: enhanced image result item, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSEnhancedImageResultItem

The `DSEnhancedImageResultItem` class  is an extension of [`DSCapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html) that represents a enhanced image. This is the most basic unit of the enhanced image result, one of the captured result types that the Capture Vision Router can output.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSEnhancedImageResultItem: DSCapturedResultItem
```
2. 
```swift
class EnhancedImageResultItem : CapturedResultItem
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`imageData`](#imagedata) | *DSImageData \** | A `DSImageData` object as the image data of a enhanced image. |
| [`originalToLocalMatrix`](#originaltolocalmatrix) | *CGAffineTransform* | The transformation matrix from the original image coordinate system to the local coordinate system. |

The following attributes are inherited from [`DSCapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html).

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`type`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#type) | *DSCapturedResultItemType* | The type of the captured result item. |
| [`referencedItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#referenceditem) | *DSCapturedResultItem \** | The referenced captured result item. The reference dependencies is defined in the Capture Vision settings. |
| [`targetROIDefName`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#targetroidefname) | *NSString* | The name of the [`TargetROIDef`]({{ site.dcv_parameters_reference }}target-roi-def/) object which includes a task that generated the result. |
| [`taskName`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#taskname) | *NSString* | The name of the task that generated the result. |

### imageData

A [`DSImageData`]({{ site.dcv_ios_api }}core/basic-structures/image-data.html) object for the enhanced image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable, readonly) DSImageData *imageData
```
2. 
```swift
var imageData: ImageData? { get }
```

### originalToLocalMatrix

The transformation matrix from the original image coordinate system to the local coordinate system.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) CGAffineTransform originalToLocalMatrix;
```
2. 
```swift
var originalToLocalMatrix: CGAffineTransform { get }
```
