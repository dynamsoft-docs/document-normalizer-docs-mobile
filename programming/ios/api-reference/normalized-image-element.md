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

*Assembly:* DynamsoftDocumentNormalizer.framework

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

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`imageData`](#imagedata) | *DSImageData \** | A `DSImageData` object as the image data of a normalized image. |

### imageData

A `DSImageData` object as the image data of a normalized image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, strong, nullable, readonly) DSImageData *imageData;
```
2. 
```swift
var imageData: ImageData? { get }
```
