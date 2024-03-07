---
layout: default-layout
title: DetectedQuadsUnit - Dynamsoft Document Normalizer Android SDK API Reference
description: The class DetectedQuadsUnit represents an intermediate result unit whose type is detected quads. It is inherited from the IntermediateResultUnit class.
keywords: detected quads, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DetectedQuadsUnit

The `DetectedQuadsUnit` class represents an intermediate result unit whose type is detected quads. It is inherited from the `IntermediateResultUnit` class.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class DetectedQuadsUnit extends IntermediateResultUnit
```

## Methods Summary

| Methods | Description |
| ---------- | ----------- |
| [`getDetectedQuads`](#getdetectedquads) | Gets an array of `DetectedQuadElement` objects, each containing the information of a single detected quadrilateral. |
| [`getCount`](#getcount) | Gets the number of detected quadrilaterals. |
| [`getDetectedQuad`](#getdetectedquad) | Gets a detected quadrilateral. |
| [`removeAllDetectedQuads`](#removedetectedquads) | Removes all detected quadrilaterals. |
| [`removeDetectedQuad`](#removedetectedquad) | Removes a detected quadrilateral. |
| [`addDetectedQuad`](#adddetectedquad) | Adds a detected quadrilateral. |
| [`setDetectedQuad`](#setdetectedquad) | Sets a detected quadrilateral. |

### getDetectedQuads

Gets an array of `DetectedQuadElement` objects, each containing the information of a single detected quadrilateral.

```java
DetectedQuadElement[] getDetectedQuads()
```

**Return Value**

The array of [`DetectedQuadElement`](./detected-quad-element.md).

### getCount

Gets the number of detected quadrilaterals.

```java
int getCount()
```

**Return Value**

The number of detected quadrilaterals.

### getDetectedQuad

Gets the `DetectedQuadElement` at the specified index.

```java
DetectedQuadElement getDetectedQuad(int index)
```

**Return Value**

A [`DetectedQuadElement`](./detected-quad-element.md) object that represents the detected quadrilateral.

### removeAllDetectedQuads

Removes all detected quadrilaterals.

```java
void removeAllDetectedQuads()
```

### removeDetectedQuad

Removes the detected quadrilateral at the specified index.

```java
int removeDetectedQuad(int index)
```

**Parameters**

`[in] index`: The index of the quadrilateral to remove.

**Return Value**

Returns the ErrorCode if failed. otherwise, returns 0.

### addDetectedQuad

Adds a [`DetectedQuadElement`](./detected-quad-element.md) to the unit.

```java
int addDetectedQuad(DetectedQuadElement element, Matrix matrixToOriginalImage)
```

**Parameters**

`[in] element`: The [`DetectedQuadElement`](./detected-quad-element.md) object to add.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### setDetectedQuad

Sets the [`DetectedQuadElement`](./detected-quad-element.md) at the specified index.

```java
int setDetectedQuad(int index, DetectedQuadElement element, Matrix matrixToOriginalImage)
```

**Parameters**

`[in] index`: The index of the quadrilateral to set.

`[in] element`: The [`DetectedQuadElement`](./detected-quad-element.md) object to set.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
