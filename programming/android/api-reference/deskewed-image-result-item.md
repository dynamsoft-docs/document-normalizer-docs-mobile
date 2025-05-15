---
layout: default-layout
title: DeskewedImageResultItem - Dynamsoft Document Normalizer Android SDK API Reference
description: The class DeskewedImageResultItem represents a captured result item whose type is a deskewed image. It stores the deskewed image information.
keywords: deskewed image result item, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DeskewedImageResultItem

The `DeskewedImageResultItem` class is an extension of [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html) that represents a deskewed image. This is the most basic unit of the deskewed image result, one of the captured result types that the Capture Vision Router can output. 

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftDocumentNormalizer.aar

```java
class DeskewedImageResultItem extends CapturedResultItem
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getImageData`](#getimagedata) | Returns an `ImageData` object as the deskewed image. |
| [`getSourceDeskewQuad`](#getlocation) | Returns the quadrilateral from which you get the deskewed image result item. |
| [`getCrossVerificationStatus`](#getcrossverificationstatus) | Returns the cross verification status of the result item. |
| [`getOriginalToLocalMatrix`](#getoriginaltolocalmatrix) | Returns the transformation matrix from the original image coordinate system to the local coordinate system. |

The following methods are inherited from [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html).

| Method | Description |
| ------ | ----------- |
| [`getType`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#gettype) | Returns the type of the captured result item, indicating what kind of data it represents. |
| [`getReferencedItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#getreferenceditem) | Returns a property of type `CapturedResultItem` that represents a reference to another captured result item. |
| [`getTargetROIDefName`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#gettargetroidefname) | Returns the name of the [`TargetROIDef`]({{ site.dcv_parameters_reference }}target-roi-def/) object which includes a task that generated the result. |
| [`getTaskName`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#gettaskname) | Returns the name of the task that generated the result. |

### getImageData

Returns an [`ImageData`]({{ site.dcv_android_api }}core/basic-structures/image-data.html) object for the deskewed image.

```java
ImageData getImageData();
```

**Return Value**

The `ImageData` object as the deskewed image.

### getSourceDeskewQuad

Returns the soure [Quadrilateral]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html) that used to deskew the image.

```java
Quadrilateral getLocation();
```

**Return Value**

The soure [Quadrilateral]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html) that used to deskew the image.

### getCrossVerificationStatus

Returns the cross verification status of the result item. The cross verification status determines whether the result item is approved by the multi-frame cross verification mechanism. If approved, the cross verification status is `CVS_PASSED`. Otherwise, it is `CVS_FAILED`.

```java
EnumCrossVerificationStatus getCrossVerificationStatus();
```

**Return Value**

Returns the cross verification status of type [`EnumCrossVerificationStatus`]({{ site.dcv_enumerations }}core/cross-verification-status.html).

### getOriginalToLocalMatrix

Returns the transformation matrix from the original image coordinate system to the local coordinate system.

```java
Matrix getOriginalToLocalMatrix();
```

**Return Value**

The transformation matrix of type `android.graphics.Matrix`.
