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

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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

## Methods

| Methods | Description |
| ------- | ----------- |
| [`getConfidenceAsDocumentBoundary`](#getconfidenceasdocumentboundary) | Returns the confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document. |

The following methods are inherited from class [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-ios.md -%}

## getConfidenceAsDocumentBoundary

Returns the confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSUInteger)getConfidenceAsDocumentBoundary;
```
2. 
```swift
func getConfidenceAsDocumentBoundary() -> Int
```
