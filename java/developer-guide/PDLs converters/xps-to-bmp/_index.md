---
title: Convert XPS to BMP using Java
type: docs
weight: 20
url: /java/convert/xps-to-bmp/
description: XPS to BMP conversion functionality included in Aspose.Page API solution for Java is described and illustrated with the code snippets here.
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page XPS to BMP conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/xps-to-bmp">XPS to BMP Converter</a>
or <a nofollow href="https://products.aspose.app/page/viewer/xps">XPS Viewer</a> {{% /alert %}}

Aspose.Page Java XPS to BMP converter allows to convert XPS document to BMP image on any OS for which Java Virtual Machine exists.
<br>It is necessary to do several steps in order to perform XPS to BMP conversion:
1. Initialize an input stream for input XPS document.
2. Create an instance of [XpsDocument](https://reference.aspose.com/page/java/com.aspose.xps/xpsdocument) from created earlier input stream.
4. Specify **SmoothingMode**, **Resolution** and other options of [BmpSaveOptions](https://reference.aspose.com/page/java/com.aspose.xps.rendering/bmpsaveoptions).
5. Create an instance of [ImageDevice](https://reference.aspose.com/page/java/com.aspose.xps.rendering/imagedevice).
6. Save XPS document as image with BMP save options to an array of arrays of bytes. One array of bytes for one page of input document.
7. Save resulting 2-dimensional arrays of bytes to BMP files creating for every bytes array a new file output stream.

<br>Following code snippet shows how to convert XPS to BMP files in Java:
<br>
```Java
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-Java
// The path to the documents directory.
String dataDir = Utils.getDataDir();
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
// Initialize options object with necessary parameters.
com.aspose.xps.rendering.BmpSaveOptions options = new com.aspose.xps.rendering.BmpSaveOptions();
options.setSmoothingMode(com.aspose.xps.rendering.SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[]{1, 2, 6});

// Create rendering device for image
com.aspose.xps.rendering.ImageDevice device = new com.aspose.xps.rendering.ImageDevice();

document.save(device, options);

// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
    }
}
```
{{% alert color="primary" %}}
See XPS to BMP conversion in [.NET](/page/net/convert/xps-to-bmp/) and [C++](/page/cpp/convert/xps-to-bmp/).
{{% /alert %}}

Let's consider [BmpSaveOptions](https://reference.aspose.com/page/java/com.aspose.xps.rendering/bmpsaveoptions). Using this class we can assign different conversion parameters while converting XPS to BMP.
<br>
- **SmoothingMode** assigns a degree of smoothing for lines, curves and edges of filled areas, may be AntiAlias, HighQuality, HighSpeed and Default (none). Default value is HighQuality.
- **Resolution** controls resolution of resulting image. Default value is 96.
- **TextRenderingHint** assigns quality of text rendering, may be AntiAlias, AntiAliasGridFit, ClearTypeGridFit, SingleBitPerPixel, SingleBitPerPixelGridFit, SystemDefault. Default value in XPS to BMP conversion is AntiAliasGridFit.
- **InterpolationMode** defines algorithm that is used when scaling or/and rotating image, may be Bicubic, Bilinear, High, HighQualityBicubic, HighQualityBilinear, Low, NearestNeighbor and Default. Default value is HighQualityBicubic.
- **PageNumbers** represents an array of numbers of pages which will be saved to BMP.

{{% alert color="primary" %}} 
Evaluate XPS to BMP conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/xps-to-bmp">XPS to BMP Converter</a>. You can convert several XPS files to BMP at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-Java). {{% /alert %}} 