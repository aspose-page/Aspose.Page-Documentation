---
title: Convert XPS to PDF
type: docs
weight: 20
url: /java/convert/xps-to-pdf/
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page conversion and view the results online at this link:

[products.aspose.app/page/conversion/xps-to-pdf](https://products.aspose.app/page/conversion/xps-to-pdf) {{% /alert %}} 

Aspose.Page Java XPS to PDF converter allows to convert XPS document to PDF document on any OS for which Java Virtual Machine exists.
<br>It is necessary to do several steps in order to perform XPS to PDF conversion:
1. Initialize an input stream for input XPS document.
2. Initialize an output stream for output PDF document.
3. Create an instance of [XpsDocument](https://apireference.aspose.com/page/java/com.aspose.xps/xpsdocument) from created earlier input stream.
4. Specify **TextCompression**, **ImageCompression**, **JpegQualityLevel**, and other options of [PdfSaveOptions](https://apireference.aspose.com/page/java/com.aspose.xps.rendering/pdfsaveoptions).
5. Create an instance of [PdfDevice](https://apireference.aspose.com/page/java/com.aspose.xps.rendering/pdfdevice) from created earlier output stream.
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

