---
title: Convert XPS to PNG
type: docs
weight: 20
url: /cpp/convert/xps-to-png/
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page XPS to PNG conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/xps-to-png">XPS to PNG Converter</a>
or <a nofollow href="https://products.aspose.app/page/viewer/xps">XPS Viewer</a> {{% /alert %}}

Aspose.Page C++ XPS to PNG converter allows to convert XPS document to PNG image on Windows and Linux.
<br>It is necessary to do several steps in order to perform XPS to PNG conversion:
1. Initialize an input stream for input XPS document.
2. Create an instance of [XpsDocument](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_document) from created earlier input stream.
4. Specify **SmoothingMode**, **Resolution** and other options of [PngSaveOptions](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.presentation.image.png_save_options).
5. Create an instance of [ImageDevice](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.presentation.image.image_device).
6. Save XPS document as image with PNG save options to an array of arrays of bytes. One array of bytes for one page of input document.
7. Save resulting 2-dimensional arrays of bytes to PNG files creating for every bytes array a new file output stream.

<br>Following code snippet shows how to convert XPS to PNG files in C++:
<br>
```C++
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-C
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithDocumentConversion();
// Input file
string inputFileName = dataDir + "input.xps";
//Outut file 
string outputFileName = dataDir + "XPStoImage_out.png";
// Initialize XPS input stream
using (Stream xpsStream = File.Open(inputFileName, FileMode.Open, FileAccess.Read))
{
    // Load XPS document form the stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // or load XPS document directly from file. No xpsStream is needed then.
    // XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());

    // Initialize options object with necessary parameters.
    PngSaveOptions options = new PngSaveOptions()
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
See XPS to PNG conversion in [.Net](/page/net/convert/xps-to-png/) and [Java](/page/java/convert/xps-to-png/).
{{% /alert %}}

Let's consider [PngSaveOptions](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.presentation.image.png_save_options). Using this class we can assign different conversion parameters while converting XPS to PNG.
<br>
- **SmoothingMode** assigns a degree of smoothing for lines, curves and edges of filled areas, may be AntiAlias, HighQuality, HighSpeed and Default (none). Default value is HighQuality.
- **Resolution** controls resolution of resulting image. Default value is 96.
- **TextRenderingHint** assigns quality of text rendering, may be AntiAlias, AntiAliasGridFit, ClearTypeGridFit, SingleBitPerPixel, SingleBitPerPixelGridFit, SystemDefault. Default value in XPS to PNG conversion is AntiAliasGridFit.
- **InterpolationMode** defines algorithm that is used when scaling or/and rotating image, may be Bicubic, Bilinear, High, HighQualityBicubic, HighQualityBilinear, Low, NearestNeighbor and Default. Default value is HighQualityBicubic.
- **PageNumbers** represents an array of numbers of pages which will be saved to PNG.

{{% alert color="primary" %}} 
Evaluate XPS to PNG conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/xps-to-png">XPS to PNG Converter</a>. You can convert several XPS files to PNG at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-C). {{% /alert %}} 
