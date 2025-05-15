---
layout: default-layout
title: DeskewedImageElement - Dynamsoft Document Normalizer Android SDK API Reference
description: The class DeskewedImageElement represents an intermediate result whose type is deskewed image, It is inherited from RegionObjectElement and contains image data of deskewed result as additional parameter.
keywords: deskewed image element, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DeskewedImageElement

The `DeskewedImageElement` class represents an intermediate result whose type is deskewed image. It is inherited from `RegionObjectElement` and contains image data of deskewed result as an additional parameter.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftCaptureVisionBundle.aar

```java
class DeskewedImageElement extends RegionObjectElement
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`setImageData`](#getimagedata) | Sets the image data of the deskewed image with a `DSImageData` object. |
| [`getSourceDeskewQuad`](#sourcedeskewquad) | Returns the quadrilateral from which you get the deskewed image result item. |

The following methods are inherited from class [`RegionObjectElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-android.md -%}

### setImageData

Gets an [`ImageData`]({{site.dcv_android_api}}core/basic-structures/image-data.html) object as the deskewed image.

```java
void setImageData(ImageData imageData);
```

**Parameters**

`imageData`: A [`ImageData`]({{site.dcv_android_api}}core/basic-structures/image-data.html) object that represents the deskewed image.

### getSourceDeskewQuad

Returns the quadrilateral from which you get the deskewed image result item.

```java
Quadrilateral getSourceDeskewQuad();
```

**Return Value**

The quadrilateral from which you get the deskewed image result item.
