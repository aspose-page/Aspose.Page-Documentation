---
title: Convert XPS to PDF
type: docs
weight: 20
url: /net/convert/xps-to-pdf/
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page conversion and view the results online at this link:

[products.aspose.app/page/conversion/xps-to-pdf](https://products.aspose.app/page/conversion/xps-to-pdf) {{% /alert %}} 

Aspose.Page .NET XPS to PDF converter allows to convert XPS document to PDF document with using of any language supported by .Net platform: C#, VB, J#.
<br>It is necessary to do several steps in order to perform XPS to PDF conversion:
1. Initialize an input stream for input XPS document.
2. Initialize an output stream for output PDF document.
3. Create an instance of [XpsDocument](https://apireference.aspose.com/page/net/aspose.page.xps/xpsdocument) from created earlier input stream.
4. Specify **TextCompression**, **ImageCompression**, **JpegQualityLevel**, and other options of [PdfSaveOptions](https://apireference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdfsaveoptions).
5. Create an instance of [PdfDevice](https://apireference.aspose.com/page/net/aspose.page.xps.presentation.pdf/pdfdevice) from created earlier output stream.
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

