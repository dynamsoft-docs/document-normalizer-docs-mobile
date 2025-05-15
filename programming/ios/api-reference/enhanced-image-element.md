---
layout: default-layout
title: DSEnhancedImageElement - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSEnhancedImageElement of Dynamsoft Document Normalizer module represents an intermediate result whose type is enhanced image, It is inherited from DSRegionObjectElement and contains image data of enhanced result as additional parameter.
keywords: enhanced image element, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSEnhancedImageElement

The `DSEnhancedImageElement` class represents an intermediate result whose type is enhanced image. It is inherited from `DSRegionObjectElement` and contains image data of enhanced result as an additional parameter.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSEnhancedImageElement : DSRegionObjectElement
```
2. 
```swift
class EnhancedImageElement : RegionObjectElement
```

## Methods

| Methods | Description |
| ------- | ----------- |
| [`setImageData`](#getimagedata) | Sets the image data of the enhanced image with a `DSImageData` object. |

The following methods are inherited from class [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-ios.md -%}

### setImageData

Sets the image data of the enhanced image with a `DSImageData` object.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setImageData:(nullable DSImageData *)imageData;
```
2. 
```swift
func setImageData(_ imageData: ImageData?)
```
