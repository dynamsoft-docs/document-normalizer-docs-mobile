---
layout: default-layout
title: DeskewedImageResultItem - Dynamsoft Capture Vision React Native SDK API Reference
description: Interface DeskewedImageResultItem of Dynamsoft Capture Vision React Native represents a captured result item whose type is a deskewed image. It stores the deskewed image information.
keywords: deskewed image result item, js
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DeskewedImageResultItem

Interface `DeskewedImageResultItem` is an extension of [`CapturedResultItem`]({{ site.dcv_react_native_api }}core/captured-result-item.html) that represents a deskewed image. This is the most basic unit of the deskewed image result, one of the captured result types that the Capture Vision Router can output. 

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```js
interface DeskewedImageResultItem extends CapturedResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`imageData`](#imagedata) | *ImageData* | An `ImageData` object as the deskewed image. |
| [`sourceDeskewQuad`](#location) | *Quadrilateral* | The quadrilateral from which you get the deskewed image result item. |
| [`crossVerificationStatus`](#crossverificationstatus) | *EnumCrossVerificationStatus* | The cross verification status of the result item. |
| [`originalToLocalMatrix`](#originaltolocalmatrix) | *Array\<number\>* | The transformation matrix from the original image coordinate system to the local coordinate system. |

The following methods are inherited from [`CapturedResultItem`]({{ site.dcv_react_native_api }}core/captured-result-item.html).

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`targetROIDefName`]({{ site.dcv_react_native_api }}core/captured-result-item.html#targetroidefname) | *String* | The name of the target region of interest (ROI) where the captured result was found. |
| [`taskName`]({{ site.dcv_react_native_api }}core/captured-result-item.html#taskname) | *String* | The name of the recognition task that produced the CapturedResultItem. |
| [`type`]({{ site.dcv_react_native_api }}core/captured-result-item.html#type) | [*EnumCapturedResultItemType*]({{ site.dcv_react_native_api }}core/enum/captured-result-item-type.html) | The type of the captured result item. |

### imageData

An [`ImageData`]({{ site.dcv_react_native_api }}core/image-data.html) object for the deskewed image.

```js
imageData: ImageData;
```

### sourceDeskewQuad

The soure [Quadrilateral]({{ site.dcv_react_native_api }}core/quadrilateral.html) that used to deskew the image.

```js
sourceDeskewQuad: Quadrilateral;
```

### crossVerificationStatus

The cross verification status of the result item. The cross verification status determines whether the result item is approved by the multi-frame cross verification mechanism. If approved, the cross verification status is `CVS_PASSED`. Otherwise, it is `CVS_FAILED`.

```js
crossVerificationStatus: EnumCrossVerificationStatus | number;
```

### originalToLocalMatrix

The transformation matrix from the original image coordinate system to the local coordinate system.

```js
originalToLocalMatrix: Array<number>;
```
