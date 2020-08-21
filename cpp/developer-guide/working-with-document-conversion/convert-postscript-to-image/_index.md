---
title: Convert PostScript to Image
type: docs
weight: 10
url: /cpp/convert-postscript-to-image/
---

It is a common requirement to convert PostScript (PS) files to Image file format. Aspose.Page for C++ lets you read the PS document and convert it to an image. In order to convert a PS file to image, the following steps can be used.

1. Create a document of PsDocument class with stream
1. Create an object of ImageSaveOptions
1. Create an object of ImageDevice class
1. Use the JpegQualityLevel class to specify the quality of output image
1. Use the Save method to save the image to disc

{{% alert color="primary" %}}

You can use a boolean value while initializing ImageSaveOptions which tells the converter whether to suppress errors or not. If the value is set to true, you can print encountered errors later from **Exception** Enumeration of **PsConverterException**.

{{% /alert %}}  

{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-PostScriptToImage-PostScriptToImage.cpp" >}}
