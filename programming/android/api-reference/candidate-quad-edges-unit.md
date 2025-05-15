---
layout: default-layout
title: CandidateQuadEdgesUnit - Dynamsoft Document Normalizer Android SDK API Reference
description: The class CandidateQuadEdgesUnit represents an intermediate result unit whose type is candidate quad edges.
keywords: candidate quad edges, intermediate result unit, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# CandidateQuadEdgesUnit

The `CandidateQuadEdgesUnit` class represents an intermediate result unit whose type is candidate quad edges.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftCaptureVisionBundle.aar

```java
class CandidateQuadEdgesUnit extends IntermediateResultUnit
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

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getCandidateQuadEdges

Get an array of edges. It includes all edges that candidate quadrilaterals assembling.

```java
Edge[] getCandidateQuadEdges();
```

**Return Value**

Get an array of [`Edge`]({{site.dcv_android_api}}core/basic-structures/edge.html).

### getCount

Get the number of edges.

```java
int getCount();
```

**Return Value**

The number of edges.

### getCandidateQuadEdge

Get the `Edge` object at the specified index.

```java
Edge getCandidateQuadEdge(int index);
```

**Parameters**

`[in] index`: The index of the edge.

**Return Value**

The `Edge` object as the specified edge.

### removeAllCandidateQuadEdges

Remove all edges.

```java
void removeAllCandidateQuadEdges();
```

### removeCandidateQuadEdge

Remove the `Edge` object at the specified index.

```java
int removeCandidateQuadEdge(int index);
```

**Parameters**

`[in] index`: The index of the edge.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### addCandidateQuadEdge

Add a new `Edge` object to the unit.

```java
int addCandidateQuadEdge(Edge edge, Matrix matrixToOriginalImage);
```

**Parameter**

`[in] edge`: The edge to be added.

`[in] matrixToOriginalImage`: The matrix to the original image.

### setCandidateQuadEdge

Set the `Edge` object at the specified index.

```java
int setCandidateQuadEdge(int index, Edge edge, Matrix matrixToOriginalImage);
```

**Parameters**

`[in] index`: The index of the edge.

`[in] edge`: The edge to be set.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
