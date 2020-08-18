---
title: Convert PostScript to PDF
type: docs
weight: 20
url: /cpp/convert-postscript-to-pdf/
---

# **Convert PostScript to PDF**
Aspose.Page for C++ lets you convert PostScript (PS) documents to PDF. The PdfSaveOptions class is used to convert a PS file to PDF document. In order to control the output quality, the quality parameters can be specified using the JpegQualityLevel parameter. The following steps summarize how to convert PS files to PDF.

1. Load the input PostScript document in stream
1. Instantiate an instance of [PsDocument](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.ps_document/) with this file stream
1. Use the [PdfSaveOptions](https://apireference.aspose.com/page/cpp/class/aspose.page.save_options/) class to specify desired parameters
1. Save the document to PDF

Following C++ code demonstrates the conversion of PS files to PDF.



{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-PostScriptToPdf-PostScriptToPdf.cpp" >}}

{{% alert color="primary" %}} 

The generated PDF document will show "Aspose.Page for C++" as producer or creator of the document in properties of the PDF and it cannot be changed.

{{% /alert %}}
