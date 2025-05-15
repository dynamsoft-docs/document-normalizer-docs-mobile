---
layout: default-layout
title: DSDeskewedImagesUnit - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSDeskewedImagesUnit of Dynamsoft Document Normalizer module represents an intermediate result unit whose type is deskewed images.
keywords: deskewed images, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSDeskewedImagesUnit

The `DSDeskewedImagesUnit` class represents an intermediate result unit whose type is deskewed images.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSDeskewedImagesUnit: DSIntermediateResultUnit
```
2. 
```swift
class DeskewedImagesUnit: IntermediateResultUnit
```

## Methods

| Methods | Description |
| ------- | ----------- |
| [`getDeskewedImage`](#getdeskewedimage) | Gets the deskewed image of type [`DSDeskewedImageElement`](deskewed-image-element.md). |
| [`setDeskewedImage`](#setdeskewedimage) | Sets the deskewed image with a [`DSDeskewedImageElement`](deskewed-image-element.md) object |

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getDeskewedImage

Gets the deskewed image of type [`DSDeskewedImageElement`](deskewed-image-element.md).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(DSDeskewedImageElement *)getDeskewedImage;
```
2. 
```swift
func getDeskewedImage() -> DeskewedImageElement
```

**Return Value**

The deskewed image of type [`DSDeskewedImageElement`](deskewed-image-element.md).

### setDeskewedImage

Set the deskewed image with a [`DSDeskewedImageElement`](deskewed-image-element.md) object.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)setDeskewedImage:(DSDeskewedImageElement*)element
       matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func setDeskewedImage(element: DeskewedImageElement, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`[in] element`: The deskewed image to be set.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
