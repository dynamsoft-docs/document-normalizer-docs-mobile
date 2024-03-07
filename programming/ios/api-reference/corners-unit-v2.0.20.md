---
layout: default-layout
title: DSCornersUnit - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSCornersUnit of Dynamsoft Document Normalizer module represents an intermediate result unit whose type is corners.
keywords: corners unit, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSCornersUnit

The `DSCornersUnit` class represents an intermediate result unit whose type is corners.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSCornersUnit : DSIntermediateResultUnit
```
2. 
```swift
class CornersUnit : IntermediateResultUnit
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`corners`](#corners) | *NSArray<DSCorner*> \** | An array of corners. It includes all corners that participate quadrilaterals assembling. |

### corners

An array of corners. It includes all corners that participate quadrilaterals assembling.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, copy, nullable) NSArray<DSCorner *> *corners
```
2. 
```swift
var corners: [Corner]? { get set }
```
