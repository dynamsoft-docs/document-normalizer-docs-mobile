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

## Methods Summary

| Methods | Description |
| ---------- | ----------- |
| [`getLongLines`](#getlonglines) | Get an array of [`LineSegment`]({{site.dcv_android_api}}core/basic-structures/line-segment.html) as the long lines. |

### getLongLines

Get an array of [`LineSegment`]({{site.dcv_android_api}}core/basic-structures/line-segment.html) as the long lines.

```java
LineSegment[] getLongLines();
```

**Return Value**

The array of [`LineSegment`]({{site.dcv_android_api}}core/basic-structures/line-segment.html) as the long lines.
