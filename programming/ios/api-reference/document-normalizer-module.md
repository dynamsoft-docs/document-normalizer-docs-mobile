---
layout: default-layout
title: DSDocumentNormalizerModule - Dynamsoft Document Normalizer module iOS Edition API Reference
description: The class DSDocumentNormalizerModule of Dynamsoft Document Normalizer module represents the document normalizer module, which provides general functions for document normalization.
keywords: document normalizer, objective-c, swift
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DSDocumentNormalizerModule

The `DSDocumentNormalizerModule` class defines general functions of the document normalizer module.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NS_ASSUME_NONNULL_BEGIN
@interface DSDocumentNormalizerModule : NSObject
```
2. 
```swift
class DocumentNormalizerModule : NSObject
```

## Methods

| Method | Description |
|------- |-------------|
| [`getVersion`](#getversion) | Get the version of Dynamsoft Document Normalizer. |

### getVersion

Get the version of Dynamsoft Document Normalizer.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+ (NSString *)getVersion;
```
2. 
```swift
class func getVersion() -> String
```

**Return Value**

The version of Dynamsoft Document Normalizer.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSString *version = [DSDocumentNormalizerModule getVersion];
```
2. 
```swift
let version = DocumentNormalizerModule.getVersion()
```
