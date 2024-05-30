---
layout: default-layout
title: DSDetectedQuadElement - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSDetectedQuadElement of Dynamsoft Document Normalizer module represents a detected quadrilateral element, which is an intermediate result in the document scanning process.
keywords: detected quad, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSDetectedQuadElement

The `DSDetectedQuadElement` class represents a detected quadrilateral element, which is an intermediate result in the document scanning process. It is a subclass of `DSRegionObjectElement`.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSDetectedQuadElement: DSRegionObjectElement
```
2. 
```swift
class DetectedQuadElement: RegionObjectElement
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`confidenceAsDocumentBoundary`](#confidenceasdocumentboundary) | *NSInteger* | The confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document. |

## confidenceAsDocumentBoundary

The confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger confidenceAsDocumentBoundary;
```
2. 
```swift
var confidenceAsDocumentBoundary: Int { get }
```
