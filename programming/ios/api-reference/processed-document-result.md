---
layout: default-layout
title: ProcessedDocumentResult - Dynamsoft Document Normalizer iOS SDK API Reference
description: The class ProcessedDocumentResult represents a collection of captured result items whose type are normalized images.
keywords: normalized images, objective-c, objc, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# ProcessedDocumentResult

The class `ProcessedDocumentResult` represents a collection of captured result items whose types are detected boundaries, deskew images or enhanced images.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSProcessedDocumentResult : DSCapturedResultBase
```
2. 
```swift
class ProcessedDocumentResult : CapturedResultBase
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`deskewedImageResultItems`](#deskewedimageresultitems) | *NSArray<DSDeskewedImageResultItem \*>* | The deskew images represented by an array of [`DeskewedImageResultItem`](deskewed-image-result-item.md). |
| [`detectedQuadResultItems`](#detectedquadresultitems) | *NSArray<DSDetectedImageResultItem \*>* | The detected boundaries represented by an array of [`DetectedImageResultItem`](detected-image-result-item.md). |
| [`enhancedImageResultItems`](#enhancedimageresultitems) | *NSArray<DSEnhancedImageResultItem \*>* | The enhanced images represented by an array of [`EnhancedImageResultItem`](enhanced-image-result-item.md). |

The following attributes are inherited from [`DSCapturedResultBase`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-base.html):

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`originalImageHashId`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-base.html#originalimagehashid) | *NSString \** | The hash id of the original image. |
| [`originalImageTag`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-base.html#originalimagetag) | *DSImageTag \** | The [DSImageTag](image-tag.md) of the original image. |
| [`rotationTransformMatrix`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-base.html#rotationtransformmatrix) | *CGAffineTransform* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`errorCode`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-base.html#errorcode) | *NSInteger* | Get the error code of this result. |
| [`errorMessage`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-base.html#errormessage) | *NSString \** | Get the error message of this result. |

### deskewedImageResultItems

The deskew images represented by an array of [`DSDeskewedImageResultItem`](deskewed-image-result-item.md).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) NSArray<DSDeskewedImageResultItem *>* deskewedImageResultItems;
```
2. 
```swift
var deskewedImageResultItems: [DSDeskewedImageResultItem]? { get }
```

**Return Value**

The array of the deskewed image result items.

### detectedQuadResultItems

The detected boundaries represented by an array of [`DSDetectedImageResultItem`](detected-image-result-item.md).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) NSArray<DSDetectedQuadResultItem*>* detectedQuadResultItems;
```
2. 
```swift
var detectedQuadResultItems: [DSDetectedQuadResultItem]? { get }
```

**Return Value**

The array of the detected quad result items.

### enhancedImageResultItems

The enhanced images represented by an array of [`DSEnhancedImageResultItem`](enhanced-image-result-item.md).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) NSArray<DSEnhancedImageResultItem*>* enhancedImageResultItems;
```
2. 
```swift
var enhancedImageResultItems: [DSEnhancedImageResultItem]? { get }
```

**Return Value**

The array of the enhanced image result items.
