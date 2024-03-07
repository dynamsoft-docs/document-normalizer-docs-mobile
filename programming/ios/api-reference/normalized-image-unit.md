---
layout: default-layout
title: DSNormalizedImagesUnit - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSNormalizedImagesUnit of Dynamsoft Document Normalizer module represents an intermediate result unit whose type is normalized images.
keywords: normalized images, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSNormalizedImagesUnit

The `DSNormalizedImagesUnit` class represents an intermediate result unit whose type is normalized images.

## Definition

*Assembly:* DynamsoftDocumentNormalizer.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSNormalizedImagesUnit: DSIntermediateResultUnit
```
2. 
```swift
class NormalizedImagesUnit: IntermediateResultUnit
```

## Methods

| Methods | Description |
| ------- | ----------- |
| [`getNormalizedImages`](#getnormalizedimages) | Get an array of [`DSNormalizedImageElement`](normalized-image-element.md) that represent all the normalized images. |
| [`getCount`](#getcount) | Get the number of normalized images. |
| [`getNormalizedImage`](#getnormalizedimage) | Get the [`DSNormalizedImageElement`](normalized-image-element.md) at the specified index. |
| [`removeAllNormalizedImages`](#removeallnormalizedimages) | Remove all normalized images. |
| [`setNormalizedImage`](#setnormalizedimage) | Set the [`DSNormalizedImageElement`](normalized-image-element.md) at the specified index. |

### getNormalizedImages

Get an array of [`DSNormalizedImageElement`](normalized-image-element.md) that represent all the normalized images.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable NSArray<DSNormalizedImageElement*>*)getNormalizedImages;
```
2. 
```swift
func getNormalizedImages() -> [NormalizedImageElement]?
```

**Return Value**

An array of [`DSNormalizedImageElement`](normalized-image-element.md) that represent all the normalized images.

### getCount

Get the number of normalized images.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)getCount;
```
2. 
```swift
func getCount() -> Int
```

**Return Value**

The number of normalized images.

### getNormalizedImage

Get the [`DSNormalizedImageElement`](normalized-image-element.md) at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable DSNormalizedImageElement*)getNormalizedImage:(NSInteger)index;
```
2. 
```swift
func getNormalizedImage(index: Int) -> NormalizedImageElement?
```

**Parameters**

`[in] index`: The index of the normalized image.

**Return Value**

The [`DSNormalizedImageElement`](normalized-image-element.md) at the specified index.

### removeAllNormalizedImages

Remove all normalized images.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(void)removeAllNormalizedImages;
```
2. 
```swift
func removeAllNormalizedImages()
```

### setNormalizedImage

Set the [`DSNormalizedImageElement`](normalized-image-element.md) at the specified index.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)setNormalizedImage:(DSNormalizedImageElement*)element
         matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage;
```
2. 
```swift
func setNormalizedImage(element: NormalizedImageElement, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`[in] element`: The normalized image to be set.

`[in] matrixToOriginalImage`: The matrix to the original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
