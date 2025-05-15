---
layout: default-layout
title: EnhancedImageResultItem - Dynamsoft Document Normalizer Android SDK API Reference
description: The class EnhancedImageResultItem represents a captured result item whose type is a enhanced image. It stores the enhanced image information.
keywords: enhanced image result item, java, kotlin
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# EnhancedImageResultItem

The `EnhancedImageResultItem` class is an extension of [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html) that represents a enhanced image. This is the most basic unit of the enhanced image result, one of the captured result types that the Capture Vision Router can output. 

## Definition

*Namespace:* com.dynamsoft.ddn

*Assembly:* DynamsoftCaptureVisionBundle.aar

```java
class EnhancedImageResultItem extends CapturedResultItem
```

## Methods

| Methods | Description |
| ---------- | ----------- |
| [`getImageData`](#getimagedata) | Returns an `ImageData` object as the enhanced image. |
| [`getOriginalToLocalMatrix`](#getoriginaltolocalmatrix) | Returns the transformation matrix from the original image coordinate system to the local coordinate system. |

The following methods are inherited from [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html).

| Method | Description |
| ------ | ----------- |
| [`getType`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#gettype) | Returns the type of the captured result item, indicating what kind of data it represents. |
| [`getReferencedItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#getreferenceditem) | Returns a property of type `CapturedResultItem` that represents a reference to another captured result item. |
| [`getTargetROIDefName`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#gettargetroidefname) | Returns the name of the [`TargetROIDef`]({{ site.dcv_parameters_reference }}target-roi-def/) object which includes a task that generated the result. |
| [`getTaskName`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#gettaskname) | Returns the name of the task that generated the result. |

### getImageData

Returns an [`ImageData`]({{ site.dcv_android_api }}core/basic-structures/image-data.html) object for the enhanced image.

```java
ImageData getImageData();
```

**Return Value**

The `ImageData` object as the enhanced image.

### getOriginalToLocalMatrix

Returns the transformation matrix from the original image coordinate system to the local coordinate system.

```java
Matrix getOriginalToLocalMatrix();
```

**Return Value**

The transformation matrix of type `android.graphics.Matrix`.
