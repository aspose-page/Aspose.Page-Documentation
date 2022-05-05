---
title: Convert XPS to JPG using .NET
type: docs
weight: 20
url: /net/convert/xps-to-jpg/
description: XPS to JPG conversion functionality included in Aspose.Page API solution for .NET is described and illustrated with the code snippets here.
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page XPS to JPG conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/xps-to-jpg">XPS to JPG Converter</a>
or <a nofollow href="https://products.aspose.app/page/viewer/xps">XPS Viewer</a> {{% /alert %}}

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

    // Create rendering device for image
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
{{% alert color="primary" %}}
See XPS to JPG conversion in [Java](/page/java/convert/xps-to-jpg/) and [C++](/page/cpp/convert/xps-to-jpg/).
{{% /alert %}}

Let's consider [JpegSaveOptions](https://apireference.aspose.com/page/net/aspose.page.xps.presentation.image/jpegsaveoptions). Using this class we can assign different conversion parameters while converting XPS to JPG.
<br>
- **SmoothingMode** assigns a degree of smoothing for lines, curves and edges of filled areas, may be AntiAlias, HighQuality, HighSpeed and Default (none). Default value is HighQuality.
- **Resolution** controls resolution of resulting image. Default value is 96.
- **TextRenderingHint** assigns quality of text rendering, may be AntiAlias, AntiAliasGridFit, ClearTypeGridFit, SingleBitPerPixel, SingleBitPerPixelGridFit, SystemDefault. Default value in XPS to JPG conversion is AntiAliasGridFit.
- **InterpolationMode** defines algorithm that is used when scaling or/and rotating image, may be Bicubic, Bilinear, High, HighQualityBicubic, HighQualityBilinear, Low, NearestNeighbor and Default. Default value is HighQualityBicubic.
- **PageNumbers** represents an array of numbers of pages which will be saved to JPG.

{{% alert color="primary" %}} 
Evaluate XPS to JPG conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/xps-to-jpg">XPS to JPG Converter</a>. You can convert several XPS files to JPG at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 