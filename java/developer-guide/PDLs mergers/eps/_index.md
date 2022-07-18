---
title: Merge EPS files to PDF using Java
type: docs
weight: 20
url: /java/merge/eps/
description: Merger EPS functionality of  Aspose.Page API solution for Java allows you to combine several EPS files into a single PDF document.
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS Merger and view the results via free online <a nofollow href="https://products.aspose.app/page/merger/eps">EPS Merger</a> {{% /alert %}} 

Aspose.Page for Java EPS Merger allows to merge Encapsulated PostScript (EPS) files to PDF document on any OS for which Java Virtual Machine exists.
<br>It is necessary to do several steps in order to perform EPS to PDF merge:
1. Initialize an input stream for the first input EPS file.
2. Initialize an output stream for output PDF document.
3. Create an array of EPS files that will be merged with the first one.
4. Create an instance of [PsDocument](https://reference.aspose.com/page/java/com.aspose.eps/psdocument) from created earlier input stream.
5. Use [PdfSaveOptions](https://reference.aspose.com/page/java/com.aspose.eps.device/pdfsaveoptions) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
6. Create an instance of [PdfDevice](https://reference.aspose.com/page/java/com.aspose.eps.device/pdfdevice) from created earlier output stream.
7. Merge EPS files with created document and save it as PDF with PDF save options.
8. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during merging of EPS files to PDF document and saved in **Exceptions** list.

<br>Following code snippet shows how to merge EPS files to PDF document in Java:
<br>
```Java
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-Java

        // The path to the documents directory.
        String dataDir = Utils.getDataDir();
        // Initialize PDF output stream
        FileOutputStream pdfStream = new FileOutputStream(dataDir + "EPStoPDF.pdf");

        // Initialize the first EPS file input stream
        FileInputStream psStream = new FileInputStream(dataDir + "input.eps");

        PsDocument document = new PsDocument(psStream);
        
        // Create an array of EPS file that will be merged with the first one
				String[] filesForMerge = new String[] { dataDir + "input2.eps", dataDir + "input3.eps" };

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
            document.merge(filesForMerge, device, options);
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
See EPS merge in [.NET](/page/net/merge/eps/) and [C++](/page/cpp/merge/eps/).
{{% /alert %}}

Let's consider [PdfSaveOptions](https://reference.aspose.com/page/java/com.aspose.eps.device/pdfsaveoptions). Using this class we can assign different conversion parameters while merging EPS files to PDF.
<br>
- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.
- **SuppressError** controls behaviour of EPS to PDF merger when non-critical errors are appeared. If value is true than it is possible to view a list of such errors after merging in **Exceptions** field. Default value is true.
- **Debug** allows outputting debug information to console. Default value is false.

{{% alert color="primary" %}}
Evaluate EPS merging online on our <a nofollow href="https://products.aspose.app/page/merger/eps">EPS Merger</a>.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-Java). {{% /alert %}} 