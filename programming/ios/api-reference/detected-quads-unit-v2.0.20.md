---
layout: default-layout
title: DSDetectedQuadsUnit - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSDetectedQuadsUnit of Dynamsoft Document Normalizer module represents an intermediate result unit whose type is detected quads. It is inherited from the DSIntermediateResultUnit class.
keywords: detected quads, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSDetectedQuadsUnit

The `DSDetectedQuadsUnit` class represents an intermediate result unit whose type is detected quads. It is inherited from the `DSIntermediateResultUnit` class.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSDetectedQuadsUnit : DSIntermediateResultUnit
```
2. 
```swift
class DetectedQuadsUnit : IntermediateResultUnit
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`detectedQuads`](#detectedquads) | *NSArray<DSDetectedQuadElement*> \** | An array of `DSDetectedQuadElement`. Each `DSDetectedQuadElement` contains the information of a single detected quadrilateral. |

### detectedQuads

An array of `DSDetectedQuadElement`. Each `DSDetectedQuadElement` contains the information of a single detected quadrilateral.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable, copy) NSArray<DSDetectedQuadElement*>* detectedQuads;
```
2. 
```swift
var detectedQuads: [DetectedQuadElement]? { get set }
```
