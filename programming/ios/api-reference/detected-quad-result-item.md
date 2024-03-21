---
layout: default-layout
title: DSDetectedQuadResultItem - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSDetectedQuadResultItem of Dynamsoft Document Normalizer module represents a captured result whose type is detected quads, which contains the location and confidence as a document boundary.
keywords: detected quads, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSDetectedQuadResultItem

The `DetectedQuadResultItem` class is an extension of the [`DSCapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html) that represents a detected quadrilateral. This is the most basic unit of a detected quadrilateral, one of the captured result types that the Capture Vision Router can output.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NS_SWIFT_NAME(DetectedQuadResultItem)
@interface DSDetectedQuadResultItem: DSCapturedResultItem
```
2. 
```swift
class DetectedQuadResultItem: CapturedResultItem
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`location`](#location) | *DSQuadrilateral* | A DSQuadrilateral object as the location of current object. |
| [`confidenceAsDocumentBoundary`](#confidenceasdocumentboundary) | *NSInteger* | TThe confidence score of the detected quadrilateral's boundary, measuring the certainty that the detected quadrilateral represents the boundary of a document. |

### location

A [DSQuadrilateral]({{ site.dcv_ios_api }}core/basic-structures/quadrilateral.html) object that represents the location of the detected quadrilateral within the image or frame.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) DSQuadrilateral *location;
```
2. 
```swift
var location: DSQuadrilateral? { get }
```

### confidenceAsDocumentBoundary

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
