---
layout: default-layout
title: Dynamic .NET TWAIN Schedule - Stable Release
keywords: Dynamic .NET TWAIN, Documentation, Schedule, Stable Release
breadcrumbText: Stable Releases
description: Dynamic .NET TWAIN SDK Documentation Schedule Stable Release Page
needAutoGenerateSidebar: true
---

# Stable Releases

## 8.3.3 (07/27/2021)

### FIXED

* Fixed some minor bugs about scanning.

## 8.3 (07/19/2021)

### NEW

* Added support for .NET Core 3.1 and .NET 5.

### FIXED

* Fixed the bug that the Scanner UI will close automatically after 2 minutes if nothing is done.
* Fixed the bug that the Ratio of Rectangle still changes after setting `SelectionRectAspectRatio`.
* Fixed some other minor bugs.

## 8.1.2 (02/20/2020)

### NEW

* Added a new property `extendedImageInfoQueryLevel` for the method `AcquireImage` that allows setting up how the library queries extended image info items. In version 8.1, the default level would result in scanning failure or serious performance issues with some scanners.

### FIXED

* Fixed the handle leak issue of OCR.

* Fixed the bug that the extended image info messages are not returned when setting `IfGetExtendedImageInfo` to true.

* Fixed the bug that mouse scroll moving up only.

* Fixed the bug that `cameraManager.Dispose` will throw an exception when there is no camera connected.

* Fixed the bug that some HD cameras failed to initialize.

### CHANGED

* Some optimizations on the samples.

## 8.1 (12/03/2019)

### NEW

* Added `SetDPI` method to change the DPI (dots per inch) of an image specified by index.

* Added `SetOpenSourceTimeout` method to set the time-out used to open a specified Data Source.

### IMPROVED

* Improved the method `AcquireImage` by adding two more options `IfGetImageInfo` & `IfGetExtImageInfo` to its callback `IAcquireCallback` which are true by default and means extra image info will be returned with each transferred image. The info could be returned by the event `OnPostTransfer`.

* Improved the method `SetFileXFERInfo` so that you can specify a naming pattern for the transferred images when the transfer mode is `Disk` File.

### FIXED

* Fixed the memory leak issue of the Webcam Capture Sample.

* Fixed a bug where the captured images in the container do not rotate when the video stream has been rotated.

* Fixed a bug where loading PDF file throws an exception when `Convert Mode` is set to Auto.

* Other minor fixes and tweaks.

### CHANGED

* Added Image Editor Sample.

## 8.0 (07/03/2018)

### NEW

* Added `CreateBarcode` method to create a barcode image in the Barcode Generator Module.

* Added `ScanInNewProcess` property for acquiring image in an independent 32-bit process in the TWAIN Scan Module.

* Updated the scanning process.

### IMPROVED

* Improved OCR accuracy & speed by using a newer library.

* Improved the rendering performance of the PDF Library.

* Improved the compatibility with higher resolution of Webcam in the Webcam Module.

* Improved the performance of the samples.

### FIXED

* Fixed the bug that the exception cannot be thrown if there is a scanning error.

* Fixed an issue where you can't save multiple images in disk mode.

* Other minor fixes and tweaks.

### CHANGED

* Removed `Encrypt` & `Merge` methods.

* Very high resolutions are hidden in the Webcam Module to stop the application from crashing.

## 7.1 (06/29/2017)

### NEW

* Added `SaveAsTIFF` method to save images as multi-page TIFF in bytes.

### IMPROVED

* Deleted unused namespaces and classes.

* Decreased the memory consumption of the video stream in the Webcam module.

* Improved the interface of the demo guide program and the samples.

### FIXED

* Fixed a bug where setting the Value of Zoom throws an error in the Webcam module.

* Fixed an issue where the resolution of the output PDF is fixed to 72 dpi in the PDF Library for images whose width/height is less than 2000.

* Fixed a bug where the mouse flashes when an area is selected in the **Viewer** module.

* Other minor fixes and tweaks.

## 7.0 (05/03/2017)

### IMPROVED

* Modularized the following into separate modules - **TWAIN Scan**, **UVC Camera**, **PDF**, **Barcode Generator**, **Barcode Reader**, **OCR**, **Image Core** and **Image Viewer**.

### CHANGED

* Removed the Image Editor from the core product.

## 6.2 (09/21/2016)

### NEW

* Added features to the PDF Rasterizer add-on:
    - `MergePDFFiles` method: merge multiple PDF files into a single PDF file.
    - `EncryptPDFFile` method: encrypt a PDF file with password and permissions on disk and save the results as a new PDF file.
    - `PDFConvertMode` property: set the convert mode for PDF files.
    - `SetPDFResolution` method: set the resolution for converting PDF to image.

* Added `BestQuality` to `DWTInterpolationMethod` class.

* Added `OnFrameCapture` event which is triggered when a frame is captured by WebCam.

* Added `OnPrePageLoad` event which is triggered before every page of a local image is loaded.

* Added `OnPostPageLoad` event which is triggered after every page of a local image is loaded.

### IMPROVED

* Improved the compatibility of the annotation generated by PDF Annotation add-on with other PDF tools.

* Improved the JPEG Compression type of `TiffCompressionType`.

* Improved the logic of load and download related functions to work better with the PDF Rasterizer.

* Improved sample applications to support Visual Studio 2015.

### FIXED

* Fixed an issue where PDF files will be loaded multiple times when executing ConvertPDFToImage.

* Fixed an issue where the process can't be killed when ScanInNewProcess fails.

* Other minor fixes and tweaks.

## 6.1 (12/29/2015)

### NEW

* Added `GetBitmap` method to convert an image to a Bitmap so that you can read a barcode from a Bitmap image in WPF applications.

* Added `Rotate` and `FocusOnArea` functionalities in the Dynamic .NET TWAIN built-in webcam User Interface.

### IMPROVED

* Changed the name of the barcode generator add-on dll from DynamicBarcode(x64).dll to DynamicBarcodeGenerator(x64).dll and separated the Barcode Generator add-on and Barcode Reader add-on. In other words, the barcode reader and generator add-ons are now built into individual dll assemblies.

* Changed `RotateVideo` method so that it rotates the video by a certain degree from its original orientation instead of the current orientation.

* Removed Dynamsoft related information from the Dynamic .NET TWAIN built-in Image Editor.

### FIXED

* Fixed a bug where `IsBlankImage` crashes in certain cases.

* Fixed an issue where the core product is not compatible with the old barcode reader add-on.

* Fixed an issue where `FocusOnArea` method doesn’t work when running the executable outside of Visual Studio.

* Other minor fixes and tweaks.

# 6.0 (11/17/2015)

### NEW

* Added WPF version of Dynamic .NET TWAIN Webcam Module.

* Added a new method `LoadImage(Image)` to load an image from an Image object.

* Added a new method `FocusOnArea(Rectangle)` to focus on a specified area.

* Added a new method `RotateVideo(RotationType)` to rotate your video.

* Added a new event `OnPostLoad` which can be triggered when an image from a local directory is loaded into the control.
* Added a new property `IfPrintAnnotations` to print annotations.

* Added a new property `PDFVersion` to set the version info for saving PDF files (PDF Rasterizer add-on does not support it yet).

### IMPROVED

* Replaced old Barcode Reader add-on with Dynamsoft Barcode Reader for better performance.

* Replaced old PDF Rasterizer add-on with a brand new rasterizer for better performance. All relative APIs remain the same.

* Improved license verification mechanism to ease the upgrade of trial version to full version.

### FIXED

* Fixed a bug where some special PDF files are rotated by 90 degree automatically when being loaded into the control.

* Fixed an issue where the control would crash or stop working when loop loading some PDF files if one of them is corrupted.

* Fixed an issue where image transfer failed when `GetImageInfo` and `GetBarcodeInfo` throw an error.

* Fixed a bug where the property `CapIfSupported` returns wrong value.

* Other minor fixes and tweaks.

## 5.4.1 (01/27/2015)

### IMPROVED

* Improved 2D barcode reader add-on performance, especially for PDF417 and QRCode.

* Improved barcode decoding accuracy for PDF417.

* Other minor fixes and tweaks.

## 5.4 (10/15/2014)

### NEW

* Improved 1D barcode reader add-on in both barcode decoding accuracy and performance, especially for Code 39 and Code 128.

* Improved WPF control of Dynamic .NET TWAIN in the performance of image displaying.

* Improved speed for multi-page PDF loading and viewing.

* Added new method `ConvertPDFToImage(byte[], resolution)` for converting PDF byte array to images.

* Other minor fixes and tweaks.

## 5.3 (07/22/2014)

### NEW
* Added `ScanInNewProcess` property for acquiring images in an independent 32-bit process. With the new process, you can now access 32-bit TWAIN scanners from 64-bit applications.

* Other minor fixes and tweaks.

## 5.2 (04/29/2014)

### NEW

* PDF Rasterizer, which performs high-quality conversion from a PDF file (image-based or text-based) to an image. In this way, the output image can be successfully loaded into Dynamic .NET TWAIN.

* 1D & 2D Barcode Generator, which allows you to generate a barcode and add it to a specified area on an image loaded in Dynamic .NET TWAIN. The supported barcode types are
   * 1D Barcode Reader SDK
      - Code 39, Code 128
   * 2D Barcode Reader SDK
      - QR Code, PDF417 (MicroPDF417 not supported)

* Added OCR methods
`GetOCRResultPageSetCount`, `GetOCRResultPageCount`, `GetOCRResultLineCount`, `GetOCRResultWordsCount`,
`GetOCRResultLineRect`, `GetOCRResultWordsRect`, `GetOCRResultWordsFontSize`, `GetOCRResultWordsFontName`,
`GetOCRResultWordsText`.

* Added support for loading encrypted PDF files.

* Other minor fixes and tweaks.

## 5.1 (01/14/2014)

### NEW

* Optimized memory usage of both Dynamic .NET TWAIN WinForm and WPF controls.

* `Print` method is added to the WPF control.

* A user-friendly demo guide program - "Dynamic .NET TWAIN SDK" - is now available. You can run it from the shortcut icon on the desktop and have an overall view of all demos & sample code.

* A developer's guide (PDF) is added to *installation path\Dynamsoft\Dynamic .NET TWAIN 5.1 Trial\Documentation*. It helps developers learn how to use the Dynamic .NET TWAIN component step by step.

* Other minor fixes and tweaks.

## 5.0 (12/03/2013)

### NEW

* Added WPF version of Dynamic .NET TWAIN, which makes it easier to integrate document scanning feature into your WPF applications.

* Added an `IfShowCancelDialogWhenBarcodeOrOCR` property to display a progress bar while doing barcode or OCR.

* Added an `OnWaitForEnd` event to detect the beginning and ending of Barcode/OCR progress.

* Changed the way trial notification is displayed to make it more friendly.

* Added GIF format support for load and download methods.

* Added JPEG Compression type to `TiffCompressionType`.

* Upgraded Tesseract OCR engine for OCR add-on. It now supports saving OCR result into PDF/A 1-b.

* Improved the `Print` method so that users are able to print the desired number of pages instead of just all of them.

* Other minor fixes and tweaks.

## 4.3 (06/04/2013)

### NEW

* Greatly improved speed and robustness of the barcode recognition.

* Added property `BarcodeDllPath` to return or set the barcode dll path.

* Added property `LicenseKeys` for flexible licensing.

* Added property `SelectionRectAspectRatio` to return or set the selection rectangle aspect ratio.

* Added methods `SetSelectionRectPosition`, `GetSelectionRect` and `ClearSelectionRect` to manipulate the selection rectangle.

* Improved the OCR method to enable recognition for a certain area.

* Added method `EnableSourceUI` to change and save scanner profiles.

* Added property `MaxBarcodesToRead` to get or set the maximum number of barcodes to be detected.

* Improved method `Print` for flexible print settings.

* Added methods `GetImageIndexByGuid`, `GetImageGuidByIndex` and `SetImageGuidByIndex` to manage scanned images by its GUID (Globally Unique Identifier).

* Added an advanced sample. Improved the barcode and OCR demos.

* Changed the way trial notification is displayed to make it more friendly.

* Other minor fixes and tweaks.

## 4.2 (01/18/2013)

### NEW

* Added `GetSourceType` method to detect source type, i.e. scanner or webcam.

* Added `GetSkewAngle` and `GetSkewAngleEx` methods to calculate skew angle of scanned image. It can be used with `Rotate` (or `RotateEx`) method for deskew purpose.

* Improved performance of Barcode Reader add-on.

* Improved PDF decoder for better compatibility.

* Improved the performance and compatibility of webcam model.

* Improved image display quality in the image viewer by using Windows GDI+ Draw Mode.

### FIXED

* Fixed bug where accessing scanner via Events leads to scanner hang with `ScanInNewThread` enabled.

* Fixed bug where image DPI changed (in rare cases) after calling `LoadImage` method.

* Fixed a few minor bugs of webcam model and OCR add-on.

## 4.1 (06/12/2012)

### NEW

* Added new add-on: OCR (Optical Character Recognition) - OCR documents in different languages and convert them to searchable PDF/text.

* Other minor fixes and tweaks.

## 4.0 (04/17/2012)

### NEW

* Added new add-on: Annotation - markup and draw objects onto a PDF document.

* Added new add-on: Barcode (1D) - support 1D barcode recognition.

* Added new add-on: Barcode (2D) - support 2D barcode recognition.

* Added new add-on: Webcam - acquire an image from a webcam, edit and then upload to a database or web server.

* Supports TWAIN Specification 2.1.

* Added `ScanInNewThread` property to allow Dynamic .NET TWAIN to communicate with the scanner in a separate thread.

* Added `OnSourceUIClose` event which is triggered after the user closes the scanner UI.

* Added `CapValueType` property.

* Added `IfUseTWAINDSM` property.

* Other new methods, events and properties for the add-ons.

* Other minor fixes and tweaks.

## 3.0 (10/11/2011)

### NEW

* Image Annotation supported.

* Print supported.

* Added support for fitting image width or height to viewer window by setting the property `FitWindowType`.

* Added property `IfShowPrintUI` to show the UI of the printer.

* Added more image processing methods including `Invert` and `GrayScale`.

### Details:

#### NEW

* New properties:
`IfShowPrintUI`, `FitWindowType`, `AnnotationTextFont`, `AnnotationTextColor`, `AnnotationPen`, `AnnotationFillColor`, `AnnotationType`,
`LogLevel`, `IfSaveAnnotations`.

* New methods:
`Print`, `Invert`, `GrayScale`, `GetAllAnnotationDataList`, `LoadAnnotationDataList`, `GetSelectedAnnotationList`, `CreateAnnotation`,
`UpdateAnnotation`, `DeleteAnnotations`, `ChangeAnnotationPosition`.

* New events:
`OnAnnotationSelected`, `OnAnnotationDeselected`, `OnAnnotationCreated`, `OnAnnotationMoved`, `OnAnnotationResized`,
`OnAnnotationTextChanged`.

## 2.0 (2/22/2011)

### NEW

* Microsoft .NET Framework 2.0 and above supported.

* Added support for running under any CPU (x86-32bit; x64-64bit). Under x86, all 32-bit drivers can be found. Under x64, 64-bit drivers can be found and used.

* Added `PDFPageSize` property to set the page size of PDF files. All page size values listed in `DWTPDFPageSize` are supported.

* Added properties to set the PDF margins: `PDFMarginBottom`, `PDFMarginLeft`, `PDFMarginRight`, `PDFMarginTop`.

* Optimized the zoom feature: smoother transformation when zooming in/out an image.

* Added methods to save the settings of the user interface of the source: `SaveCustomDSData`, `SaveCustomDSDataEx`.

* Added methods to restore the saved settings of the user interface: `LoadCustomDSData`, `LoadCustomDSDataEx`.

* Other minor fixes and tweaks.

## 1.0.1 (3/9/2010)

### NEW

* Improved PDF compatibility.

## 1.0 (1/20/2010)

### NEW

* Dynamic .NET TWAIN 1.0 released!


