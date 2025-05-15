---
layout: default-layout
title: LogicLinesUnit - Dynamsoft Document Normalizer Android SDK API Reference
description: The class LogicLinesUnit of DDN Android represents an intermediate result unit containing logic lines. It inherits from the IntermediateResultUnit class.
keywords: logic lines, intermediate result unit, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# LogicLinesUnit

The `LogicLinesUnit` class represents an intermediate result unit containing logic lines. It inherits from the `IntermediateResultUnit` class.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftCaptureVisionBundle.aar

```java
class LogicLinesUnit extends IntermediateResultUnit
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

```java
LineSegment[] getLogicLines();
```

**Return Value**

Returns an array of `LineSegment` as the logic lines.

### getCount

Gets the number of logic lines in the unit.

```java
int getCount();
```

**Return Value**

Returns the number of logic lines in the unit.

### getLogicLine

Gets a logic line at the specified index.

```java
LineSegment getLogicLine(int index);
```

**Parameters**

`index` The index of the logic line.

**Return Value**

Returns a reference to the `LineSegment` object at the specified index.

### removeAllLogicLines

Removes all logic lines.

```java
void removeAllLogicLines();
```

### removeLogicLine

Removes the logic line at the specified index.

```java
int removeLogicLine(int index);
```

**Parameters**

`index` The index of the logic line to remove.

**Return Value**

Returns 0 if successful, otherwise returns a negative value.

### addLogicLine

Adds a logic line.

```java
int addLogicLine(LineSegment logicLine, Matrix matrixToOriginalImage);
```

**Parameters**

`logicLine` The logic line to add.

`matrixToOriginalImage` The matrix to the original image (3x3 matrix).

**Return Value**
Returns 0 if successful, otherwise returns a negative value.

### setLogicLine

Sets the logic line at the specified index.

```java
int setLogicLine(int index, LineSegment logicLine, Matrix matrixToOriginalImage);
```

**Parameters**

`index` The index of the logic line to set.

`logicLine` The logic line to set.

`matrixToOriginalImage` The matrix to the original image (3x3 matrix).

**Return Value**

Returns 0 if successful, otherwise returns a negative value.
