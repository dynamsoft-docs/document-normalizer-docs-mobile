---
layout: default-layout
title: DSDeskewedImageElement - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSDeskewedImageElement of Dynamsoft Document Normalizer module represents an intermediate result whose type is deskewed image, It is inherited from DSRegionObjectElement and contains image data of deskewed result as additional parameter.
keywords: deskewed image element, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSDeskewedImageElement

The `DSDeskewedImageElement` class represents an intermediate result whose type is deskewed image. It is inherited from `DSRegionObjectElement` and contains image data of deskewed result as an additional parameter.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSDeskewedImageElement : DSRegionObjectElement
```
2. 
```swift
class DeskewedImageElement : RegionObjectElement
```

## Methods

| Methods | Description |
| ------- | ----------- |
| [`setImageData`](#getimagedata) | Sets the image data of the deskewed image with a `DSImageData` object. |


| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`sourceDeskewQuad`](#sourcedeskewquad) | *DSQuadrilateral \** | The quadrilateral from which you get the deskewed image result item. |

The following methods are inherited from class [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-ios.md -%}

### getImageData

Returns `DSImageData` object as the image data of a deskewed image.

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

### setImageData

Sets the image data of the deskewed image with a `DSImageData` object.

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

### sourceDeskewQuad

The quadrilateral from which you get the deskewed image result item.

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
