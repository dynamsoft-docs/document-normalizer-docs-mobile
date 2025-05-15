---
layout: default-layout
title: EnhancedImageElement - Dynamsoft Document Normalizer Android SDK API Reference
description: The class EnhancedImageElement represents an intermediate result whose type is enhanced image, It is inherited from RegionObjectElement and contains image data of enhanced result as additional parameter.
keywords: enhanced image element, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# EnhancedImageElement

The `EnhancedImageElement` class represents an intermediate result whose type is enhanced image. It is inherited from `RegionObjectElement` and contains image data of enhanced result as an additional parameter.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class EnhancedImageElement extends RegionObjectElement
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`setImageData`](#getimagedata) | Sets the image data of the deskewed image with a `DSImageData` object. |

The following methods are inherited from class [`RegionObjectElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-android.md -%}

### setImageData

Gets an [`ImageData`]({{site.dcv_android_api}}core/basic-structures/image-data.html) object as the enhanced image.

```java
void setImageData(ImageData imageData);
```

**Parameters**

`imageData`: A [`ImageData`]({{site.dcv_android_api}}core/basic-structures/image-data.html) object that represents the enhanced image.
