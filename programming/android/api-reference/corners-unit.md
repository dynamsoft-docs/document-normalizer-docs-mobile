---
layout: default-layout
Title: CornersUnit - Dynamsoft Document Normalizer Android SDK API Reference
Description: The class CornersUnit represents an intermediate result unit whose type is corners.
Keywords: corners unit, java, kotlin
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

### getCorners

Get an array of corners. It includes all corners that participate quadrilaterals assembling.

```java
Corner[] getCorners();
```

**Return Value**

Get an array of [`Corner`]({{site.dcv_android_api}}core/basic-structures/corner.html).