---
title: Convert EPS to BMP using Java
type: docs
weight: 20
url: /java/convert/eps-to-bmp/
description: EPS to BMP conversion functionality offered by Aspose.Page API solution for Java is explained and illustrated with the code snippets here.
---

## Overview

This article explains how to **convert EPS to BMP using Java**. It covers the following topics.

- [Java EPS to BMP](#java-eps-to-bmp)
- [Java Convert EPS to BMP](#java-eps-to-bmp)
- [Java EPS to Image](#java-eps-to-image)
- [Java BMP from EPS](#java-eps-to-bmp)
- [Java How to Convert EPS to BMP Programmatically](#java-eps-to-bmp)
- [Java Save EPS as BMP](#java-eps-to-bmp)

<a name="java-eps-to-image"><h3>Java EPS to Image</h3></a>

The EPS to Image conversion using Java in other formats like JPG, PNG, TIFF, WMF etc. are covered in these articles.

- [Java EPS to JPG](https://docs.aspose.com/page/java/convert/eps-to-jpg/)
- [Java EPS to PNG](https://docs.aspose.com/page/java/convert/eps-to-png/)
- [Java EPS to TIFF](https://docs.aspose.com/page/java/convert/eps-to-tiff/)
- [Java EPS to EMF](https://docs.aspose.com/page/java/convert/eps-to-emf/)
- [Java EPS to WMF](https://docs.aspose.com/page/java/convert/eps-to-wmf/)

## Java EPS to JPG Convesion

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to BMP conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-bmp">EPS to BMP Converter</a>
or <a nofollow href="https://products.aspose.app/page/viewer/eps">EPS Viewer</a> {{% /alert %}}

Aspose.Page for Java EPS to BMP converter allows to convert Encapsulated PostScript (EPS) file to BMP image on any OS for which Java Virtual Machine exists.

<a name="java-eps-to-bmp"><strong>Steps: EPS to BMP Converter API Code in Java</strong></a>

It is necessary to do several steps in order to perform EPS to BMP conversion:

1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://reference.aspose.com/page/java/com.aspose.eps/psdocument) from created earlier input stream.
4. Use [ImageSaveOptions](https://reference.aspose.com/page/java/com.aspose.eps.device/imagesaveoptions) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
5. Create an instance of [ImageDevice](https://reference.aspose.com/page/java/com.aspose.eps.device/imagedevice) specifying image type and size if it is necessary.
6. Save PostScript document as image with image save options to an array of arrays of bytes. One array of bytes for one page of input document.
7. Save resulting 2-dimensional arrays of bytes to BMP files creating for every bytes array a new file output stream.
8. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during conversion of EPS to BMP.

Following Java code snippet shows how to **convert EPS to BMP files in Java**:

```Java
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-Java
// The path to the documents directory.
String dataDir = Utils.getDataDir();
//Initialize image format
ImageFormat imageFormat = ImageFormat.BMP;
// Initialize Encapsulated PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.eps");

PsDocument document = new PsDocument(psStream);

// If you want to convert Postscript file despite of minor errors set this flag
boolean suppressErrors = true;

//Initialize options object with necessary parameters.
ImageSaveOptions options = new ImageSaveOptions(suppressErrors);
// If you want to add special folder where fonts are stored. Default fonts folder in OS is always included.
//options.setAdditionalFontsFolders(new String [] {"FONTS_FOLDER"});

// Default image size is 595x842 and it is not mandatory to set it in ImageDevice
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice(imageFormat);
// But if you need to specify size use constructor with two parameters
//ImageDevice device = new ImageDevice(new Dimension(595, 842), imageFormat);

try {
    document.save(device, options);
} finally {
    psStream.close();
}

byte[][] imagesBytes = device.getImagesBytes();

int i = 0;

for (byte [] imageBytes : imagesBytes) {
    String imagePath = dataDir + "EPSToImage" + i + "." + imageFormat.toString().toLowerCase();
    FileOutputStream fs = new FileOutputStream(imagePath);

    try {
        fs.write(imageBytes, 0, imageBytes.length);
    } catch (IOException ex) {
        System.out.println(ex.getMessage());
    } finally {
        fs.close();
    }
    i++;
}

//Review errors
if (suppressErrors) {
    for (Exception ex : options.getExceptions()) {
        System.out.println(ex.getMessage());
    }
}
```
{{% alert color="primary" %}}
See EPS to BMP conversion in [.NET](/page/net/convert/eps-to-bmp/) and [C++](/page/cpp/convert/eps-to-bmp/).
{{% /alert %}}

Let's consider [ImageSaveOptions](https://reference.aspose.com/page/java/com.aspose.eps.device/imagesaveoptions). Using this class we can assign different conversion parameters while converting EPS to BMP.
<br>
- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.
- **SuppressError** controls behaviour of EPS to BMP converter when non-critical errors are appeared. If value is true than it is possible to view a list of such errors after conversion in **Exceptions** field. Default value is true.
- **Debug** allows outputting debug information to console. Default value is false.

{{% alert color="primary" %}}
Evaluate EPS to BMP conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/eps-to-bmp">EPS to BMP Converter</a>. You can convert several EPS files to BMP at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-Java). {{% /alert %}} 
