---
layout: default-layout
Title: DSDetectedQuadsResult - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class DSDetectedQuadsResult of Dynamsoft Document Normalizer module represents a captured result whose type is detected quads, which contains an array of DSDetectedQuadResultItems and the rotation transformation matrix of the original image relative to the rotated image.
Keywords: detected quads result, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSDetectedQuadsResult

The `DSDetectedQuadsResult` class represents a captured result whose type is detected quads, which contains an array of `DSDetectedQuadResultItems` and the rotation transformation matrix of the original image relative to the rotated image.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSDetectedQuadsResult : NSObject
```
2. 
```swift
class DetectedQuadsResult : NSObject
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`items`](#items) | *NSArray<DSDetectedQuadResultItem \*>* | An array of `DSDetectedQuadResultItems`, which are the basic unit of the captured results. |
| [`rotationTransformMatrix`](#rotationtransformmatrix) | *CGAffineTransform* | The rotation transformation matrix of the original image relative to the rotated image. |

### items

An array of `DSDetectedQuadResultItems`, which are the basic unit of the captured results.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, strong, nullable, readonly) NSArray<DSDetectedQuadResultItem*>* items;
```
2. 
```swift
var items: [DSDetectedQuadResultItem]? { get }
```

### rotationTransformMatrix

The rotation transformation matrix of the original image relative to the rotated image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) CGAffineTransform rotationTransformMatrix;
```
2. 
```swift
var rotationTransformMatrix: CGAffineTransform { get }
```
