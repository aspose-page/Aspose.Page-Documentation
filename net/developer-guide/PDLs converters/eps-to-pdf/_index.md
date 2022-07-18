---
title: Convert EPS to PDF using .NET
type: docs
weight: 20
url: /net/convert/eps-to-pdf/
description: EPS to PDF conversion functionality offered by Aspose.Page API solution for .NET is explained and illustrated with the code snippets here.
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a> {{% /alert %}} 

Aspose.Page for .NET EPS to PDF converter allows to convert Encapsulated PostScript (EPS) file to PDF document with using of any language supported by .Net platform: C#, VB, J#.
<br>It is necessary to do several steps in order to perform EPS to PDF conversion:
1. Initialize an input stream for input EPS file.
2. Initialize an output stream for output PDF document.
3. Create an instance of [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument) from created earlier input stream.
4. Use [PdfSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pdfsaveoptions) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
5. Create an instance of [PdfDevice](https://reference.aspose.com/page/net/aspose.page.eps.device/pdfdevice) from created earlier output stream.
6. Save PostScript document as PDF with PDF save options.
7. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during conversion of EPS to PDF and saved in **Exceptions** list.

<br>Following code snippet shows how to convert EPS to PDF document in C#:
<br>
```C#
/ For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-.NET
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithDocumentConversion();
// Initialize PDF output stream
System.IO.FileStream pdfStream = new System.IO.FileStream(dataDir + "outputPDF_out.pdf", System.IO.FileMode.Create, System.IO.FileAccess.Write);
// Initialize PostScript input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);

// If you want to convert Postscript file despite of minor errors set this flag
bool suppressErrors = true;

//Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions(suppressErrors);
// If you want to add special folder where fonts are stored. Default fonts folder in OS is always included.
options.AdditionalFontsFolders = new string[] { @"{FONT_FOLDER}" };

// Default page size is 595x842 and it is not mandatory to set it in PdfDevice
Aspose.Page.EPS.Device.PdfDevice device = new Aspose.Page.EPS.Device.PdfDevice(pdfStream);
// But if you need to specify size use following line
//Aspose.Page.EPS.Device.PdfDevice device = new Aspose.Page.EPS.Device.PdfDevice(pdfStream, new System.Drawing.Size(595, 842));

try
{
    document.Save(device, options);
}
finally
{
    psStream.Close();
    pdfStream.Close();
}

//Review errors
if (suppressErrors)
{
    foreach (PsConverterException ex in options.Exceptions)
    {
        Console.WriteLine(ex.Message);
    }
}
```
{{% alert color="primary" %}}
See EPS to PDF conversion in [Java](/page/java/convert/eps-to-pdf/) and [C++](/page/cpp/convert/eps-to-pdf/).
{{% /alert %}}

Let's consider [PdfSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pdfsaveoptions). Using this class we can assign different conversion parameters while converting EPS to PDF.
<br>
- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.
- **SuppressError** controls behaviour of EPS to PDF converter when non-critical errors are appeared. If value is true than it is possible to view a list of such errors after conversion in **Exceptions** field. Default value is true.
- **Debug** allows outputting debug information to console. Default value is false.

{{% alert color="primary" %}}
Evaluate EPS to PDF conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a>. You can convert several EPS files to PDF at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 