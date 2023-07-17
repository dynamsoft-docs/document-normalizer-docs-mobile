---
layout: default-layout
Title: LongLinesUnit - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class LongLinesUnit of Dynamsoft Document Normalizer module represents an intermediate result unit whose type is long lines. Line segments that are located in the same line are extended and merged to form a long line.
Keywords: long lines, intermediate result unit, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# LongLinesUnit

The `LongLinesUnit` class represents an intermediate result unit whose type is long lines. Line segments that are located in the same line are extended and merged to form a long line.

## Definition

*Assembly:* package com.dynamsoft.ddn

```java
class LongLinesUnit extends IntermediateResultUnit
```

## Attributes

| Attributes | Description |
| ---------- | ----------- |
| [`getLongLines`](#getlonglines) | Get an array of `LineSegments` as the long lines. |

### getLongLines

Get an array of `LineSegments` as the long lines.

```java
LineSegment[] getLongLines();
```
