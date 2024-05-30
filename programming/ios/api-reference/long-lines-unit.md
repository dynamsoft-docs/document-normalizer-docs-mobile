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

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getLongLines`](#getlonglines) | Get an array of `DSLineSegment` as the long lines. |
| [`getCount`](#getcount) | Get the number of long lines. |
| [`getLongLine`](#getlongline) | Get a long line. |
| [`removeAllLongLines`](#removealllonglines) | Remove all long lines. |
| [`removeLongLine`](#removelongline) | Remove a long line. |
| [`addLongLine`](#addlongline) | Add a long line. |
| [`setLongLine`](#setlongline) | Set a long line. |

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getLongLines

Get an array of `DSLineSegment` as the long lines.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable NSArray<DSLineSegment*>*)getLongLines;
```
2. 
```swift
func getLongLines() -> [LineSegment]?
```

**Return Value**

The array of `DSLineSegment` as the long lines.

### getCount

Get the number of long lines.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)getCount;
```
2. 
```swift
func getCount() -> Int
```

**Return Value**

The number of long lines.

### getLongLine

Get the long line at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable DSLineSegment*)getLongLine:(NSInteger)index;
```
2. 
```swift
func getLongLine(_ index: Int) -> LineSegment?
```

**Parameters**

`[in] index`: The index of the long line.

**Return Value**

A `DSLineSegment` object as the long line at the specified index.

### removeAllLongLines

Remove all long lines.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(void)removeAllLongLines;
```
2. 
```swift
func removeAllLongLines()
```

### removeLongLine

Remove the long line at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)removeLongLine:(NSInteger)index;
```
2. 
```swift
func removeLongLine(_ index: Int) -> Int
```

**Parameters**

The index of the long line to be removed.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### addLongLine

Add a long line.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)addLongLine:(DSLineSegment*)line
  matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func addLongLine(_ line: LineSegment, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`[in] line`: The long line to be added.

`[in] matrixToOriginalImage`: The transformation matrix of the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### setLongLine

Set the long line at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)setLongLine:(NSInteger)index
                   line:(DSLineSegment*)line
  matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func setLongLine(_ index: Int, line: LineSegment, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`[in] index`: The index of the long line.

`[in] line`: The long line to be set.

`[in] matrixToOriginalImage`: The transformation matrix of the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
