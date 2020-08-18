---
title: Convert PostScript to PDF
type: docs
weight: 40
url: /net/convert-postscript-to-pdf/
---

# **Convert PostScript to PDF**
{{% alert color="primary" %}} 

You can check the quality of Aspose.Page conversion and view the results online at this link:

[products.aspose.app/page/conversion/ps-to-pdf](https://products.aspose.app/page/conversion/ps-to-pdf) {{% /alert %}} 

Aspose.Page for .NET offers **PdfSaveOptions** class, with which you can convert a PS file into PDF document. You can specify **JpegQualityLevel**, and other options of PdfSaveOptions and save PS document as PDF document using **Save** method of **PsDocument** class. You can boolean value while initializing PdfSaveOptions which tells the converter whether to suppress errors or not. If the value is set to true, you can print encountered error later from **Exception** Enumeration of **PsConverterException**. Following code snippet shows how to convert PS document to PDF document:

{{< gist "aspose-com-gists" "6f0d8b5420af1af6af2d064587dd6803" "Examples-Aspose.Page.Examples.CSharp-WorkingWithDocumentConversion-PostScriptToPdf-1.cs" >}}

The generated PDF document will show "Aspose.Page for .NET" as producer or creator of the document in properties of the PDF and it cannot be changed.
