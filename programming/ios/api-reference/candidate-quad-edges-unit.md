---
layout: default-layout
title: DSCandidateQuadEdgesUnit - Dynamsoft Document Normalizer SDK API Reference
description: The class DSCandidateQuadEdgesUnit represents an intermediate result unit whose type is candidate quad edges.
keywords: candidate quad edges, intermediate result unit, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSCandidateQuadEdgesUnit

The `DSCandidateQuadEdgesUnit` class represents an intermediate result unit whose type is candidate quad edges.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSCandidateQuadEdgesUnit: DSIntermediateResultUnit
```
2. 
```swift
class CandidateQuadEdgesUnit: IntermediateResultUnit
```

## Methods

| Methods | Description |
| ------- | ----------- |
| [`getCandidateQuadEdges`](#getcandidatequadedges) | Get an array of edges. It includes all edges that candidate quadrilaterals assembling. |
| [`getCount`](#getcount) | Get the number of edges. |
| [`getCandidateQuadEdge`](#getcandidatequadedge) | Get an edge. |
| [`removeAllCandidateQuadEdges`](#removeallcandidatequadedges) | Remove all edges. |
| [`removeCandidateQuadEdge`](#removecandidatequadedge) | Remove an edge. |
| [`addCandidateQuadEdge`](#addcandidatequadedge) | Add an edge. |
| [`setCandidateQuadEdge`](#setcandidatequadedge) | Set an edge. |

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getCandidateQuadEdges

Get an array of edges. It includes all edges that candidate quadrilaterals assembling.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable NSArray<DSEdge *> *)getCandidateQuadEdges;
```
2. 
```swift
func getCandidateQuadEdges() -> [DSEdge]?
```

**Return Value**

Returns an array of edges.

### getCount

Get the number of edges.

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
func getCount() -> NSInteger
```

**Return Value**

Returns the number of edges.

### getCandidateQuadEdge

Get the `DSEdge` object at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable DSEdge *)getCandidateQuadEdge:(NSInteger)index;
```
2. 
```swift
func getCandidateQuadEdge(_ index: Int) -> DSEdge?
```

**Parameters**

`[in] index`: The index of the edge.

**Return Value**

Returns the `DSEdge` object as the specified edge.

### removeAllCandidateQuadEdges

Remove all edges.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(void)removeAllCandidateQuadEdges;
```
2. 
```swift
func removeAllCandidateQuadEdges()
```

### removeCandidateQuadEdge

Remove the `DSEdge` object at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)removeCandidateQuadEdge:(NSInteger)index;
```
2. 
```swift
func removeCandidateQuadEdge(_ index: Int) -> NSInteger
```

**Parameters**

`[in] index`: The index of the edge.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### addCandidateQuadEdge

Add an edge.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)addCandidateQuadEdge:(DSEdge *)edge
           matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func addCandidateQuadEdge(_ edge: DSEdge, matrixToOriginalImage: CGAffineTransform) -> NSInteger
```

**Parameters**

`[in] edge`: The edge to be added.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### setCandidateQuadEdge

Set the `DSEdge` object at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)setCandidateQuadEdge:(NSInteger)index 
                            edge:(DSEdge *)edge
           matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func setCandidateQuadEdge(_ index: Int, edge: DSEdge, matrixToOriginalImage: CGAffineTransform) -> NSInteger
```

**Parameters**

`[in] index`: The index of the edge.

`[in] edge`: The edge to be set.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
