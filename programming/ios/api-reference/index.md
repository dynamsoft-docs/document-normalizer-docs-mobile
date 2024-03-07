---
layout: default-layout
title: Dynamsoft Document Normalizer iOS  API Reference - Main Page
description: This is the main page of Dynamsoft Document Normalizer SDK API Reference for iOS.
keywords: api reference, iOS 
permalink: /programming/ios/api-reference/index.html
---

# API Reference - iOS 

## DynamsoftCaptureVisionRouter

### CaptureVisionRouter Class

- [`CaptureVisionRouter`]({{ site.dcv_ios_api }}capture-vision-router/capture-vision-router.html)

### Auxiliary Classes

- [`CaptureVisionRouterModule`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/capture-vision-router-module.html)
- [`CapturedResultFilter`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/captured-result-filter.html)
- [`CapturedResultReceiver`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html)
- [`IntermediateResultManager`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html)
- [`IntermediateResultReceiver`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/intermediate-result-receiver.html)
- [`SimplifiedCaptureVisionSettings`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html)

### Interfaces

- [`CaptureStateListener`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/capture-state-listener.html)
- [`ImageSourceStateListener`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/image-source-state-listener.html)

### Enumerations

- [`EnumCaptureState`]({{ site.dcv_enumerations }}capture-vision-router/capture-state.html?lang=objc,swift)
- [`EnumPresetTemplate`]({{ site.dcv_enumerations }}capture-vision-router/preset-template.html?lang=objc,swift)

## DynamsoftDocumentNormalizer

### Classes

- [`CandidateQuadEdgesUnit`]({{ site.ddn_ios_api }}candidate-quad-edges-unit.html)
- [`CornersUnit`]({{ site.ddn_ios_api }}corners-unit.html)
- [`DetectedQuadElement`]({{ site.ddn_ios_api }}detected-quad-element.html)
- [`DetectedQuadResultItem`]({{ site.ddn_ios_api }}detected-quad-result-item.html)
- [`DetectedQuadsResult`]({{ site.ddn_ios_api }}detected-quads-result.html)
- [`DetectedQuadsUnit`]({{ site.ddn_ios_api }}detected-quads-unit.html)
- [`DocumentNormalizerModule`]({{ site.ddn_ios_api }}document-normalizer-module.html)
- [`LongLinesUnit`]({{ site.ddn_ios_api }}long-lines-unit.html)
- [`NormalizedImageElement`]({{ site.ddn_ios_api }}normalized-image-element.html)
- [`NormalizedImageResultItem`]({{ site.ddn_ios_api }}normalized-image-result-item.html)
- [`NormalizedImagesResult`]({{ site.ddn_ios_api }}normalized-images-result.html)
- [`NormalizedImageUnit`]({{ site.ddn_ios_api }}normalized-image-unit.html)
- [`SimplifiedDocumentNormalizerSettings`]({{ site.ddn_ios_api }}simplified-document-normalizer-settings.html)

## DynamsoftCore

### Classes

- [`BinaryImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/binary-image-unit.html)
- [`CapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html)
- [`CapturedResult`]({{ site.dcv_ios_api }}core/basic-structures/captured-result.html)
- [`ColourImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/colour-image-unit.html)
- [`ContoursUnit`]({{ site.dcv_ios_api }}core/intermediate-results/contours-unit.html)
- [`Contour`]({{ site.dcv_ios_api }}core/basic-structures/contour.html)
- [`CoreModule`]({{ site.dcv_ios_api }}core/basic-structures/core-module.html)
- [`Corner`]({{ site.dcv_ios_api }}core/basic-structures/corner.html)
- [`DSRect`]({{ site.dcv_ios_api }}core/basic-structures/rect.html)
- [`Edge`]({{ site.dcv_ios_api }}core/basic-structures/edge.html)
- [`EnhancedGrayscaleImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/enhanced-grayscale-image-unit.html)
- [`FileImageTag`]({{ site.dcv_ios_api }}core/basic-structures/file-image-tag.html)
- [`GrayscaleImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/grayscale-image-unit.html)
- [`ImageData`]({{ site.dcv_ios_api }}core/basic-structures/image-data.html)
- [`ImageSourceAdapter`]({{ site.dcv_ios_api }}core/basic-structures/image-source-adapter.html)
- [`ImageTag`]({{ site.dcv_ios_api }}core/basic-structures/image-tag.html)
- [`IntermediateResultExtraInfo`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-extra-info.html)
- [`IntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html)
- [`IntermediateResult`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result.html)
- [`LineSegmentsUnit`]({{ site.dcv_ios_api }}core/intermediate-results/line-segments-unit.html)
- [`LineSegment`]({{ site.dcv_ios_api }}core/basic-structures/line-segment.html)
- [`ObservationParameters`]({{ site.dcv_ios_api }}core/intermediate-results/observation-parameters.html)
- [`OriginalImageResultItem`]({{ site.dcv_ios_api }}core/basic-structures/original-image-result-item.html)
- [`PredetectedRegionElement`]({{ site.dcv_ios_api }}core/intermediate-results/predetected-region-element.html)
- [`PredetectedRegionsUnit`]({{ site.dcv_ios_api }}core/intermediate-results/predetected-regions-unit.html)
- [`Quadrilateral`]({{ site.dcv_ios_api }}core/basic-structures/quadrilateral.html)
- [`RegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html)
- [`ScaledDownColourImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/scaled-down-colour-image-unit.html)
- [`TextRemovedBinaryImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/text-removed-binary-image-unit.html)
- [`TextureDetectionResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/texture-detection-result-unit.html)
- [`TextureRemovedBinaryImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/texture-removed-binary-image-unit.html)
- [`TextureRemovedGrayscaleImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/texture-removed-grayscale-image-unit.html)
- [`TextZonesUnit`]({{ site.dcv_ios_api }}core/intermediate-results/text-zones-unit.html)
- [`TransformedGrayscaleImageUnit`]({{ site.dcv_ios_api }}core/intermediate-results/transformed-grayscale-image-unit.html)
- [`Vector4`]({{ site.dcv_ios_api }}core/basic-structures/vector4.html)
- [`VideoFrameTag`]({{ site.dcv_ios_api }}core/basic-structures/video-frame-tag.html)

### Interfaces

- [`ImageSourceErrorListener`]({{ site.dcv_ios_api }}core/basic-structures/image-source-error-listener.html)

### Enumerations

- [`BufferOverflowProtectionMode`]({{ site.dcv_enumerations }}core/buffer-overflow-protection-mode.html?lang=objc,swift)
- [`CapturedResultItemType`]({{ site.dcv_enumerations }}core/captured-result-item-type.html?lang=objc,swift)
- [`ColourChannelUsageType`]({{ site.dcv_enumerations }}core/colour-channel-usage-type.html?lang=objc,swift)
- [`CornerType`]({{ site.dcv_enumerations }}core/corner-type.html?lang=objc,swift)
- [`ErrorCode`]({{ site.dcv_enumerations }}core/error-code.html?lang=objc,swift)
- [`GrayscaleEnhancementMode`]({{ site.dcv_enumerations }}core/grayscale-enhancement-mode.html?lang=objc,swift)
- [`GrayscaleTransformationMode`]({{ site.dcv_enumerations }}core/grayscale-transformation-mode.html?lang=objc,swift)
- [`ImageCaptureDistanceMode`]({{ site.dcv_enumerations }}core/image-capture-distance-mode.html?lang=objc,swift)
- [`ImagePixelFormat`]({{ site.dcv_enumerations }}core/image-pixel-format.html?lang=objc,swift)
- [`ImageSourceState`]({{ site.dcv_enumerations }}core/image-source-state.html?lang=objc,swift)
- [`ImageTagType`]({{ site.dcv_enumerations }}core/image-tag-type.html?lang=objc,swift)
- [`IntermediateResultUnitType`]({{ site.dcv_enumerations }}core/intermediate-result-unit-type.html?lang=objc,swift)
- [`LogMode`]({{ site.dcv_enumerations }}core/log-mode.html?lang=objc,swift)
- [`RegionObjectElementType`]({{ site.dcv_enumerations }}core/region-object-element-type.html?lang=objc,swift)
- [`SectionType`]({{ site.dcv_enumerations }}core/section-type.html?lang=objc,swift)
- [`TransformMatrixType`]({{ site.dcv_enumerations }}core/transform-matrix-type.html?lang=objc,swift)
- [`VideoFrameQuality`]({{ site.dcv_enumerations }}core/video-frame-quality.html?lang=objc,swift)

## DynamsoftUtility

### Classes

- [`DirectoryFetcher`]({{ site.dcv_ios_api }}utility/directory-fetcher.html)
- [`FileFetcher`]({{ site.dcv_ios_api }}utility/file-fetcher.html)
- [`MultiFrameResultCrossFilter`]({{ site.dcv_ios_api }}utility/multi-frame-result-cross-filter.html)
- [`UtilityModule`]({{ site.dcv_ios_api }}utility/utility-module.html)

## DynamsoftCameraEnhancer

### Classes

- [`CameraEnhancer`]({{ site.dce_ios_api }}primary-api/camera-enhancer.html)
- [`CameraEnhancerModule`]({{ site.dce_ios_api }}auxiliary-api/camera-enhancer-module.html)
- [`CameraView`]({{ site.dce_ios_api }}auxiliary-api/dcecameraview.html)
- [`Capabilities`]({{ site.dce_ios_api }}auxiliary-api/capabilities.html)
- [`DrawingItem`]({{ site.dce_ios_api }}auxiliary-api/drawingitem.html)
- [`DrawingLayer`]({{ site.dce_ios_api }}auxiliary-api/dcedrawinglayer.html)
- [`DrawingStyleManager`]({{ site.dce_ios_api }}auxiliary-api/drawingstylemanager.html)
- [`DrawingStyle`]({{ site.dce_ios_api }}auxiliary-api/drawingstyle.html)
- [`Feedback`]({{ site.dce_ios_api }}auxiliary-api/dcefeedback.html)
- [`ImageEditorView`]({{ site.dce_ios_api }}auxiliary-api/dceimageeditorview.html)
- [`LineDrawingItem`]({{ site.dce_ios_api }}auxiliary-api/drawingitem-line.html)
- [`Note`]({{ site.dce_ios_api }}auxiliary-api/note.html)
- [`QuadDrawingItem`]({{ site.dce_ios_api }}auxiliary-api/drawingitem-quad.html)
- [`RectDrawingItem`]({{ site.dce_ios_api }}auxiliary-api/drawingitem-rect.html)
- [`TextDrawingItem`]({{ site.dce_ios_api }}auxiliary-api/drawingitem-text.html)
- [`TipConfig`]({{ site.dce_ios_api }}auxiliary-api/tip-config.html)

### Interfaces

- [`CameraStateListener`]({{ site.dce_ios_api }}auxiliary-api/protocol-dcecamerastatelistener.html)
- [`PhotoListener`]({{ site.dce_ios_api }}auxiliary-api/protocol-dcephotolistener.html)
- [`VideoFrameListener`]({{ site.dce_ios_api }}auxiliary-api/protocol-dceframelistener.html)

### Enumerations

- [`CameraPosition`]({{ site.dcv_enumerations }}camera-position.html?lang=objc,swift)
- [`CameraState`]({{ site.dcv_enumerations }}camera-state.html?lang=objc,swift)
- [`CoordinateBase`]({{ site.dcv_enumerations }}coordinate-base.html?lang=objc,swift)
- [`DrawingItemMediaType`]({{ site.dcv_enumerations }}drawing-item-media-type.html?lang=objc,swift)
- [`DrawingItemState`]({{ site.dcv_enumerations }}drawing-item-state.html?lang=objc,swift)
- [`EnhancedFeatures`]({{ site.dcv_enumerations }}enhanced-features.html?lang=objc,swift)
- [`FocusMode`]({{ site.dcv_enumerations }}focus-mode.html?lang=objc,swift)
- [`Resolution`]({{ site.dcv_enumerations }}resolution.html?lang=objc,swift)

## DynamsoftImageProcessing

### Classes

- [`ImageProcessingModule`]({{ site.dcv_ios_api }}image-processing/image-processing-module.html)

## DynamsoftLicense

### Classes

- [`LicenseManger`]({{ site.dcv_ios_api }}license/license-manager.html)
- [`LicenseModule`]({{ site.dcv_ios_api }}license/license-module.html)
