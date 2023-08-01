---
layout: default-layout
Title: DSNormalizedImagesResult - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class DSNormalizedImagesResult of Dynamsoft Document Normalizer module represents a collection of captured result items whose type are normalized images.
Keywords: normalized images, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSNormalizedImagesResult

The `DSNormalizedImagesResult` class represents a collection of captured result items whose type are normalized images.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.framework

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
| [`sourceImageHashId`](#sourceimagehashid) | *NSString* | The hash id of the source image. You can use this ID to get the source image via IntermediateResultManager class. |
| [`sourceImageTag`](#sourceimagetag) | *DSImageTag \* | The tag of the original image, from which you get the normalized image. |

### items

An array of DSNormalizedImageResultItem. Each DSNormalizedImageResultItem is a result object of a single normalized image.

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

The rotation transformation matrix of the original image relative to the rotated image.

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

### sourceImageHashId

The hash id of the source image. You can use this ID to get the source image via IntermediateResultManager class.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nonnull, readonly) NSString* sourceImageHashId;
```
2. 
```swift
var sourceImageHashId: String { get }
```

### sourceImageTag

The tag of the original image, from which you get the normalized image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly) DSImageTag* sourceImageTag;
```
2. 
```swift
var sourceImageTag: DSImageTag { get }
```
