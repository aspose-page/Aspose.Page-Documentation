---
title: Merge XPS files to PDF using .NET
type: docs
weight: 20
url: /java/merge/xps/
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page XPS Merger and view the results via free online <a nofollow href="https://products.aspose.app/page/merge/xps">XPS Merger</a> {{% /alert %}} 

Aspose.Page Java XPS merger allows to merge XPS files to PDF document on any OS for which Java Virtual Machine exists.
<br>It is necessary to do several steps in order to perform XPS to PDF merge:
1. Initialize an input stream for the first input XPS document.
2. Initialize an output stream for output PDF document.
3. Create an array of XPS files that will be merged with the first one.
4. Create an instance of [XpsDocument](https://apireference.aspose.com/page/java/com.aspose.xps/xpsdocument) from created earlier input stream.
5. Specify **TextCompression**, **ImageCompression**, **JpegQualityLevel**, and other options of [PdfSaveOptions](https://apireference.aspose.com/page/java/com.aspose.xps.rendering/pdfsaveoptions).
6. Create an instance of [PdfDevice](https://apireference.aspose.com/page/java/com.aspose.xps.rendering/pdfdevice) from created earlier output stream.
7. Merge XPS files with created document and save it as PDF with PDF save options. 

<br>Following code snippet shows how to merge XPS files to PDF document in Java:
<br>
```Java
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-Java
// The path to the documents directory.
String dataDir = Utils.getDataDir();
// Initialize PDF output stream
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");

// Load the first XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");

// Initialize options object with necessary parameters.
com.aspose.xps.rendering.PdfSaveOptions options = new com.aspose.xps.rendering.PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(com.aspose.xps.rendering.PdfImageCompression.Jpeg);
options.setTextCompression(com.aspose.xps.rendering.PdfTextCompression.Flate);

// Create rendering device for PDF format
com.aspose.xps.rendering.PdfDevice device = new com.aspose.xps.rendering.PdfDevice(pdfStream);

// Create an array of XPS files that will be merged with the first one
string[] filesToMerge = new string[] { dataDir + "input2.xps", dataDir + "input3.xps" };

// Merge XPS files to output PDF document
document.merge(filesToMerge, device, options);
```
{{% alert color="primary" %}}
See XPS merge in [.NET](/page/net/merge/xps/) and [C++](/page/cpp/merge/xps/).
{{% /alert %}}

Let's consider [PdfSaveOptions](https://apireference.aspose.com/page/java/com.aspose.xps.rendering/pdfsaveoptions). Using this class we can assign different conversion parameters while merging XPS to PDF.
<br>
- **JpegQualityLevel** controls a quality of images in PDF document if **ImageCompression** algorithm is JPEG and can be from 0 to 100.
- **ImageCompression** algorithm encapsulated in [PdfImageCompression](https://apireference.aspose.com/page/java/com.aspose.xps.rendering/pdfimagecompression) Enumeration, may be Run Length Encoding (RLE), Flate, Lempel-Ziv-Welch (LZW) with base or optimized pedictor, JPEG , none (raw image bytes) and auto (the most appropriate compression for each image). Default is auto compression.
- **TextCompression** algorithm encapsulated in [PdfTextCompression](https://apireference.aspose.com/page/java/com.aspose.xps.rendering/pdftextcompression) Enumeration, may be Run Length Encoding (RLE), Flate, Lempel-Ziv-Welch (LZW) and none. Default value in XPS to PDF merging is Flate.
- **EncryptionDetails** encapsulated in [PdfEncryptionDetails](https://apireference.aspose.com/page/java/com.aspose.xps.rendering/pdfencryptiondetails). It allows setting encryption algorithm, permisions, owner and user passwords for PDF document.
- **OutlineTreeExpansionLevel** and **OutlineTreeHeight** controls view of document outline.

{{% alert color="primary" %}}
Evaluate XPS merging online on our <a nofollow href="https://products.aspose.app/page/merge/xps">XPS Meger</a>.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-Java). {{% /alert %}}
