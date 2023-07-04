---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - DynamsoftDocumentNormalizer Runtime Settings Advanced Methods
description: This page shows advanced runtime settings methods of Dynamsoft Document Normalizer for iOS SDK.
keywords: initRuntimeSettingsFromFile, initRuntimeSettingsFromString, outputRuntimeSettingsToFile, outputRuntimeSettings, runtime settings advanced methods, DynamsoftDocumentNormalizer, api reference, ios
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/ios/api-reference/document-normalizer-settings.html
---

# Runtime Settings Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`initRuntimeSettingsFromFile`](#initruntimesettingsfromfile)  | Initialize runtime settings with the settings in a given JSON file. |
  | [`initRuntimeSettingsFromString`](#initruntimesettingsfromstring) | Initialize runtime settings with the settings in a given JSON string. |
  | [`outputRuntimeSettingsToFile`](#outputruntimesettingstofile) | Output runtime settings to a settings file (JSON file). |
  | [`outputRuntimeSettings`](#outputruntimesettings) | Output runtime settings to a string. |

  ---

## initRuntimeSettingsFromFile

Initialize runtime settings from a given JSON file.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(BOOL)initRuntimeSettingsFromFile:(NSString*)filePath error:(NSError**)error;
```
2. 
```swift
func initRuntimeSettingsFromFile(_ filePath: String) throws
```

**Parameters**

`[in] filePath`: The path of the settings file.  
`[in,out] error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The boolean value indicating whether the operation was successful.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
NSError* error;
BOOL isSuccess = [normalizer initRuntimeSettingsFromFile:@"your template file path" error:&error];
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
do{
   try normalizer.initRuntimeSettingsFromFile("your template file path")
}catch{
   // Add your code to deal with the exceptions.
}
```

## initRuntimeSettingsFromString

Initialize runtime settings from a given JSON string.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(BOOL)initRuntimeSettingsFromString:(NSString*)content error:(NSError**)error;
```
2. 
```swift
func initRuntimeSettingsFromString(_ JSONString: String) throws
```

**Parameters**

`[in] content`: A JSON string that represents the content of the settings.  
`[in,out] error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The boolean value indicating whether the operation was successful.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
NSError* error;
BOOL isSuccess = [normalizer initRuntimeSettingsFromString:@"your json template string" error:&error];
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
do{
   try normalizer.initRuntimeSettingsFromString("your json template string")
}catch{
   // Add your code to deal with the exceptions.
}
```

## outputRuntimeSettingsToFile

Output runtime settings to a settings file (JSON file).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(BOOL)outputRuntimeSettingsToFile:(NSString*)filePath, settingsName:(NSString*)settingsName error:(NSError**)error;
```
2. 
```swift
func outputRuntimeSettingsToFile(_ filePath: String, templateName: String) throws
```

**Parameters**

`[in] filePath`: The output file path which stores runtime settings.  
`[in] settingsName`: A unique name for declaring runtime settings.  
`[in,out] error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The boolean value indicating whether the operation was successful.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
NSError* error;
BOOL isSuccess = [normalizer outputRuntimeSettingsToFile:@"your template file path" settingsName:@"your template name" error:&error];
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
do{
   try normalizer.outputRuntimeSettingsToFile("your template file path", settingsName:"your template name")
}catch{
   // Add your code to deal with the exceptions.
}
```

## outputRuntimeSettings

Output runtime settings to a JSON string.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSString*)outputRuntimeSettings:(NSString*)settingsName error:(NSError**)error;
```
2. 
```swift
func outputRuntimeSettings(_ templateName: String) throws -> String
```

**Parameters** 

`[in] settingsName` A unique name for declaring runtime settings.  
`[in,out] error`: Input a pointer to an error object. If an error occurs, this pointer is set to an actual error object containing the error information. You may specify nil for this parameter if you do not want the error information.

**Return Value**

The output JSON string which stores the contents of runtime settings.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftDocumentNormalizer* normalizer = [[DynamsoftDocumentNormalizer alloc] init];
NSError* error;
NSString* settingsString = [normalizer outputRuntimeSettings:@"your template name" error:&error];
```
2. 
```swift
let normalizer = DynamsoftDocumentNormalizer()
do{
   let settingsString = try normalizer.outputRuntimeSettings("your template name")
}catch{
   // Add your code to deal with the exceptions.
}
```
