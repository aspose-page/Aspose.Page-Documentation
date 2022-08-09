---
title: Merge PostScript files to PDF using .NET
type: docs
weight: 20
url: /net/merge/ps/
description: Merger PS functionality of Aspose.Page API solution for .NET allows you to combine a few PS files into a single PDF document.
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page PS Merger and view the results via free online <a nofollow href="https://products.aspose.app/page/merger/ps">PostScipt Merger</a> {{% /alert %}} 

Aspose.Page for .NET PS Merger allows to merge PostScript (PS) files to PDF document with using of any language supported by .NET platform: C#, VB, J#.
<br>It is necessary to do several steps in order to perform PS merge:
1. Initialize an input stream for the first input PS file.
2. Initialize an output stream for output PDF document.
3. Create an array of PS files that will be merged with the first one.
4. Create an instance of [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) from created earlier input stream.
5. Use [PdfSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pdfsaveoptions/) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
6. Create an instance of [PdfDevice](https://reference.aspose.com/page/net/aspose.page.eps.device/pdfdevice/) from created earlier output stream.
7. Merge PostScript files with created document and save it as PDF with PDF save options.
8. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during merging of PS files to PDF document and saved in **Exceptions** list.

<br>Following code snippet shows how to merge PS files to PDF document in C#:
<br>
```C#
/ For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-.NET
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithDocumentMerging();
// Initialize PDF output stream
System.IO.FileStream pdfStream = new System.IO.FileStream(dataDir + "outputPDF_out.pdf", System.IO.FileMode.Create, System.IO.FileAccess.Write);
// Initialize the first PostScript file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "input.ps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);

// Create an array of PostScript file that will be merged with the first one
string[] filesForMerge = new string[] { dataDir + "input2.ps", dataDir + "input3.ps" };

// If you want to merge Postscript files despite of minor errors set this flag
bool suppressErrors = true;

//Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions(suppressErrors);
// If you want to add special folder where fonts are stored. Default fonts folder in OS is always included.
options.AdditionalFontsFolders = new string[] { @"{FONT_FOLDER}" };

// Default page size is 595x842 and it is not mandatory to set it in PdfDevice
Aspose.Page.EPS.Device.PdfDevice device = new Aspose.Page.EPS.Device.PdfDevice(pdfStream);
// But if you need to specify size and image format use following line
//Aspose.Page.EPS.Device.PdfDevice device = new Aspose.Page.EPS.Device.PdfDevice(pdfStream, new System.Drawing.Size(595, 842));

try
{
    document.Merge(filesForMerge, device, options);
}
finally
{
    psStream.Close();
    pdfStream.Close();
}

//Review errors
if (suppressErrors)
{
    foreach (Exception ex in options.Exceptions)
    {
        Console.WriteLine(ex.Message);
    }
}
```
{{% alert color="primary" %}}
See PS merge in [Java](/page/java/merge/ps/) and [C++](/page/cpp/merge/ps/).
{{% /alert %}}

Let's consider [PdfSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pdfsaveoptions/). Using this class we can assign different conversion parameters while merging PS files to PDF.
<br>
- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.
- **SuppressError** controls behaviour of PS merger when non-critical errors are appeared. If value is true than it is possible to view a list of such errors after merging in **Exceptions** field. Default value is true.
- **Debug** allows outputting debug information to console. Default value is false.

{{% alert color="primary" %}}
Evaluate PS merging online on our <a nofollow href="https://products.aspose.app/page/merger/ps">PS Merger</a>.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 