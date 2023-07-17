---
layout: default-layout
Title: DSNormalizedImageResultItem - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class DSNormalizedImageResultItem of Dynamsoft Document Normalizer module represents a captured result item whose type is a normalized image. It stores the normalized image information.
Keywords: normalized image result item, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSNormalizedImageResultItem

The `DSNormalizedImageResultItem` class represents a captured result item whose type is a normalized image. It stores the normalized image information.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.framework

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

A `DSImageData` object as the image data of a normalized image.

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

The quadrilateral from which you get the normalized image result item.

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
