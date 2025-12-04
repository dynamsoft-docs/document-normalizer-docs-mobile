---
layout: default-layout
title: ProcessedDocumentResult - Dynamsoft Capture Vision React Native SDK API Reference
description: Interface ProcessedDocumentResult of Dynamsoft Capture Vision React Native represents a collection of captured result items whose types are detected boundaries, deskew images or enhanced images.
keywords: detected boundaries, deskew images, enhanced images, js
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# ProcessedDocumentResult

Interface `ProcessedDocumentResult` represents a collection of captured result items whose types are detected boundaries, deskew images or enhanced images.

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```js
interface ProcessedDocumentResult extends CapturedResultBase
```

## Properties

| Property | Types | Description |
| -------- | ----- | ----------- |
| [`DeskewedImageResultItems`](#deskewedimageresultitems) | *Array\<DeskewedImageResultItem\>* | An array of [`DeskewedImageResultItem`](deskewed-image-result-item.md) objects, where each `DeskewedImageResultItem` represents a single deskewed image. |
| [`DetectedQuadResultItems`](#detectedquadresultitems) | *Array\<DetectedQuadResultItem\>* | An array of [`DetectedQuadResultItem`](detected-quad-result-item.md) objects, where each `DetectedQuadResultItem` represents a single detected boundary. |
| [`EnhancedImageResultItems`](#enhancedimageresultitems) | *Array\<EnhancedImageResultItem\>* | A array of [`EnhancedImageResultItem`](enhanced-image-result-item.md) objects, where each `EnhancedImageResultItem` represents a single enhnanced image. |

The following properties are inherited from [`CapturedResultBase`]({{ site.dcv_react_native_api }}core/captured-result-base.html):

| Property | Types | Description |
| -------- | ----- | ----------- |
| [`originalImageHashId`]({{ site.dcv_react_native_api }}core/captured-result-base.html#originalimagehashid) | *String* | The hash id of the original image. |
| [`rotationTransformMatrix`]({{ site.dcv_react_native_api }}core/captured-result-base.html#rotationtransformmatrix) | *Matrix4* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`errorCode`]({{ site.dcv_react_native_api }}core/captured-result-base.html#errorcode) | *int* | The error code of this result. |
| [`errorMessage`]({{ site.dcv_react_native_api }}core/captured-result-base.html#errormessage) | *String* | The error message of this result. |

### deskewedImageResultItems

An array of [`DeskewedImageResultItem`](deskewed-image-result-item.md) objects, where each `DeskewedImageResultItem` represents a single deskewed image.

```js
deskewedImageResultItems?: Array<DeskewedImageResultItem>;
```

### detectedQuadResultItems

An array of [`DetectedQuadResultItem`](detected-quad-result-item.md) objects, where each `DetectedQuadResultItem` represents a single detected boundary.

```js
detectedQuadResultItems?: Array<DetectedQuadResultItem>;
```

### enhancedImageResultItems

A array of [`EnhancedImageResultItem`](enhanced-image-result-item.md) objects, where each `EnhancedImageResultItem` represents a single enhnanced image.

```js
enhancedImageResultItems?: Array<EnhancedImageResultItem>;
```
