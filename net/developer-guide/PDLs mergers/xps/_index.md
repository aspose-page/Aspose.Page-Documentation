---
title: Merge XPS files to PDF using .NET
type: docs
weight: 20
url: /net/merge/xps/
description: Merger XPS functionality of Aspose.Page API solution for .NET allows you to combine several XPS files into a single PDF document.
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page XPS merger and view the results via free online <a nofollow href="https://products.aspose.app/page/merger/xps">XPS Merger</a> {{% /alert %}} 

Aspose.Page .NET XPS Merge allows to merge XPS files to PDF document with using of any language supported by .NET platform: C#, VB, J#.
<br>It is necessary to do several steps in order to perform XPS to PDF merge:
1. Initialize an input stream for the first input XPS document.
2. Initialize an output stream for output PDF document.
3. Create an array of XPS files that will be merged with the first one.
4. Create an instance of [XpsDocument](https://apireference.aspose.com/page/net/aspose.page.xps/xpsdocument) from created earlier input stream.
5. Specify **TextCompression**, **ImageCompression**, **JpegQualityLevel**, and other options of [PdfSaveOptions](https://apireference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdfsaveoptions).
6. Create an instance of [PdfDevice](https://apireference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdfdevice) from created earlier output stream.
7. Merge XPS files with created document and save it as PDF with PDF save options. 

<br>Following code snippet shows how to merge XPS files to PDF document in C#:
<br>
```C#
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-.NET
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithDocumentMerging();
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "mergedXPSfiles.pdf", System.IO.FileMode.Create, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open, System.IO.FileAccess.Read))
{
    // Load the first XPS document from the stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // or load XPS document directly from file. No xpsStream is needed then.
    // XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());

    // Initialize options object with necessary parameters.
    Aspose.Page.XPS.Presentation.Pdf.PdfSaveOptions options = new Aspose.Page.XPS.Presentation.Pdf.PdfSaveOptions()
    {
        JpegQualityLevel = 100,
        ImageCompression = Aspose.Page.XPS.Presentation.Pdf.PdfImageCompression.Jpeg,
        TextCompression = Aspose.Page.XPS.Presentation.Pdf.PdfTextCompression.Flate
    };

    // Create rendering device for PDF format
    Aspose.Page.XPS.Presentation.Pdf.PdfDevice device = new Aspose.Page.XPS.Presentation.Pdf.PdfDevice(pdfStream);
    
    // Create an array of XPS files that will be merged with the first one
    string[] filesToMerge = new string[] { dataDir + "input2.xps", dataDir + "input3.xps" };

		// Merge XPS files to output PDF document
    document.Save(filesToMerge, device, options);
}
```
{{% alert color="primary" %}}
See XPS merge in [Java](/page/java/merge/xps/) and [C++](/page/cpp/merge/xps/).
{{% /alert %}}

Let's consider [PdfSaveOptions](https://apireference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdfsaveoptions). Using this class we can assign different conversion parameters while merging XPS files to PDF.
<br>
- **JpegQualityLevel** controls a quality of images in PDF document if **ImageCompression** algorithm is JPEG and can be from 0 to 100.
- **ImageCompression** algorithm encapsulated in [PdfImageCompression](https://apireference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdfimagecompression) Enumeration, may be Run Length Encoding (RLE), Flate, Lempel-Ziv-Welch (LZW) with base or optimized pedictor, JPEG , none (raw image bytes) and auto (the most appropriate compression for each image). Default is auto compression.
- **TextCompression** algorithm encapsulated in [PdfTextCompression](https://apireference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdftextcompression) Enumeration, may be Run Length Encoding (RLE), Flate, Lempel-Ziv-Welch (LZW) and none. Default value in XPS to PDF merging is Flate.
- **EncryptionDetails** encapsulated in [PdfEncryptionDetails](https://apireference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdfencryptiondetails). It allows setting encryption algorithm, permisions, owner and user passwords for PDF document.
- **OutlineTreeExpansionLevel** and **OutlineTreeHeight** controls view of document outline.

{{% alert color="primary" %}}
Evaluate XPS merging online on our <a nofollow href="https://products.aspose.app/page/merger/xps">XPS Merger</a>.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 