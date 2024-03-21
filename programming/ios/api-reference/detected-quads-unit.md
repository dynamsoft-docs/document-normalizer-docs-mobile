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

## Methods

| Methods | Description |
| ------- | ----------- |
| [`getDetectedQuads`](#getdetectedquads) | Get an array of `DSDetectedQuadElement` that represent all the detected quadrilaterals. |
| [`getCount`](#getcount) | Get the number of detected quadrilaterals. |
| [`getDetectedQuad`](#getdetectedquad) | Get the `DSDetectedQuadElement` at the specified index. |
| [`removeAllDetectedQuads`](#removealldetectedquads) | Remove all detected quadrilaterals. |
| [`removeDetectedQuad`](#removedetectedquad) | Remove the `DSDetectedQuadElement` at the specified index. |
| [`addDetectedQuad`](#adddetectedquad) | Add a new `DSDetectedQuadElement` to the unit. |
| [`setDetectedQuad`](#setdetectedquad) | Set the `DSDetectedQuadElement` at the specified index. |

### getDetectedQuads

Get an array of `DSDetectedQuadElement` that represent all the detected quadrilaterals.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable NSArray<DSDetectedQuadElement*>*)getDetectedQuads;
```
2. 
```swift
func getDetectedQuads() -> [DetectedQuadElement]?
```

**Return Value**

An array of `DSDetectedQuadElement` that represent all the detected quadrilaterals.

### getCount

Get the number of detected quadrilaterals.

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

The number of detected quadrilaterals.

### getDetectedQuad

Get the `DSDetectedQuadElement` at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable DSDetectedQuadElement*)getDetectedQuad:(NSInteger)index;
```
2. 
```swift
func getDetectedQuad(index: Int) -> DetectedQuadElement?
```

**Parameters**

`[in] index`: The index of the detected quadrilateral.

**Return Value**

The `DSDetectedQuadElement` object at the specified index. If the index is out of range, `nil` will be returned.

### removeAllDetectedQuads

Remove all detected quadrilaterals.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(void)removeAllDetectedQuads;
```
2. 
```swift
func removeAllDetectedQuads()
```

### removeDetectedQuad

Remove the `DSDetectedQuadElement` at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)removeDetectedQuad:(NSInteger)index;
```
2. 
```swift
func removeDetectedQuad(_ index: Int) -> Int
```

**Parameters**

`[in] index`: The index of the detected quadrilateral.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### addDetectedQuad

Add a new `DSDetectedQuadElement` to the unit.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)addDetectedQuad:(DSDetectedQuadElement*)element
      matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func addDetectedQuad(_ element: DetectedQuadElement, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`[in] element`: The detected quadrilateral to be added.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### setDetectedQuad

Set the `DSDetectedQuadElement` at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)setDetectedQuad:(NSInteger)index
                    element:(DSDetectedQuadElement*)element
      matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func setDetectedQuad(_ index: Int, element: DetectedQuadElement, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`[in] index`: The index of the detected quadrilateral.

`[in] element`: The detected quadrilateral to be set.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
