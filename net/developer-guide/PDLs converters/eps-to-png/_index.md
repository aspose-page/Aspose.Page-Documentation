---
title: Convert EPS to PNG using .NET
type: docs
weight: 20
url: /net/convert/eps-to-png/
description: EPS to PNG conversion functionality offered by Aspose.Page API solution for .NET is explained and illustrated with the code snippets here.
---

## Overview

This article explains how to **convert EPS to PNG using C#**. It covers the following topics.

- [C# EPS to PNG](#c-eps-to-png)
- [C# Convert EPS to PNG](#c-eps-to-png)
- [C# EPS to Image](#c-eps-to-image)
- [C# PNG from EPS](#c-eps-to-png)
- [C# How to Convert EPS to PNG Programmatically](#c-eps-to-png)
- [C# Save EPS as PNG](#c-eps-to-png)

<a name="c-eps-to-image"><strong>C# EPS to Image</strong></a>

The EPS to Image conversion using C# in other formats like JPG, BMP, TIFF, EMF etc. are covered in these articles.

- [C# EPS to JPG](https://docs.aspose.com/page/net/convert/eps-to-jpg/)
- [C# EPS to BMP](https://docs.aspose.com/page/net/convert/eps-to-bmp/)
- [C# EPS to TIFF](https://docs.aspose.com/page/net/convert/eps-to-tiff/)
- [C# EPS to EMF](https://docs.aspose.com/page/net/convert/eps-to-emf/)
- [C# EPS to WMF](https://docs.aspose.com/page/net/convert/eps-to-wmf/)

## C# EPS to PNG Conversion

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to PNG conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-png">EPS to PNG Converter</a>
or <a nofollow href="https://products.aspose.app/page/viewer/eps">EPS Viewer</a> {{% /alert %}}

Aspose.Page for .NET EPS to PNG converter allows to convert Encapsulated PostScript (EPS) file to PNG image with using of any language supported by .Net platform: C#, VB, J#.

<a name="c-eps-to-png"><strong>Steps: EPS to PNG Converter API Code in C#</strong></a>

It is necessary to do several steps in order to perform EPS to PNG conversion:

1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) from created earlier input stream.
4. Use [ImageSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/imagesaveoptions/) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
5. Create an instance of [ImageDevice](https://reference.aspose.com/page/net/aspose.page.eps.device/imagedevice/) specifying image type and size if it is necessary.
6. Save PostScript document as image with image save options to an array of arrays of bytes. One array of bytes for one page of input document.
7. Save resulting 2-dimensional arrays of bytes to PNG files creating for every bytes array a new file output stream.
8. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during conversion of EPS to PNG.

Following C# code snippet shows how to **convert EPS to PNG files in C#**:

```C#
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-.NET
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithDocumentConversion();

// Specifies image format
System.Drawing.Imaging.ImageFormat imageFormat = System.Drawing.Imaging.ImageFormat.Png;

// Initialize PostScript input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "inputForImage.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);

PsDocument document = new PsDocument(psStream);

// If you want to convert Postscript file despite of minor errors set this flag
bool suppressErrors = true;

//Initialize options object with necessary parameters.
ImageSaveOptions options = new ImageSaveOptions(suppressErrors);
            
// If you want to add special folder where fonts are stored. Default fonts folder in OS is always included.
options.AdditionalFontsFolders = new string[] { @"{FONT_FOLDER}" };

// Default image size is 595x842 and it is not mandatory to set it in ImageDevice
ImageDevice device = new ImageDevice(new System.Drawing.Size(imageFormat);

// But if you need to specify size use constructor with two parameters
//ImageDevice device = new ImageDevice(new System.Drawing.Size(595, 842), imageFormat);

try
{
    document.Save(device, options);
}
finally
{
    psStream.Close();
}

byte[][] imagesBytes = device.ImagesBytes;

int i = 0;

foreach (byte[] imageBytes in imagesBytes)
{
    string imagePath = Path.GetFullPath("out_image" + i.ToString() +"." + imageFormat.ToString().ToLower());
    using (FileStream fs = new FileStream(imagePath, FileMode.Create, FileAccess.Write))
    {
        fs.Write(imageBytes, 0, imageBytes.Length);
    }
    i++;
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
{{% alert color="primary" %}}
See EPS to PNG conversion in [Java](/page/java/convert/eps-to-png/) and [C++](/page/cpp/convert/eps-to-png/).
{{% /alert %}}

Let's consider [ImageSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/imagesaveoptions/). Using this class we can assign different conversion parameters while converting EPS to PNG.
<br>
- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.
- **SuppressError** controls behaviour of EPS to PNG converter when non-critical errors are appeared. If value is true than it is possible to view a list of such errors after conversion in **Exceptions** field. Default value is true.
- **Debug** allows outputting debug information to console. Default value is false.

{{% alert color="primary" %}}
Evaluate EPS to PNG conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/eps-to-png">EPS to PNG Converter</a>. You can convert several EPS files to PNG at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 
