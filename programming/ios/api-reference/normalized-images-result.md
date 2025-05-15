---
layout: default-layout
title: DSNormalizedImagesResult - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSNormalizedImagesResult of Dynamsoft Document Normalizer module represents a collection of captured result items whose type are normalized images.
keywords: normalized images, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSNormalizedImagesResult

The `DSNormalizedImagesResult` class represents a collection of [`DSNormalizedImageResultItem`](normalized-image-result-item.md), the basic unit of a normalized image result.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSNormalizedImagesResult : NSObject
```
2. 
```swift
class NormalizedImagesResult : NSObject
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`items`](#items) | *NSArray<DSNormalizedImageResultItem \*>* | An array of DSNormalizedImageResultItem. Each DSNormalizedImageResultItem is a result object of a single normalized image. |
| [`rotationTransformMatrix`](#rotationtransformmatrix) | *CGAffineTransform* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`originalImageHashId`](#originalimagehashid) | *NSString* | The hash id of the original image. You can use this ID to get the original image via IntermediateResultManager class. |
| [`originalImageTag`](#originalimagetag) | *DSImageTag \* | The tag of the original image, from which you get the normalized image. |

### items

An array of [`DSNormalizedImageResultItem`](normalized-image-result-item.md), where each `DSNormalizedImageResultItem` represents a single normalized image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable, readonly) NSArray<DSNormalizedImageResultItem *>* items;
```
2. 
```swift
var items: [DSNormalizedImageResultItem]? { get }
```

### rotationTransformMatrix

The rotation transformation matrix of the original image relative to the rotated image. Please see [CGAffineTransform](https://developer.apple.com/documentation/corefoundation/cgaffinetransform){:target="_blank"} for more info.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign, readonly) CGAffineTransform rotationTransformMatrix;
```
2. 
```swift
var rotationTransformMatrix: CGAffineTransform { get }
```

### originalImageHashId

The hash ID of the original image. You can use this ID to get the original image via [`IntermediateResultManager`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-manager.html) class.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nonnull, readonly) NSString* originalImageHashId;
```
2. 
```swift
var originalImageHashId: String { get }
```

### originalImageTag

The [`ImageTag`]({{ site.dcv_ios_api }}core/basic-structures/image-tag.html) of the original image, which contains various information about the image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly) DSImageTag* originalImageTag;
```
2. 
```swift
var originalImageTag: DSImageTag { get }
```
