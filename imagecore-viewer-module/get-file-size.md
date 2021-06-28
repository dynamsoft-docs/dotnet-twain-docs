---
layout: default-layout
title: How to get the file size in the specified format
keywords: dynamic .net twain, get file size
description: How to get the file size in the specified format
needAutoGenerateSidebar: true
---

# How to get the file size in the specified format by index

## From version 7.0

- In JPG, BMP, PNG, TIF 

  You can use the method [`GetImageSizeWithSpecifiedType`](https://www.dynamsoft.com/help/TWAIN/.Net-TWAIN-Scanner/api/M_Dynamsoft_Core_Business_IO_GetImageSizeWithSpecifiedType.htm) to get the file size in JPG, BMP, PNG, TIF.

  For example,

    ```c#
    m_ImageCore = new ImageCore();

    int FileSizeinJPG = m_ImageCore.IO.GetImageSizeWithSpecifiedType(m_ImageCore.ImageBuffer.CurrentImageIndexInBuffer, EnumImageFileFormat.WEBTW_JPG); //Calculates the file size in JPG for the current image.
    ```

- In PDF 

  Since PDF Module has been separated from version 7.0, the supported format for [`GetImageSizeWithSpecifiedType`](https://www.dynamsoft.com/help/TWAIN/.Net-TWAIN-Scanner/api/M_Dynamsoft_Core_Business_IO_GetImageSizeWithSpecifiedType.htm) does not include PDF.

  If you want to get the file size in PDF format, please follow the steps below.

  Step1: Download [Dynamsoft.Core.Util.cs](https://tst.dynamsoft.com/libs/dnt/Dynamsoft.Core.Util.zip) and add it to the solution.
  
  Step2: Refer to the sample code.

  ```c#
  m_ImageCore = new ImageCore();
  m_PDFCreator = new PDFCreator();

  int FileSizeinPDF = Dynamsoft.Core.Util.GetImageSizeWithSpecifiedType(m_ImageCore, m_PDFCreator, m_ImageCore.ImageBuffer.CurrentImageIndexInBuffer, EnumImageFileFormatEx.WEBTW_PDF); //Calculates the file size in PDF for the current image.
  ```


