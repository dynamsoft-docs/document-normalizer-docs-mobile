---
layout: default-layout
Title: DSDetectedQuadResultItem - Dynamsoft Document Normalizer module iOS Edition API Reference
Description: The class DSDetectedQuadResultItem of Dynamsoft Document Normalizer module represents a captured result whose type is detected quads, which contains the location and confidence as a document boundary.
Keywords: detected quads, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSDetectedQuadResultItem

The `DSDetectedQuadResultItem` class represents a captured result whose type is detected quads, which contains the location and confidence as a document boundary.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.framework

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
| [`confidenceAsDocumentBoundary`](#confidenceasdocumentboundary) | *NSInteger* | The confidence of current object as a document boundary. |

### location

A DSQuadrilateral object as the location of current object.

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

The confidence of current object as a document boundary.

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
