---
layout: default-layout
title: DSEnhancedImagesUnit - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSEnhancedImagesUnit of Dynamsoft Document Normalizer module represents an intermediate result unit whose type is enhanced images.
keywords: enhanced images, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSEnhancedImagesUnit

The `DSEnhancedImagesUnit` class represents an intermediate result unit whose type is enhanced images.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSEnhancedImagesUnit: DSIntermediateResultUnit
```
2. 
```swift
class EnhancedImagesUnit: IntermediateResultUnit
```

## Methods

| Methods | Description |
| ------- | ----------- |
| [`getEnhancedImage`](#getenhancedimage) | Gets the enhanced image of type [`DSEnhancedImageElement`](enhanced-image-element.md). |
| [`setEnhancedImage`](#setenhancedimage) | Set the [`DSEnhancedImageElement`](enhanced-image-element.md) at the specified index. |

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getEnhancedImage

Gets the [`DSEnhancedImageElement`](enhanced-image-element.md).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(DSEnhancedImageElement *)getEnhancedImage;
```
2. 
```swift
func getEnhancedImage() -> EnhancedImageElement
```

**Return Value**

The enhanced image of type [`DSEnhancedImageElement`](enhanced-image-element.md).

### setEnhancedImage

Set the [`DSEnhancedImageElement`](enhanced-image-element.md) at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)setEnhancedImage:(DSEnhancedImageElement*)element;
```
2. 
```swift
func setEnhancedImage(element: EnhancedImageElement) -> Int
```

**Parameters**

`[in] element`: The enhanced image to be set.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
