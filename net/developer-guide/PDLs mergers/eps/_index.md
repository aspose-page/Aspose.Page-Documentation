---
title: Merge EPS files to PDF using .NET
type: docs
weight: 20
url: /net/merge/eps/
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS Merger and view the results via free online <a nofollow href="https://products.aspose.app/page/merger/eps">EPS Merger</a> {{% /alert %}} 

Aspose.Page for .NET EPS Merger allows to merge Encapsulated PostScript (EPS) files to PDF document with using of any language supported by .NET platform: C#, VB, J#.
<br>It is necessary to do several steps in order to perform EPS merge:
1. Initialize an input stream for the first input EPS file.
2. Initialize an output stream for output PDF document.
3. Create an array of EPS files that will be merged with the first one.
4. Create an instance of [PsDocument](https://apireference.aspose.com/page/net/aspose.page.eps/psdocument) from created earlier input stream.
5. Use [PdfSaveOptions](https://apireference.aspose.com/page/net/aspose.page.eps.device/pdfsaveoptions) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
6. Create an instance of [PdfDevice](https://apireference.aspose.com/page/net/aspose.page.eps.device/pdfdevice) from created earlier output stream.
7. Merge EPS files with created document and save it as PDF with PDF save options.
7. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during merging of EPS files to PDF document and saved in **Exceptions** list.

<br>Following code snippet shows how to merge EPS files to PDF document in C#:
<br>
```C#
/ For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-.NET
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithDocumentMerging();
// Initialize PDF output stream
System.IO.FileStream pdfStream = new System.IO.FileStream(dataDir + "outputPDF_out.pdf", System.IO.FileMode.Create, System.IO.FileAccess.Write);
// Initialize the first EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);

// Create an array of EPS file that will be merged with the first one
string[] filesForMerge = new string[] { dataDir + "input2.eps", dataDir + "input3.eps" };

// If you want to merge EPS files despite of minor errors set this flag
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
See EPS merge in [Java](/page/java/merge/eps/) and [C++](/page/cpp/merge/eps/).
{{% /alert %}}

Let's consider [PdfSaveOptions](https://apireference.aspose.com/page/net/aspose.page.eps.device/pdfsaveoptions). Using this class we can assign different conversion parameters while merging EPS to PDF.
<br>
- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.
- **SuppressError** controls behaviour of EPS merger when non-critical errors are appeared. If value is true than it is possible to view a list of such errors after merging in **Exceptions** field. Default value is true.
- **Debug** allows outputting debug information to console. Default value is false.

{{% alert color="primary" %}}
Evaluate EPS merging online on our <a nofollow href="https://products.aspose.app/page/merger/eps">EPS Merger</a>.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 