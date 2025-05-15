---
layout: default-layout
title: DSDeskewedImageResultItem - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSDeskewedImageResultItem of Dynamsoft Document Normalizer module represents a captured result item whose type is a deskewed image. It stores the deskewed image information.
keywords: deskewed image result item, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSDeskewedImageResultItem

The `DSDeskewedImageResultItem` class  is an extension of [`DSCapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html) that represents a deskewed image. This is the most basic unit of the deskewed image result, one of the captured result types that the Capture Vision Router can output.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSDeskewedImageResultItem: DSCapturedResultItem
```
2. 
```swift
class DeskewedImageResultItem : CapturedResultItem
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`imageData`](#imagedata) | *DSImageData \** | A `DSImageData` object as the image data of a deskewed image. |
| [`sourceDeskewQuad`](#sourcedeskewquad) | *DSQuadrilateral \** | The quadrilateral from which you get the deskewed image result item. |
| [`crossVerificationStatus`](#crossverificationstatus) | *DSCrossVerificationStatus* | The cross verification status of the result item. |
| [`originalToLocalMatrix`](#originaltolocalmatrix) | *CGAffineTransform* | The transformation matrix from the original image coordinate system to the local coordinate system. |

The following attributes are inherited from [`DSCapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html).

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`type`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#type) | *DSCapturedResultItemType* | The type of the captured result item. |
| [`referencedItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#referenceditem) | *DSCapturedResultItem \** | The referenced captured result item. The reference dependencies is defined in the Capture Vision settings. |
| [`targetROIDefName`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#targetroidefname) | *NSString* | The name of the [`TargetROIDef`]({{ site.dcv_parameters_reference }}target-roi-def/) object which includes a task that generated the result. |
| [`taskName`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#taskname) | *NSString* | The name of the task that generated the result. |

### imageData

A [`DSImageData`]({{ site.dcv_ios_api }}core/basic-structures/image-data.html) object for the deskewed image.

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

The quadrilateral from which you get the deskewed image result item.

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

### crossVerificationStatus

The cross verification status of the result. The cross verification status determines whether the result item is approved by the multi-frame cross verification mechanism. If approved, the cross verification status is `passed`. Otherwise, it is `failed`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly) DSCrossVerificationStatus crossVerificationStatus;
```
2. 
```swift
var crossVerificationStatus: CrossVerificationStatus { get }
```

Related API:

- [`DSCrossVerificationStatus`]({{ site.dcv_enumerations }}core/cross-verification-status.html)

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
