---
layout: default-layout
title: DSNormalizedImageElement - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSNormalizedImageElement of Dynamsoft Document Normalizer module represents an intermediate result whose type is normalized image, It is inherited from DSRegionObjectElement and contains image data of normalized result as additional parameter.
keywords: normalized image element, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSNormalizedImageElement

The `DSNormalizedImageElement` class represents an intermediate result whose type is normalized image. It is inherited from `DSRegionObjectElement` and contains image data of normalized result as an additional parameter.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSNormalizedImageElement : DSRegionObjectElement
```
2. 
```swift
class NormalizedImageElement : RegionObjectElement
```

## Methods

| Methods | Description |
| ------- | ----------- |
| [`getImageData`](#getimagedata) | Returns a `DSImageData` object as the image data of a normalized image. |

The following methods are inherited from class [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-ios.md -%}

### getImageData

Returns `DSImageData` object as the image data of a normalized image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (nullable DSImageData *)getImageData;
```
2. 
```swift
func getImageData() -> DSImageData?
```
