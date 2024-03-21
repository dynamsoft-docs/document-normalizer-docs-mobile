---
layout: default-layout
title: DSNormalizedImageResultItem - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSNormalizedImageResultItem of Dynamsoft Document Normalizer module represents a captured result item whose type is a normalized image. It stores the normalized image information.
keywords: normalized image result item, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSNormalizedImageResultItem

The `DSNormalizedImageResultItem` class  is an extension of [`DSCapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html) that represents a normalized image. This is the most basic unit of the normalized image result, one of the captured result types that the Capture Vision Router can output.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSNormalizedImageResultItem: DSCapturedResultItem
```
2. 
```swift
class NormalizedImageResultItem : CapturedResultItem
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`imageData`](#imagedata) | *DSImageData \** | A `DSImageData` object as the image data of a normalized image. |
| [`location`](#location) | *DSQuadrilateral \** | The quadrilateral from which you get the normalized image result item. |

### imageData

A [`DSImageData`]({{ site.dcv_ios_api }}core/basic-structures/image-data.html) object for the normalized image.

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

### location

The [DSQuadrilateral]({{ site.dcv_ios_api }}core/basic-structures/quadrilateral.html) that represents the location of the normalized image within the original image or frame.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable, readonly) DSQuadrilateral *location
```
2. 
```swift
var location: Quadrilateral? { get }
```
