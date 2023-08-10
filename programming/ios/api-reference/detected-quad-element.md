---
layout: default-layout
Title: DSDetectedQuadElement - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class DSDetectedQuadElement of Dynamsoft Document Normalizer module represents a detected quadrilateral element, which is an intermediate result in the document scanning process.
Keywords: detected quad, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSDetectedQuadElement

The `DSDetectedQuadElement` class represents a detected quadrilateral element, which is an intermediate result in the document scanning process. It is a subclass of `DSRegionObjectElement`.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.framework

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
| [`confidenceAsDocumentBoundary`](#confidenceasdocumentboundary) | *NSInteger* | The confidence of the quadrilateral to be a document boundary. |

## confidenceAsDocumentBoundary

The confidence of the quadrilateral to be a document boundary.

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
