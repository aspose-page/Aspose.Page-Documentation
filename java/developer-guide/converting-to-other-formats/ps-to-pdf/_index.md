---
title: Convert PostScript to PDF
type: docs
weight: 20
url: /java/convert/ps-to-pdf/
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page conversion and view the results online at this link:

[products.aspose.app/page/conversion/ps-to-pdf](https://products.aspose.app/page/conversion/ps-to-pdf) {{% /alert %}} 

Aspose.Page for Java PS to PDF converter allows to convert PostScript (PS) file to PDF document on any OS for which Java Virtual Machine exists.
<br>It is necessary to do several steps in order to perform PS to PDF conversion:
1. Initialize an input stream for input PS file.
2. Initialize an output stream for output PDF document.
3. Create an instance of [PsDocument](https://apireference.aspose.com/page/java/com.aspose.eps/psdocument) from created earlier input stream.
4. Use [PdfSaveOptions](https://apireference.aspose.com/page/java/com.aspose.eps.device/pdfsaveoptions) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
5. Create an instance of [PdfDevice](https://apireference.aspose.com/page/java/com.aspose.eps.device/pdfdevice) from created earlier output stream.
6. Save PostScript document as PDF with PDF save options.
7. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during conversion of PS to PDF.

<br>Following code snippet shows how to convert PS to PDF document in C#:
<br>
```C#
/ For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-Java
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithDocumentConversion();
// Initialize PDF output stream
System.IO.FileStream pdfStream = new System.IO.FileStream(dataDir + "outputPDF_out.pdf", System.IO.FileMode.Create, System.IO.FileAccess.Write);
// Initialize PostScript input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "input.ps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
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


