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

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getCorners`](#getcorners) | Get an array of corners. It includes all corners that participate quadrilaterals assembling. |
| [`getCount`](#getcount) | Get the number of corners. |
| [`getCorner`](#getcorner) | Get a corner. |
| [`removeAllCorners`](#removeallcorners) | Remove all corners. |
| [`removeCorner`](#removecorner) | Remove a corner. |
| [`addCorner`](#addcorner) | Add a corner. |
| [`setCorner`](#setcorner) | Set a corner. |

### getCorners

Get an array of `DSCorner` that represent all the assembled corners. The corners will participate assembling.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable NSArray<DSCorner*>*)getCorners;
```
2. 
```swift
func getCorners() -> [Corner]?
```

**Return Value**

An array of `DSCorner` as the assembled corners.

### getCount

Get the number of corners.

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

The number of corners.

### getCorner

Get the corner at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable DSCorner*)getCorner:(NSInteger)index;
```
2. 
```swift
func getCorner(_ index: Int) -> Corner?
```

**Parameters**

`[in] index`: The index of the corner.

**Return Value**

The corner at the specified index.

### removeAllCorners

Remove all corners.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(void)removeAllCorners;
```
2. 
```swift
func removeAllCorners()
```

### removeCorner

Remove the corner at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)removeCorner:(NSInteger)index;
```
2. 
```swift
func removeCorner(_ index: Int) -> Int
```

**Parameters**

`[in] index`: The index of the corner to be removed.

**Return Value**

The index of the removed corner.

### addCorner

Add a corner.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)addCorner:(DSCorner*)corner
matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func addCorner(_ corner: Corner, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`[in] corner`: The corner to be added.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### setCorner

Set the corner at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)setCorner:(NSInteger)index
               corner:(DSCorner*)corner
matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func setCorner(_ index: Int, corner: Corner, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`[in] index`: The index of the corner to be set.

`[in] corner`: The corner to be set.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
