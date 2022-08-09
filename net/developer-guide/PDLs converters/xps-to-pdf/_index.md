---
title: Convert XPS to PDF using .NET
type: docs
weight: 20
url: /net/convert/xps-to-pdf/
description: XPS to PDF conversion functionality included in Aspose.Page API solution for .NET is described and illustrated with the code snippets here.
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page XPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/xps-to-pdf">XPS to PDF Converter</a> {{% /alert %}} 

Aspose.Page .NET XPS to PDF converter allows to convert XPS document to PDF document with using of any language supported by .Net platform: C#, VB, J#.
<br>It is necessary to do several steps in order to perform XPS to PDF conversion:
1. Initialize an input stream for input XPS document.
2. Initialize an output stream for output PDF document.
3. Create an instance of [XpsDocument](https://reference.aspose.com/page/net/aspose.page.xps/xpsdocument/) from created earlier input stream.
4. Specify **TextCompression**, **ImageCompression**, **JpegQualityLevel**, and other options of [PdfSaveOptions](https://reference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdfsaveoptions/).
5. Create an instance of [PdfDevice](https://reference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdfdevice/) from created earlier output stream.
6. Save XPS document as PDF with PDF save options. 

<br>Following code snippet shows how to convert XPS to PDF document in C#:
<br>
```C#
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-.NET
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithDocumentConversion();
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "XPStoPDF.pdf", System.IO.FileMode.Open, System.IO.FileAccess.Read))
{
    // Load XPS document form the stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // or load XPS document directly from file. No xpsStream is needed then.
    // XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());

    // Initialize options object with necessary parameters.
    Aspose.Page.XPS.Presentation.Pdf.PdfSaveOptions options = new Aspose.Page.XPS.Presentation.Pdf.PdfSaveOptions()
    {
        JpegQualityLevel = 100,
        ImageCompression = Aspose.Page.XPS.Presentation.Pdf.PdfImageCompression.Jpeg,
        TextCompression = Aspose.Page.XPS.Presentation.Pdf.PdfTextCompression.Flate,
        PageNumbers = new int[] { 1, 2, 6 }
    };

    // Create rendering device for PDF format
    Aspose.Page.XPS.Presentation.Pdf.PdfDevice device = new Aspose.Page.XPS.Presentation.Pdf.PdfDevice(pdfStream);

    document.Save(device, options);
}
```
{{% alert color="primary" %}}
See XPS to PDF conversion in [Java](/page/java/convert/xps-to-pdf/) and [C++](/page/cpp/convert/xps-to-pdf/).
{{% /alert %}}

Let's consider [PdfSaveOptions](https://reference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdfsaveoptions/). Using this class we can assign different conversion parameters while converting XPS to PDF.
<br>
- **JpegQualityLevel** controls a quality of images in PDF document if **ImageCompression** algorithm is JPEG and can be from 0 to 100.
- **ImageCompression** algorithm encapsulated in [PdfImageCompression](https://reference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdfimagecompression/) Enumeration, may be Run Length Encoding (RLE), Flate, Lempel-Ziv-Welch (LZW) with base or optimized pedictor, JPEG , none (raw image bytes) and auto (the most appropriate compression for each image). Default is auto compression.
- **TextCompression** algorithm encapsulated in [PdfTextCompression](https://reference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdftextcompression/) Enumeration, may be Run Length Encoding (RLE), Flate, Lempel-Ziv-Welch (LZW) and none. Default value in XPS to PDF conversion is Flate.
- **EncryptionDetails** encapsulated in [PdfEncryptionDetails](https://reference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdfencryptiondetails/). It allows setting encryption algorithm, permisions, owner and user passwords for PDF document.
- **PageNumbers** represents an array of numbers of pages which will be saved to PDF.
- **OutlineTreeExpansionLevel** and **OutlineTreeHeight** controls view of document outline.

{{% alert color="primary" %}}
Evaluate XPS to PDF conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/xps-to-pdf">XPS to PDF Converter</a>. You can convert several XPS files to PDF at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 