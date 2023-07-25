---
layout: default-layout
Title: NormalizedImagesResult - Dynamsoft Document Normalizer Android SDK API Reference
Description: The class NormalizedImagesResult represents a collection of captured result items whose type are normalized images.
Keywords: normalized images, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# NormalizedImagesResult

The `NormalizedImagesResult` class represents a collection of captured result items whose type are normalized images.

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class NormalizedImagesResult
```

## Methods Summary

| Methods | Description |
| ---------- | ----------- |
| [`getItems`](#getitems) | Gets an array of NormalizedImageResultItem. Each NormalizedImageResultItem is a result object of a single normalized image. |
| [`getRotationTransformMatrix`](#getrotationtransformmatrix) | Gets the rotation transformation matrix of the original image relative to the rotated image. |
| [`getSourceImageHashId`](#getsourceimagehashid) | Gets the hash id of the source image. You can use this ID to get the source image via IntermediateResultManager class. |
| [`getSourceImageTag`](#getsourceimagetag) | Gets the tag of the source image. |

### getItems

Gets an array of `NormalizedImageResultItem` objects, where each object represents a single normalized image.

```java
NormalizedImageResultItem[] getItems();
```

**Return Value**

The array of the normalized image result items.

### getRotationTransformMatrix

Gets the rotation transformation matrix of the original image relative to the rotated image.

```java
Matrix getRotationTransformMatrix();
```

**Return Value**

The rotation transformation matrix of the original image relative to the rotated image.

### getSourceImageHashId

Gets the hash id of the source image. You can use this ID to get the source image via `IntermediateResultManager` class.

```java
String getSourceImageHashId();
```

**Return Value**

The hash id of the source image.

### getSourceImageTag

Gets the tag of the source image.

```java
ImageTag getSourceImageTag();
```

**Return Value**

The tag of the source image.

**See Also**

* [ImageTag]({{ site.dcv_android_api }}core/basic-structures/image-tag.html)