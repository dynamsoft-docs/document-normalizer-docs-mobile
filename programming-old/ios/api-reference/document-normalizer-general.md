---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - DocumentNormalizer General Methods
description: This page shows DocumentNormalizer general methods of Dynamsoft Document Normalizer for iOS SDK.
keywords: getVersion, general methods, DocumentNormalizer, api reference, ios
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/ios/api-reference/document-normalizer-general.html
---

# General Methods

> You are viewing a history document page of Dynamsoft Document Normalizer v1.0.30.

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](#getversion) | Get version information of SDK.|

  ---

## getVersion

Get version information of SDK.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+(NSString*)getVersion
```
2. 
```swift
class func getVersion() -> String
```

**Return Value**

The version information string.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSString* str = [DynamsoftDocumentNormalizer getVersion];
```
2. 
```swift
let str = DynamsoftDocumentNormalizer.getVersion()
```
