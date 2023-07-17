---
layout: default-layout
Title: CornersUnit - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class CornersUnit of Dynamsoft Document Normalizer module represents an intermediate result unit whose type is corners.
Keywords: corners unit, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# CornersUnit

The `CornersUnit` class represents an intermediate result unit whose type is corners.

## Definition

*Assembly:* package com.dynamsoft.ddn

```java
class CornersUnit extends IntermediateResultUnit
```

## Attributes

| Methods | Description |
| ------- | ----------- |
| [`getCorners`](#getcorners) | Get an array of corners. It includes all corners that participate quadrilaterals assembling. |

### getCorners

Get an array of corners. It includes all corners that participate quadrilaterals assembling.

```java
Corner[] getCorners();
```
