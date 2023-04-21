---
layout: default-layout
title: iOS Protocol DCECameraStateListener - Dynamsoft Camera Enhancer
description: This is the documentation - iOS Protocol DCECameraStateListener page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS Protocol DCECameraStateListener
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: false
breadcrumbText: iOS Protocol DCECameraStateListener
permalink: /programming/ios/api-reference/camera-enhancer/protocol-dcecamerastatelistener.html
---

# DCECameraStateListener

The protocol to handle callback when camera state changes.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@protocol DCECameraStateListener <NSObject>
```
2. 
```swift
protocol DCECameraStateListener : NSObjectProtocol
```

| Method | Type | Description |
| ------ | ---- | ----------- |
| [`stateChangeCallback`](#statechangecallback) | *required* | The callback method is triggered when **camera state** changes. |

## stateChangeCallback

The callback method is triggered when **camera state** changes.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)stateChangeCallback:(EnumCameraState)cameraState;
```
2. 
```swift
func stateChangeCallback(_ currentState: EnumCameraState)
```

**Parameters**

`cameraState`: The camera state. It includes `opened`, `opening`, `closed` and `closing`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface ViewController ()<DCECameraStateListener>
- (void)configurationDCE{
   [_dce setCameraStateListener:self];
}
- (void)stateChangeCallback:(EnumCameraState)state{
   // Add your code to do when camera state changes.
}
```
2. 
```swift
class ViewController: UIViewController,DCECameraStateListener{
   func configurationDCE(){
          dce.setCameraStateListener(self)
   }
   func stateChangeCallback(EnumCameraState currentState){
          // Add your code to do when camera state changes.
   }
}
```
