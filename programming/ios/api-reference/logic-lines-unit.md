---
layout: default-layout
title: LogicLinesUnit - Dynamsoft Document Normalizer iOS SDK API Reference
description: The class LogicLinesUnit of DDN iOS represents an intermediate result unit containing logic lines. It inherits from the IntermediateResultUnit class..
keywords: logic lines, intermediate result unit, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# LogicLinesUnit

The `LogicLinesUnit` class represents an intermediate result unit containing logic lines. It inherits from the `IntermediateResultUnit` class.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSLogicLinesUnit: DSIntermediateResultUnit
```
2. 
```swift
class LogicLinesUnit: IntermediateResultUnit
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getLogicLines`](#getlogiclines) | Get an array of [`LineSegment`]({{site.dcv_android_api}}core/basic-structures/line-segment.html) as the logic lines. |
| [`getCount`](#getcount) | Get the number of logic lines. |
| [`getLogicLine`](#getlogicline) | Get a logic line. |
| [`removeAllLogicLines`](#removealllogiclines) | Remove all logic lines. |
| [`removeLogicLine`](#removelogicline) | Remove a logic line. |
| [`addLogicLine`](#addlogicline) | Add a logic line. |
| [`setLogicLine`](#setlogicline) | Set a logic line. |

### getLogicLines

Get an array of `LineSegment` as the logic lines.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable NSArray<DSLineSegment*>*)getLogicLines;
```
2. 
```swift
func getLogicLines() -> [LineSegment]?
```

**Return Value**

Returns an array of `LineSegment` as the logic lines.

### getCount

Gets the number of logic lines in the unit.

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

Returns the number of logic lines in the unit.

### getLogicLine

Gets a logic line at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable DSLineSegment*)getLogicLine:(NSInteger)index;
```
2. 
```swift
func getLogicLine(_ index: Int) -> LineSegment?
```

**Parameters**

`index` The index of the logic line.

**Return Value**

Returns a reference to the `LineSegment` object at the specified index.

### removeAllLogicLines

Removes all logic lines.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(void)removeAllLogicLines;
```
2. 
```swift
func removeAllLogicLines()
```

### removeLogicLine

Removes the logic line at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)removeLogicLine:(NSInteger)index;
```
2. 
```swift
func removeLogicLine(_ index: Int) -> Int
```

**Parameters**

`index` The index of the logic line to remove.

**Return Value**

Returns 0 if successful, otherwise returns a negative value.

### addLogicLine

Adds a logic line.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)addLogicLine:(DSLineSegment*)line
   matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func addLogicLine(_ line: LineSegment, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`logicLine` The logic line to add.

`matrixToOriginalImage` The matrix to the original image (3x3 matrix).

**Return Value**
Returns 0 if successful, otherwise returns a negative value.

### setLogicLine

Sets the logic line at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)setLogicLine:(NSInteger)index
                    line:(DSLineSegment*)line
   matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func setLogicLine(_ index: Int, line: LineSegment, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`index` The index of the logic line to set.

`logicLine` The logic line to set.

`matrixToOriginalImage` The matrix to the original image (3x3 matrix).

**Return Value**

Returns 0 if successful, otherwise returns a negative value.
