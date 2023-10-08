---
layout: default-layout
title: Dynamsoft Document Normalizer Android  API Reference - Main Page
description: This is the main page of Dynamsoft Document Normalizer SDK API Reference for Android.
keywords: api reference, Android 
permalink: /programming/android/api-reference/index.html
---

# API Reference - Android 

## Primary Class

- [`CaptureVisionRouter`]({{ site.dcv_android_api }}capture-vision-router/capture-vision-router.html)

## Input

- [`CameraEnhancer`]({{ site.dce_android }}primary-api/camera-enhancer.html)
- [`ImageSourceAdapter`]({{ site.dcv_android_api }}core/basic-structures/image-source-adapter.html)
- [`DirectoryFetcher`]({{ site.dcv_android_api }}utility/directory-fetcher.html)
- [`FileFetcher`]({{ site.dcv_android_api }}utility/file-fetcher.html)

## Final Results

- [`CapturedResultReceiver`]({{ site.dcv_android_api }}core/basic-structures/captured-result-receiver.html)
- [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html)
- [`CapturedResult`]({{ site.dcv_android_api }}core/basic-structures/captured-result.html)
- [`DetectedQuadResultItem`]({{ site.android_api }}detected-quad-result-item.html)
- [`DetectedQuadsResult`]({{ site.android_api }}detected-quads-result.html)
- [`NormalizedImageResultItem`]({{ site.android_api }}normalized-image-result-item.html)
- [`NormalizedImagesResult`]({{ site.android_api }}normalized-images-result.html)
- [`OriginalImageResultItem`]({{ site.dcv_android_api }}core/basic-structures/original-image-result-item.html)

## Final Results Filters

- [`CapturedResultFilter`]({{ site.dcv_android_api }}core/basic-structures/captured-result-filter.html)
- [`MultiFrameResultCrossFilter`]({{ site.dcv_android_api }}utility/multi-frame-result-cross-filter.html)

## Intermediate Results

- [`IntermediateResultManager`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-manager.html)
- [`IntermediateResultReceiver`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-receiver.html)
- [`ObservationParameters`]({{ site.dcv_android_api }}core/intermediate-results/observation-parameters.html)
- [`IntermediateResultExtraInfo`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-extra-info.html)
- [`IntermediateResult`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result.html)
- [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html)
- [`PredetectedRegionsUnit`]({{ site.dcv_android_api }}core/intermediate-results/predetected-regions-unit.html)
- [`DetectedQuadsUnit`]({{ site.android_api }}detected-quads-unit.html)
- [`NormalizedImagesUnit`]({{ site.android_api }}normalized-image-unit.html)
- [`RegionObjectElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html)
- [`PredetectedRegionElement`]({{ site.dcv_android_api }}core/intermediate-results/predetected-region-element.html)
- [`DetectedQuadElement`]({{ site.android_api }}detected-quad-element.html)
- [`NormalizedImageElement`]({{ site.android_api }}normalized-image-element.html)
- [`BinaryImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/binary-image-unit.html)
- [`CandidateQuadEdgesUnit`]({{ site.android_api }}candidate-quad-edges-unit.html)
- [`ColourImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/colour-image-unit.html)
- [`ContoursUnit`]({{ site.dcv_android_api }}core/intermediate-results/contours-unit.html)
- [`CornersUnit`]({{ site.android_api }}corners-unit.html)
- [`EnhancedGrayscaleImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/enhanced-grayscale-image-unit.html)
- [`GrayscaleImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/grayscale-image-unit.html)
- [`LineSegmentsUnit`]({{ site.dcv_android_api }}core/intermediate-results/line-segments-unit.html)
- [`LongLinesUnit`]({{ site.android_api }}long-lines-unit.html)
- [`ScaledDownColourImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/scaled-down-colour-image-unit.html)
- [`TextRemovedBinaryImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/text-removed-binary-image-unit.html)
- [`TextZonesUnit`]({{ site.dcv_android_api }}core/intermediate-results/text-zones-unit.html)
- [`TextureDetectionResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/texture-detection-result-unit.html)
- [`TextureRemovedBinaryImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/texture-removed-binary-image-unit.html)
- [`TextureRemovedGrayscaleImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/texture-removed-grayscale-image-unit.html)
- [`TransformedGrayscaleImageUnit`]({{ site.dcv_android_api }}core/intermediate-results/transformed-grayscale-image-unit.html)

## Settings

- [`SimplifiedCaptureVisionSettings`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html)
- [`EnumPresetTemplate`]({{ site.dcv_enums }}capture-vision-router/preset-template.html?lang=android)

## State Listener

- [`CaptureStateListener`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/capture-state-listener.html)
- [`ImageSourceStateListener`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/image-source-state-listener.html)

## License Manager

- [`LicenseManager`]({{ site.dcv_android_api }}license/license-manager.html)

## Basic Structure

- [`Contour`]({{ site.dcv_android_api }}core/basic-structures/contour.html)
- [`Corner`]({{ site.dcv_android_api }}core/basic-structures/corner.html)
- [`Edge`]({{ site.dcv_android_api }}core/basic-structures/edge.html)
- [`FileImageTag`]({{ site.dcv_android_api }}core/basic-structures/file-image-tag.html)
- [`ImageData`]({{ site.dcv_android_api }}core/basic-structures/image-data.html)
- [`ImageTag`]({{ site.dcv_android_api }}core/basic-structures/image-tag.html)
- [`LineSegment`]({{ site.dcv_android_api }}core/basic-structures/line-segment.html)
- [`PDFReadingParameter`]({{ site.dcv_android_api }}core/basic-structures/pdf-reading-parameter.html)
- [`Quadrilateral`]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html)
- [`Rect`]({{ site.dcv_android_api }}core/basic-structures/rect.html)
- [`VideoFrameTag`]({{ site.dcv_android_api }}core/basic-structures/video-frame-tag.html)

## Modules

- [`CaptureVisionRouterModule`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/capture-vision-router-module.html)
- [`DocumentNormalizerModule`]({{ site.android_api }}document-normalizer-module.html)
- [`CoreModule`]({{ site.dcv_android_api }}core/basic-structures/core-module.html)
- [`LicenseModule`]({{ site.dcv_android_api }}license/license-module.html)
- [`UtilityModule`]({{ site.dcv_android_api }}utility/utility-module.html)
- [`ImageProcessingModule`]({{ site.dcv_android_api }}image-processing/image-processing-module.html)

## Enumerations

- [`EnumBufferOverflowProtectionMode`]({{ site.dcv_enums }}core/buffer-overflow-protection-mode.html?lang=android)
- [`EnumCapturedResultItemType`]({{ site.dcv_enums }}core/captured-result-item-type.html?lang=android)
- [`EnumCornerType`]({{ site.dcv_enums }}core/corner-type.html?lang=android)
- [`EnumErrorCode`]({{ site.dcv_enums }}core/error-code.html?lang=android)
- [`EnumGrayscaleTransformationMode`]({{ site.dcv_enums }}core/grayscale-transformation-mode.html?lang=android)
- [`EnumImageCaptureDistanceMode`]({{ site.dcv_enums }}core/image-capture-distance-mode.html?lang=android)
- [`EnumImagePixelFormat`]({{ site.dcv_enums }}core/image-pixel-format.html?lang=android)
- [`EnumImageSourceState`]({{ site.dcv_enums }}core/image-source-state.html?lang=android)
- [`EnumImageTagType`]({{ site.dcv_enums }}core/image-tag-type.html?lang=android)
- [`EnumIntermediateResultUnitType`]({{ site.dcv_enums }}core/intermediate-result-unit-type.html?lang=android)
- [`EnumPDFReadingMode`]({{ site.dcv_enums }}core/pdf-reading-mode.html?lang=android)
- [`EnumRegionObjectElementType`]({{ site.dcv_enums }}core/region-object-element-type.html?lang=android)
- [`EnumSectionType`]({{ site.dcv_enums }}core/section-type.html?lang=android)
- [`EnumRasterDataSource`]({{ site.dcv_enums }}core/raster-data-source.html?lang=android)
- [`EnumVideoFrameQuality`]({{ site.dcv_enums }}core/video-frame-quality.html?lang=android)
- [`EnumColourChannelUsageType`]({{ site.dcv_enums}}core/colour-channel-usage-type.html?lang=android)
- [`EnumTransformMatrixType`]({{ site.dcv_enums}}core/transform-matrix-type.html?lang=android)
