---
layout: default-layout
title: Class DCVDocumentNormalizer (Android) - Dynamsoft Document Normalizer Xamarin.Forms API Reference
description: This is the page of Android Class DCVDocumentNormalizer of Dynamsoft Document Normalizer Xamarin.Forms SDK.
keywords: initLicense, DCVDocumentNormalizer, api reference, Xamarin.Forms
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 1.0
permalink: /programming/xamarin/api-reference/droid-document-normalizer.html
---

# DDNXamarin.Droid.DCVDocumentNormalizer

The class that implements interface [`IDocumentNormalizer`](document-normalizer.md) on Android end.

## How to Use

Add the following code in the **MainActivity.cs** of your project to implement `IDocumentNormalizer` with `DCVDocumentNormalizer`.

```csharp
protected override void OnCreate(Bundle savedInstanceState)
{
    ...
    LoadApplication(new App(new DCVCameraEnhancer(this), new DCVDocumentNormalizer(), new DCVLicenseManager(this)));
}
```

## Methods Summary

| Method | Description |
|--------|-------------|
| [`SetCameraEnhancer`](document-normalizer.md#setcameraenhancer) | Sets an instance of ImageSource to get images. |
| [`StartDetecting`](document-normalizer.md#startdetecting) | Start the document quad detection thread in the video streaming scenario. |
| [`StopDetecting`](document-normalizer.md#stopdetecting) | Stop the document quad detection thread in the video streaming scenario. |
| [`AddResultListener`](document-normalizer.md#addresultlistener) | Set callback interface to process detection results generated during frame detecting. |
| [`DetectQuad(ImageData)`](document-normalizer.md#detectquadimagedata) | Detect quad from the memory buffer containing image pixels in defined format. |
| [`DetectQuad(File)`](document-normalizer.md#detectquadfile) | Detect quad from an image file. |
| [`Normalize(ImageData)`](document-normalizer.md#normalizeimagedata) | Normalize image from the memory buffer containing image pixels in defined format. |
| [`Normalize(File)`](document-normalizer.md#normalizefile) | Normalize an image file. |
| [`InitRuntimeSettingsFromFile`](document-normalizer.md#initruntimesettingsfromfile) | Initialize runtime settings with the settings in a given JSON file. |
| [`InitRuntimeSettings`](document-normalizer.md#initruntimesettings) | Initialize runtime settings with the settings in a given JSON string. |
| [`OutputRuntimeSettingsToFile`](document-normalizer.md#outputruntimesettingstofile) | Output runtime settings to a settings file (JSON file). |
| [`OutputRuntimeSettings`](document-normalizer.md#outputruntimesettings) | Output runtime settings to a string. |
| [`SaveToFile`](document-normalizer.md#savetofile) | Save a `NormalizedImageResult` to the targeting file path. |
| [`GetVersion`](document-normalizer.md#getversion) | Get version information of SDK. |
