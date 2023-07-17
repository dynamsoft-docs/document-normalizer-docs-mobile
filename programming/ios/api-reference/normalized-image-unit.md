---
layout: default-layout
Title: DSNormalizedImagesUnit - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class DSNormalizedImagesUnit of Dynamsoft Document Normalizer module represents an intermediate result unit whose type is normalized images.
Keywords: normalized images, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSNormalizedImagesUnit

The `DSNormalizedImagesUnit` class represents an intermediate result unit whose type is normalized images.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSNormalizedImagesUnit: DSIntermediateResultUnit
```
2. 
```swift
class NormalizedImagesUnit: IntermediateResultUnit
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`normalizedImages`](#normalizedimages) | *NSArray<DSNormalizedImageElement*>* \* | An array of DSNormalizedImageElements. |

### normalizedImages

An array of `DSNormalizedImageElements`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, copy, nullable) NSArray<DSNormalizedImageElement*>* normalizedImages;
```
2. 
```swift
var normalizedImages: [NormalizedImageElement]? { get set }
```
