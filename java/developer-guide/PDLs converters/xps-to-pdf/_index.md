---
title: Convert XPS to PDF using Java
type: docs
weight: 20
url: /java/convert/xps-to-pdf/
description: XPS to PDF conversion functionality included in Aspose.Page API solution for Java is described and illustrated with the code snippets here.
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page XPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/xps-to-pdf">XPS to PDF Converter</a> {{% /alert %}} 

Aspose.Page Java XPS to PDF converter allows to convert XPS document to PDF document on any OS for which Java Virtual Machine exists.
<br>It is necessary to do several steps in order to perform XPS to PDF conversion:
1. Initialize an input stream for input XPS document.
2. Initialize an output stream for output PDF document.
3. Create an instance of [XpsDocument](https://reference.aspose.com/page/java/com.aspose.xps/xpsdocument) from created earlier input stream.
4. Specify **TextCompression**, **ImageCompression**, **JpegQualityLevel**, and other options of [PdfSaveOptions](https://reference.aspose.com/page/java/com.aspose.xps.rendering/pdfsaveoptions).
5. Create an instance of [PdfDevice](https://reference.aspose.com/page/java/com.aspose.xps.rendering/pdfdevice) from created earlier output stream.
6. Save XPS document as PDF with PDF save options. 

<br>Following code snippet shows how to convert XPS to PDF document in Java:
<br>
```Java
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-Java
// The path to the documents directory.
String dataDir = Utils.getDataDir();
// Initialize PDF output stream
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");

// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");

// Initialize options object with necessary parameters.
com.aspose.xps.rendering.PdfSaveOptions options = new com.aspose.xps.rendering.PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(com.aspose.xps.rendering.PdfImageCompression.Jpeg);
options.setTextCompression(com.aspose.xps.rendering.PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });

// Create rendering device for PDF format
com.aspose.xps.rendering.PdfDevice device = new com.aspose.xps.rendering.PdfDevice(pdfStream);

document.save(device, options);
```
{{% alert color="primary" %}}
See XPS to PDF conversion in [.NET](/page/net/convert/xps-to-pdf/) and [C++](/page/cpp/convert/xps-to-pdf/).
{{% /alert %}}

Let's consider [PdfSaveOptions](https://reference.aspose.com/page/java/com.aspose.xps.rendering/pdfsaveoptions). Using this class we can assign different conversion parameters while converting XPS to PDF.
<br>
- **JpegQualityLevel** controls a quality of images in PDF document if **ImageCompression** algorithm is JPEG and can be from 0 to 100.
- **ImageCompression** algorithm encapsulated in [PdfImageCompression](https://reference.aspose.com/page/java/com.aspose.xps.rendering/pdfimagecompression) Enumeration, may be Run Length Encoding (RLE), Flate, Lempel-Ziv-Welch (LZW) with base or optimized pedictor, JPEG , none (raw image bytes) and auto (the most appropriate compression for each image). Default is auto compression.
- **TextCompression** algorithm encapsulated in [PdfTextCompression](https://reference.aspose.com/page/java/com.aspose.xps.rendering/pdftextcompression) Enumeration, may be Run Length Encoding (RLE), Flate, Lempel-Ziv-Welch (LZW) and none. Default value in XPS to PDF conversion is Flate.
- **EncryptionDetails** encapsulated in [PdfEncryptionDetails](https://reference.aspose.com/page/java/com.aspose.xps.rendering/pdfencryptiondetails). It allows setting encryption algorithm, permisions, owner and user passwords for PDF document.
- **PageNumbers** represents an array of numbers of pages which will be saved to PDF.
- **OutlineTreeExpansionLevel** and **OutlineTreeHeight** controls view of document outline.

{{% alert color="primary" %}}
Evaluate XPS to PDF conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/xps-to-pdf">XPS to PDF Converter</a>. You can convert several XPS files to PDF at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-Java). {{% /alert %}}
