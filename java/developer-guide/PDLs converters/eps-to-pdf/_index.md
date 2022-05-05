---
title: Convert EPS to PDF using Java
type: docs
weight: 20
url: /java/convert/eps-to-pdf/
description: EPS to PDF conversion functionality offered by Aspose.Page API solution for Java is explained and illustrated with the code snippets here.
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a> {{% /alert %}} 

Aspose.Page for Java EPS to PDF converter allows to convert Encapsulated PostScript (EPS) file to PDF document on any OS for which Java Virtual Machine exists.
<br>It is necessary to do several steps in order to perform EPS to PDF conversion:
1. Initialize an input stream for input EPS file.
2. Initialize an output stream for output PDF document.
3. Create an instance of [PsDocument](https://apireference.aspose.com/page/java/com.aspose.eps/psdocument) from created earlier input stream.
4. Use [PdfSaveOptions](https://apireference.aspose.com/page/java/com.aspose.eps.device/pdfsaveoptions) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
5. Create an instance of [PdfDevice](https://apireference.aspose.com/page/java/com.aspose.eps.device/pdfdevice) from created earlier output stream.
6. Save PostScript document as PDF with PDF save options.
7. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during conversion of EPS to PDF and saved in **Exceptions** list.

<br>Following code snippet shows how to convert EPS to PDF document in Java:
<br>
```Java
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-Java

// The path to the documents directory.
String dataDir = Utils.getDataDir();
// Initialize PDF output stream
FileOutputStream pdfStream = new FileOutputStream(dataDir + "PStoPDF.pdf");

// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");

PsDocument document = new PsDocument(psStream);

// If you want to convert Postscript file despite of minor errors set this flag
boolean suppressErrors = true;

//Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions(suppressErrors);
// If you want to add special folder where fonts are stored. Default fonts folder in OS is always included.
//options.setAdditionalFontsFolders(new String [] {"FONTS_FOLDER"});

// Default page size is 595x842 and it is not mandatory to set it in PdfDevice
com.aspose.eps.device.PdfDevice device = new com.aspose.eps.device.PdfDevice(pdfStream);
// But if you need to specify size and image format use following line
//com.aspose.eps.device.PdfDevice device = new com.aspose.eps.device.PdfDevice(pdfStream, new Dimension(595, 842));

try {
    document.save(device, options);
} finally {
    psStream.close();
    pdfStream.close();
}

//Review errors
if (suppressErrors) {
    for (Exception ex : options.getExceptions()) {
        System.out.println(ex.getMessage());
    }
}
```
{{% alert color="primary" %}}
See EPS to PDF conversion in [.NET](/page/net/convert/eps-to-pdf/) and [C++](/page/cpp/convert/eps-to-pdf/).
{{% /alert %}}

Let's consider [PdfSaveOptions](https://apireference.aspose.com/page/java/com.aspose.eps.device/pdfsaveoptions). Using this class we can assign different conversion parameters while converting EPS to PDF.
<br>
- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.
- **SuppressError** controls behaviour of EPS to PDF converter when non-critical errors are appeared. If value is true than it is possible to view a list of such errors after conversion in **Exceptions** field. Default value is true.
- **Debug** allows outputting debug information to console. Default value is false.

{{% alert color="primary" %}}
Evaluate EPS to PDF conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a>. You can convert several EPS files to PDF at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-Java). {{% /alert %}} 