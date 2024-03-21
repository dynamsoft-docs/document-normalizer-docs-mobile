---
layout: default-layout
title: DSLongLinesUnit - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSLongLinesUnit of Dynamsoft Document Normalizer module represents an intermediate result unit whose type is long lines. Line segments that are located in the same line are extended and merged to form a long line.
keywords: long lines, intermediate result unit, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSLongLinesUnit

The `DSLongLinesUnit` class represents an intermediate result unit whose type is long lines. Line segments that are located in the same line are extended and merged to form a long line.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSLongLinesUnit: DSIntermediateResultUnit
```
2. 
```swift
class LongLinesUnit: IntermediateResultUnit
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`longLines`](#longlines) | *NSArray<DSLineSegments*> \** | An array of `DSLineSegments` as the long lines. |

### longLines

An array of `DSLineSegments` as the long lines.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable, copy) NSArray<DSLineSegment*>* longLines;
```
2. 
```swift
var longLines: [LineSegment]? { get set }
```
