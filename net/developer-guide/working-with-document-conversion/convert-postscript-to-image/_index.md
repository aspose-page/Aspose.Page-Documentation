---
title: Convert PostScript to Image
type: docs
weight: 30
url: /net/convert-postscript-to-image/
---

# **Convert PostScript to Image**
{{% alert color="primary" %}} 

You can check the quality of Aspose.Page conversion and view the results online at this links:

[products.aspose.app/page/conversion/ps](https://products.aspose.app/page/conversion/ps),
[products.aspose.app/page/viewer/ps](https://products.aspose.app/page/viewer/ps). {{% /alert %}} 

Aspose.Page for .NET offers **ImageSaveOption** Class, with which you can convert a PS file into an image file. You can specify **JpegQualityLevel**, and other options of ImageSaveOptions and save PS document as an image file using **Save** method of **PsDocument** class. You can use a boolean value while initializing ImageSaveOptions which tells the converter whether to suppress errors or not. If the value is set to true, you can print encountered error later from **Exception** Enumeration of **PsConverterException**. Following code snippet shows how to convert PS document to an image file:



{{< gist "aspose-com-gists" "6f0d8b5420af1af6af2d064587dd6803" "Examples-Aspose.Page.Examples.CSharp-WorkingWithDocumentConversion-PostScriptToImage-1.cs" >}}
