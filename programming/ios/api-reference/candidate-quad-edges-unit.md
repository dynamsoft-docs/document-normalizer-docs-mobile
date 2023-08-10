---
layout: default-layout
Title: DSCandidateQuadEdgesUnit - Dynamsoft Document Normalizer SDK API Reference
Description: The class DSCandidateQuadEdgesUnit represents an intermediate result unit whose type is candidate quad edges.
Keywords: candidate quad edges, intermediate result unit, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSCandidateQuadEdgesUnit

The `DSCandidateQuadEdgesUnit` class represents an intermediate result unit whose type is candidate quad edges.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSCandidateQuadEdgesUnit: DSIntermediateResultUnit
```
2. 
```swift
class CandidateQuadEdgesUnit: IntermediateResultUnit
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`candidateQuadEdges`](#candidatequadedges) | *NSArray&lt;DSEdge \* &gt; \** | An array of edges. It includes all edges that candidate quadrilaterals assembling. |

### candidateQuadEdges

An array of edges. It includes all edges that candidate quadrilaterals assembling.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable, copy) NSArray<DSEdge *> * candidateQuadEdges;
```
2. 
```swift
var candidateQuadEdges: [Edge]? { get set }
```
