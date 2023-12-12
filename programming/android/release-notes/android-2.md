---
layout: default-layout
title: Dynamsoft Document Normalizer for Android SDK - Release Notes
description: This is the release notes page of Dynamsoft Document Normalizer for Android SDK 2.x.
keywords: release notes, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/android/release-notes/android-2.html
---

# Release Notes for Android SDK - v2.x

## 2.0.20 (12/12/2023)

### New

- Added parameter `Page` to `ImageSource` object.
- Added a new method `setPages` to the class `DirectoryFetcher` and class `FileFetcher`.
- Added `ImageSourceErrorListener` to receive the errors from an image source.
- Added method `setErrorListener` to class `ImageSourceAdapter` to add the `ImageSourceErrorListener`.
- Added a new parameter `minImageCaptureInterval` which can be set via the class `SimplifiedCaptureVisionSettings` or the `CaptureVisionTemplate` object of a JSON template file.
- Added "UNKNOWN" as a supported value of the `TextDetectionMode.direction` parameter. Changed the default value of `direction` to "UNKNOWN".
- Added the following error codes:
  - EC_FILE_ALREADY_EXISTS
  - EC_CREATE_FILE_FAILED
  - EC_IMGAE_DATA_INVALID

### Improved

- The class `DirectoryFetcher` and `FileFetcher` will be able to return error codes via `ImageSourceErrorListener`
- Updated the error codes of the method `saveToFile` of the class `ImageManager`.
- Optimize the logic to support calling `IntermediateResultManager.addResultReceiver` and  `IntermediateResultManager.removeResultReceiver` after `startCapturing`.
- Added ability to output all templates via methods `outputSettings` and `outputSettingsToFile` by specifying "*" for the parameter `templateName`.

### Fixed

- Small fixes and tweaks.

### Changed

- Updated the internal package dependencies rules.
- Changed the upper limit to the `duplicateForgetTime`, which is 3 minutes.
- Changed the timing of `onOriginalImageResultReceived` so that it is triggered immediately after receiving the image.

## 2.0.10 (08/10/2023)

{%- include release-notes/product-highlight-2.0.0.md -%}
