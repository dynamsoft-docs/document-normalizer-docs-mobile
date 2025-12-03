---
layout: default-layout
title: EnhancedImageResultItem - Dynamsoft Capture Vision Flutter SDK API Reference
description: Interface EnhancedImageResultItem represents a captured result item whose type is a enhanced image. It stores the enhanced image information.
keywords: enhanced image result item, js
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# EnhancedImageResultItem

Interface `EnhancedImageResultItem` is an extension of [`CapturedResultItem`]({{ site.dcv_react_native_api }}core/captured-result-item.html) that represents a enhanced image. This is the most basic unit of the enhanced image result, one of the captured result types that the Capture Vision Router can output. 

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```js
interface EnhancedImageResultItem extends CapturedResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`imageData`](#imagedata) | *ImageData* | An `ImageData` object as the enhanced image. |
| [`originalToLocalMatrix`](#originaltolocalmatrix) | *Array\<number\>* | The transformation matrix from the original image coordinate system to the local coordinate system. |

The following methods are inherited from [`CapturedResultItem`]({{ site.dcv_react_native_api }}core/captured-result-item.html).

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`targetROIDefName`]({{ site.dcv_react_native_api }}core/captured-result-item.html#targetroidefname) | *String* | The name of the target region of interest (ROI) where the captured result was found. |
| [`taskName`]({{ site.dcv_react_native_api }}core/captured-result-item.html#taskname) | *String* | The name of the recognition task that produced the CapturedResultItem. |
| [`type`]({{ site.dcv_react_native_api }}core/captured-result-item.html#type) | [*EnumCapturedResultItemType*]({{ site.dcv_react_native_api }}core/enum/captured-result-item-type.html) | The type of the captured result item. |

### imageData

An [`ImageData`]({{ site.dcv_react_native_api }}core/image-data.html) object for the enhanced image.

```js
imageData: ImageData;
```

### originalToLocalMatrix

The transformation matrix from the original image coordinate system to the local coordinate system.

```js
originalToLocalMatrix: Array<number>;
```
