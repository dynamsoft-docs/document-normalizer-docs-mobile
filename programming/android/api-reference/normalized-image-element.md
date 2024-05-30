---
layout: default-layout
title: NormalizedImageElement - Dynamsoft Document Normalizer Android SDK API Reference
description: The class NormalizedImageElement represents an intermediate result whose type is normalized image, It is inherited from RegionObjectElement and contains image data of normalized result as additional parameter.
keywords: normalized image element, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# NormalizedImageElement

The `NormalizedImageElement` class represents an intermediate result whose type is normalized image. It is inherited from `RegionObjectElement` and contains image data of normalized result as an additional parameter.

## Definition

*Namespace:* com.dynamsoft.ddn.intermediate_results

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class NormalizedImageElement extends RegionObjectElement
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getImageData`](#getimagedata) | Gets an [`ImageData`]({{site.dcv_android_api}}core/basic-structures/image-data.html) object as the normalized image. |

The following methods are inherited from class [`RegionObjectElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-android.md -%}

### getImageData

Gets an [`ImageData`]({{site.dcv_android_api}}core/basic-structures/image-data.html) object as the normalized image.

```java
ImageData getImageData();
```

**Return Value**

The [`ImageData`]({{site.dcv_android_api}}core/basic-structures/image-data.html) object as the normalized image.
