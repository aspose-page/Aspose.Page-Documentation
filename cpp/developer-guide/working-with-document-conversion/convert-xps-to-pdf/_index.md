---
title: Convert XPS to PDF
type: docs
weight: 40
url: /cpp/convert-xps-to-pdf/
---

Aspose.Page for C++ lets you convert XPS to PDF. The PdfSaveOptions class is used to convert XPS documents to PDF. It allows you to specify additional saving options using the TextCompression, ImageCompression, JpegQualityLevel and other associated classes. In order to convert XPS to PDF, use the following steps.

1. Load the input XPS document as a stream
1. Create an XpsDocument object from this stream
1. Specify save options using the PdfSaveOptions class
1. Instantiate a new object of PdfDevice with XPS stream
1. Save the document as PDF using the save options

The following C++ code shows how to convert XPS to PDF.



{{< gist "aspose-com-gists" "6f0d8b5420af1af6af2d064587dd6803" "Examples-Aspose.Page.Examples.CSharp-WorkingWithDocumentConversion-XPStoPDF-1.cs" >}}
