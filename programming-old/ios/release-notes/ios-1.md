---
layout: default-layout
title: Dynamsoft Document Normalizer for iOS SDK - Release Notes
description: This is the release notes page of Dynamsoft Document Normalizer for iOS SDK v7.6.1 and below.
keywords: release notes, ios, 
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/ios/release-notes/ios-1.html
---

# Release Notes for iOS SDK - v1.x

## 1.0.20 (02/02/2023)

### Fixed

- Fixed a bug that the colours of binarized images might be inverted when using [`LEM_MARGIN_BASED`]({{site.parameters}}reference/line-extraction-modes.html) mode for `LineExtractionModes`.
- Fixed a bug where the normalized image may have black borders when setting [`ColourMode`]({{site.parameters}}reference/colour-mode.html) of `NormalizerParameter` to `ICM_BINARY`.

## 1.0.10 (09/29/2022)

### New

- Added a new method [`setImageSource`](../api-reference/document-normalizer-video.md#setimagesource) in `DynamsoftDocumentNormalizer` class to set up image source.
- Added a new method [`saveToFile`](../api-reference/normalized-image-result.md#savetofile) in class `iNormalizedImageResult` to support saving the normalized image as a BMP/JPEG/PNG/PDF file.
- Added a new property [`orientation`](../api-reference/image-data.md#orientation) in class `iImageData`.

### Changed

- Updated [ErrorCode](../../enumerations/error-code.md)
  - Added `DMERR_IMAGE_ORIENTATION_INVALID` (-10060).
  - Change the value of `DDNERR_CONTENT_NOT_FOUND` from -10056 to -50001.
  - Renamed `DDNERR_QUADRILATERAL_INVALID` to `DMERR_QUADRILATERAL_INVALID`.

### Deprecated

- Deprecated `setCameraEnhancer`.

## 1.0.0 (06/21/2022)

### Highlights

{%- include release-notes/product-highlight-1.0.0.md -%}
