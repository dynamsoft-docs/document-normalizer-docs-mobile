---
layout: default-layout
title: CornersUnit - Dynamsoft Document Normalizer Android SDK API Reference
description: The class CornersUnit represents an intermediate result unit whose type is corners.
keywords: corners unit, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# CornersUnit

The `CornersUnit` class represents an intermediate result unit whose type is corners.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class CornersUnit extends IntermediateResultUnit
```

## Methods Summary

| Methods | Description |
| ------- | ----------- |
| [`getCorners`](#getcorners) | Get an array of corners. It includes all corners that participate quadrilaterals assembling. |
| [`getCount`](#getcount) | Get the number of corners. |
| [`getCorner`](#getcorner) | Get a corner. |
| [`removeAllCorners`](#removeallcorners) | Remove all corners. |
| [`removeCorner`](#removecorner) | Remove a corner. |
| [`addCorner`](#addcorner) | Add a corner. |
| [`setCorner`](#setcorner) | Set a corner. |

### getCorners

Get an array of corners. It includes all corners that participate quadrilaterals assembling.

```java
Corner[] getCorners();
```

**Return Value**

Get an array of [`Corner`]({{site.dcv_android_api}}core/basic-structures/corner.html).

### getCount

Get the number of corners.

```java
int getCount();
```

**Return Value**

The number of corners.

### getCorner

Get the `Corner` object at the specified index.

```java
Corner getCorner(int index);
```

**Parameters**

`[in] index`: The index of the corner.

**Return Value**

A `Corner` object as the specified corner.

### removeAllCorners

Remove all corners.

```java
void removeAllCorners();
```

### removeCorner

Remove the corner at the specified index.

```java
int removeCorner(int index);
```

**Parameters**

`[in] index`: The index of the corner.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### addCorner

Add a new `Corner` object to the unit.

```java
int addCorner(Corner corner, Matrix matrixToOriginalImage);
```

**Parameters**

`[in] corner`: The `Corner` object to be added.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### setCorner

Set the `Corner` object at the specified index.

```java
int setCorner(int index, Corner corner, Matrix matrixToOriginalImage);
```

**Parameters**

`[in] index`: The index of the corner.

`[in] corner`: The `Corner` object to be set.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
