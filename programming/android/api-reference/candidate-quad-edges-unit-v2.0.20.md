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

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class CandidateQuadEdgesUnit extends IntermediateResultUnit
```

## Methods

| Methods | Description |
| ------- | ----------- |
| [`getCandidateQuadEdges`](#getcandidatequadedges) | Get an array of edges. It includes all edges that candidate quadrilaterals assembling. |

### getCandidateQuadEdges

Get an array of edges. It includes all edges that candidate quadrilaterals assembling.

```java
Edge[] getCandidateQuadEdges();
```

**Return Value**

Get an array of [`Edge`]({{site.dcv_android_api}}core/basic-structures/edge.html).
