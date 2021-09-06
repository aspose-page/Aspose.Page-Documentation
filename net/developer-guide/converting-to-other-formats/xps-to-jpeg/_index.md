---
title: Convert XPS to JPG
type: docs
weight: 20
url: /net/convert/xps-to-jpg/
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page conversion and view the results online at this links:

[products.aspose.app/page/conversion/xps-to-jpg](https://products.aspose.app/page/conversion/xps-to-jpg),
[products.aspose.app/page/viewer/xps](https://products.aspose.app/page/viewer/xps). {{% /alert %}} 

Aspose.Page .NET XPS to JPG converter allows to convert XPS document to JPG image with using of any language supported by .Net platform: C#, VB, J#.
<br>It is necessary to do several steps in order to perform XPS to JPG conversion:
1. Initialize an input stream for input XPS document.
2. Create an instance of [XpsDocument](https://apireference.aspose.com/page/net/aspose.page.xps/xpsdocument) from created earlier input stream.
4. Specify **SmoothingMode**, **Resolution** and other options of [JpegSaveOptions](https://apireference.aspose.com/page/net/aspose.page.xps.presentation.image/jpegsaveoptions).
5. Create an instance of [ImageDevice](https://apireference.aspose.com/page/net/aspose.page.xps.presentation.image/imagedevice).
6. Save XPS document as image with JPEG save options to an array of arrays of bytes. One array of bytes for one page of input document.
7. Save resulting 2-dimensional arrays of bytes to JPG files creating for every bytes array a new file output stream.

<br>Following code snippet shows how to convert XPS to JPG files in C#:
<br>
```C#
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-.NET
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithDocumentConversion();
// Input file
string inputFileName = dataDir + "input.xps";
//Outut file 
string outputFileName = dataDir + "XPStoImage_out.jpg";
// Initialize XPS input stream
using (Stream xpsStream = File.Open(inputFileName, FileMode.Open, FileAccess.Read))
{
    // Load XPS document form the stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // or load XPS document directly from file. No xpsStream is needed then.
    // XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());

    // Initialize options object with necessary parameters.
    JpegSaveOptions options = new JpegSaveOptions()
    {
        SmoothingMode = System.Drawing.Drawing2D.SmoothingMode.HighQuality,
        Resolution = 300,
        PageNumbers = new int[] { 1, 2, 6 }
    };

    // Create rendering device for PDF format
    ImageDevice device = new ImageDevice();

    document.Save(device, options);

    // Iterate through document partitions (fixed documents, in XPS terms)
    for (int i = 0; i < device.Result.Length; i++)
        // Iterate through partition pages
        for (int j = 0; j < device.Result[i].Length; j++)
        {
            // Initialize image output stream
            using (Stream imageStream = System.IO.File.Open(Path.GetDirectoryName(outputFileName) +
                Path.GetFileNameWithoutExtension(outputFileName) + "_" + (i + 1) + "_" + (j + 1) +
                Path.GetExtension(outputFileName), System.IO.FileMode.Create, System.IO.FileAccess.Write))
                // Write image
                imageStream.Write(device.Result[i][j], 0, device.Result[i][j].Length);
        }
}
```

