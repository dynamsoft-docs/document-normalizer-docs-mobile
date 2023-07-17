---
layout: default-layout
Title: CandidateQuadEdgesUnit - Dynamsoft Document Imaging SDK API Reference
Description: The class CandidateQuadEdgesUnit represents an intermediate result unit whose type is candidate quad edges.
Keywords: candidate quad edges, intermediate result unit, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# CandidateQuadEdgesUnit

The `CandidateQuadEdgesUnit` class represents an intermediate result unit whose type is candidate quad edges.

## Definition

*Assembly:* package com.dynamsoft.ddn

```java
class CandidateQuadEdgesUnit extends IntermediateResultUnit
```

## Attributes

| Methods | Description |
| ------- | ----------- |
| [`getCandidateQuadEdges`](#getcandidatequadedges) | Get an array of edges. It includes all edges that candidate quadrilaterals assembling. |

### getCandidateQuadEdges

Get an array of edges. It includes all edges that candidate quadrilaterals assembling.

```java
Edge[] getCandidateQuadEdges();
```

**Return Value**

Get an array of `Edges`.
