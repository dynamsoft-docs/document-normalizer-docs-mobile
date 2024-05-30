---
layout: default-layout
title: LongLinesUnit - Dynamsoft Document Normalizer Android SDK API Reference
description: The class LongLinesUnit represents an intermediate result unit whose type is long lines. Line segments that are located in the same line are extended and merged to form a long line.
keywords: long lines, intermediate result unit, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# LongLinesUnit

The `LongLinesUnit` class represents an intermediate result unit whose type is long lines. Line segments that are located in the same line are extended and merged to form a long line.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class LongLinesUnit extends IntermediateResultUnit
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getLongLines`](#getlonglines) | Get an array of [`LineSegment`]({{site.dcv_android_api}}core/basic-structures/line-segment.html) as the long lines. |
| [`getCount`](#getcount) | Get the number of long lines. |
| [`getLongLine`](#getlongline) | Get a long line. |
| [`removeAllLongLines`](#removealllonglines) | Remove all long lines. |
| [`removeLongLine`](#removelongline) | Remove a long line. |
| [`addLongLine`](#addlongline) | Add a long line. |
| [`setLongLine`](#setlongline) | Set a long line. |

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getLongLines

Get an array of [`LineSegment`]({{site.dcv_android_api}}core/basic-structures/line-segment.html) as the long lines.

```java
LineSegment[] getLongLines();
```

**Return Value**

The array of [`LineSegment`]({{site.dcv_android_api}}core/basic-structures/line-segment.html) as the long lines.

### getCount

Get the number of long lines.

```java
int getCount();
```

**Return Value**

The number of long lines.

### getLongLine

Get the long line at the specified index.

```java
LineSegment getLongLine(int index);
```

**Parameters**

`[in] index`: The index of the long line.

**Return Value**

A `LineSegment` object as the long line at the specified index.

### removeAllLongLines

Remove all long lines.

```java
void removeAllLongLines();
```

### removeLongLine

Remove the long line at the specified index.

```java
int removeLongLine(int index);
```

**Parameters**

The index of the long line to be removed.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### addLongLine

Add a long line.

```java
int addLongLine(LineSegment line, Matrix matrixToOriginalImage);
```

**Parameters**

`[in] line`: The long line to be added.

`[in] matrixToOriginalImage`: The transformation matrix from the original image to the current image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### setLongLine

Set the long line at the specified index.

```java
int setLongLine(int index, LineSegment line,  Matrix matrixToOriginalImage);
```

**Parameters**

`[in] index`: The index of the long line to be set.

`[in] line`: A `LineSegment` object as the long line to be set.

`[in] matrixToOriginalImage`: The transformation matrix from the original image to the current image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
