---
layout: default-layout
title: Dynamsoft Core Objective-C & Swift Class - iQuadrilateral
description: This page shows the iQuadrilateral class of Dynamsoft Document Normalizer iOS edition v1.x.
keywords: iQuadrilateral, class, objective-c, oc, swift
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/ios/api-reference/quadrilateral.html
---


# iQuadrilateral

> You are viewing a history document page of Dynamsoft Document Normalizer v1.0.30.

Stores the quadrilateral.  

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iQuadrilateral : NSObject 
```
2. 
```swift
class iQuadrilateral : NSObject
```

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`points`](#points) | *NSArray\** |

&nbsp;

### points

Four vertexes (CGPoint) in a clockwise direction of a quadrilateral. Index 0 represents the left-most vertex.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSArray* points
```
2. 
```swift
var points: [Any] { get set }
```
