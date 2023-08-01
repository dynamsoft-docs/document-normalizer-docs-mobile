---
layout: default-layout
title: Dynamsoft Document Normalizer iOS API Reference - Main Page
description: This is the main page of Dynamsoft Document Normalizer SDK API Reference for iOS.
keywords: api reference, iOS 
permalink: /programming/ios/api-reference/index.html
---

# API Reference - iOS 

## Primary Class

- [`DSCaptureVisionRouter`]({{ site.dcv_ios_api }}capture-vision-router/capture-vision-router.html)

## Input

- [`DSCameraEnhancer`]({{ site.dce_ios_api }}primary-api/camera-enhancer.html)
- [`DSDirectoryFetcher`]({{ site.dcv_ios_api }}utility/directory-fetcher.html)
- [`DSFileFetcher`]({{ site.dcv_ios_api }}utility/file-fetcher.html)
- [`DSImageSourceAdapter`]({{ site.dcv_ios_api }}core/basic-structures/image-source-adapter.html)

## Final Results

- [`DSCapturedResultReceiver`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-receiver.html)
- [`DSCapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html)
- [`DSCapturedResult`]({{ site.dcv_ios_api }}core/basic-structures/captured-result.html)
- [`DSDetectedQuadResultItem`]({{ site.ios_api }}detected-quad-result-item.html)
- [`DSDetectedQuadsResult`]({{ site.ios_api }}detected-quads-result.html)
- [`DSNormalizedImageResultItem`]({{ site.ios_api }}normalized-image-result-item.html)
- [`DSNormalizedImagesResult`]({{ site.ios_api }}normalized-images-result.html)
- [`DSOriginalImageResultItem`]({{ site.dcv_ios_api }}core/basic-structures/original-image-result-item.html)

## Final Results Filters

- [`DSCapturedResultFilter`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-filter.html)
- [`DSMultiFrameResultCrossFilter`]({{ site.dcv_ios_api }}utility/multi-frame-result-cross-filter.html)

## Intermediate Results

- [`DSIntermediateResultManager`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-manager.html)
- [`DSIntermediateResultReceiver`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-receiver.html)
- [`DSObservationParameters`]({{ site.dcv_ios_api }}core/intermediate-results/observed-parameters.html)
- [`DSIntermediateResultExtraInfo`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-extra-info.html)
- [`DSIntermediateResult`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result.html)
- [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html)
- [`DSPredetectedRegionsUnit`]({{ site.dcv_ios_api }}core/intermediate-results/predetected-regions-unit.html)
- [`DSDetectedQuadsUnit`]({{ site.ios_api }}detected-quads-unit.html)
- [`DSNormalizedImagesUnit`]({{ site.ios_api }}normalized-image-unit.html)
- [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html)
- [`DSPredetectedRegionElement`]({{ site.dcv_ios_api }}core/intermediate-results/predetected-region-element.html)
- [`DSDetectedQuadElement`]({{ site.ios_api }}detected-quad-element.html)
- [`DSNormalizedImageElement`]({{ site.ios_api }}normalized-image-element.html)
- [`DSBinaryImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/binary-image-unit.html)
- [`DSCandidateQuadEdgesUnit`]({{ site.ios_api }}candidate-quad-edges-unit.html)
- [`DSColourImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/colour-image-unit.html)
- [`DSContoursUnit`]({{ site.dcv_ios_api }}core/intermediate-results/contours-unit.html)
- [`DSCornersUnit`]({{ site.ios_api }}corners-unit.html)
- [`DSEnhancedGrayscaleImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/enhanced-grayscale-image-unit.html)
- [`DSGrayscaleImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/grayscale-image-unit.html)
- [`DSLineSegmentsUnit`]({{ site.dcv_ios_api }}core/intermediate-results/line-segments-unit.html)
- [`DSLongLinesUnit`]({{ site.ios_api }}long-lines-unit.html)
- [`DSScaledDownColourImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/scaled-down-colour-image-unit.html)
- [`DSTextRemovedBinaryImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/text-removed-binary-image-unit.html)
- [`DSTextZonesUnit`]({{ site.dcv_ios_api }}core/intermediate-results/text-zones-unit.html)
- [`DSTextureDetectionResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/texture-detection-result-unit.html)
- [`DSTextureRemovedBinaryImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/texture-removed-binary-image-unit.html)
- [`DSTextureRemovedGrayscaleImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/texture-removed-grayscale-image-unit.html)
- [`DSTransformedGrayscaleImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/transformed-grayscale-image-unit.html)

## Settings

- [`DSSimplifiedCaptureVisionSettings`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html)
- [`DSPresetTemplate`]({{ site.dcv_enums }}capture-vision-router/preset-template.html?lang=objc&swift)

## State Listener

- [`DSCaptureStateListener`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/capture-state-listener.html)
- [`DSImageSourceStateListener`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/image-source-state-listener.html)

## License Manager

- [`DSLicenseManager`]({{ site.dcv_ios_api }}license/license-manager.html)

## Basic Structure

- [`DSContour`]({{ site.dcv_ios_api }}core/basic-structures/contour.html)
- [`DSCorner`]({{ site.dcv_ios_api }}core/basic-structures/corner.html)
- [`DSEdge`]({{ site.dcv_ios_api }}core/basic-structures/edge.html)
- [`DSFileImageTag`]({{ site.dcv_ios_api }}core/basic-structures/file-image-tag.html)
- [`DSImageData`]({{ site.dcv_ios_api }}core/basic-structures/image-data.html)
- [`DSImageTag`]({{ site.dcv_ios_api }}core/basic-structures/image-tag.html)
- [`DSLineSegment`]({{ site.dcv_ios_api }}core/basic-structures/line-segment.html)
- [`DSPDFReadingParameter`]({{ site.dcv_ios_api }}core/basic-structures/pdf-reading-parameter.html)
- [`DSQuadrilateral`]({{ site.dcv_ios_api }}core/basic-structures/quadrilateral.html)
- [`DSRect`]({{ site.dcv_ios_api }}core/basic-structures/rect.html)
- [`DSVideoFrameTag`]({{ site.dcv_ios_api }}core/basic-structures/video-frame-tag.html)

## Modules

- [`DSCaptureVisionRouterModule`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/capture-vision-router-module.html)
- [`DSDocumentNormalizerModule`]({{ site.ios_api }}document-normalizer-module.html)
- [`DSCoreModule`]({{ site.dcv_ios_api }}core/basic-structures/core-module.html)
- [`DSLicenseModule`]({{ site.dcv_ios_api }}license/license-module.html)
- [`DSUtilityModule`]({{ site.dcv_ios_api }}utility/utility-module.html)
- [`DSImageProcessingModule`]({{ site.dcv_ios_api }}image-processing/image-processing-module.html)

## Enumerations

- [`DSBufferOverflowProtectionMode`]({{ site.dcv_enums }}core/buffer-overflow-protection-mode.html?lang=objc&swift)
- [`DSCapturedResultItemType`]({{ site.dcv_enums }}core/captured-result-item-type.html?lang=objc&swift)
- [`DSCornerType`]({{ site.dcv_enums }}core/corner-type.html?lang=objc&swift)
- [`DSErrorCode`]({{ site.dcv_enums }}core/error-code.html?lang=objc&swift)
- [`DSGrayscaleTransformationMode`]({{ site.dcv_enums }}core/grayscale-transformation-mode.html?lang=objc&swift)
- [`DSImageCaptureDistanceMode`]({{ site.dcv_enums }}core/image-capture-distance-mode.html?lang=objc&swift)
- [`DSImagePixelFormat`]({{ site.dcv_enums }}core/image-pixel-format.html?lang=objc&swift)
- [`DSImageSourceState`]({{ site.dcv_enums }}core/image-source-state.html?lang=objc&swift)
- [`DSImageTagType`]({{ site.dcv_enums }}core/image-tag-type.html?lang=objc&swift)
- [`DSIntermediateResultUnitType`]({{ site.dcv_enums }}core/intermediate-result-unit-type.html?lang=objc&swift)
- [`DSPDFReadingMode`]({{ site.dcv_enums }}core/pdf-reading-mode.html?lang=objc&swift)
- [`DSRegionObjectElementType`]({{ site.dcv_enums }}core/region-object-element-type.html?lang=objc&swift)
- [`DSSectionType`]({{ site.dcv_enums }}core/section-type.html?lang=objc&swift)
- [`DSRasterDataSource`]({{ site.dcv_enums }}core/raster-data-source.html?lang=objc&swift)
- [`DSVideoFrameQuality`]({{ site.dcv_enums }}core/video-frame-quality.html?lang=objc&swift)
- [`DSColourChannelUsageType`]({{ site.dcv_enums}}core/colour-channel-usage-type.html?lang=objc&swift)
- [`DSTransformMatrixType`]({{ site.dcv_enums}}core/transform-matrix-type.html?lang=objc&swift)
