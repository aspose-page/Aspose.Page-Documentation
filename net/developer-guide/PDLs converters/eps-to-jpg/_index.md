---
title: Convert EPS to JPG using .NET
type: docs
weight: 20
url: /net/convert/eps-to-jpg/
description: EPS to JPG conversion functionality offered by Aspose.Page API solution for .NET is explained and illustrated with the code snippets here.
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to JPG conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-jpg">EPS to JPG Converter</a>
or <a nofollow href="https://products.aspose.app/page/viewer/eps">EPS Viewer</a> {{% /alert %}}

Aspose.Page for .NET EPS to JPG converter allows to convert Encapsulated PostScript (EPS) file to JPEG image with using of any language supported by .Net platform: C#, VB, J#.
<br>It is necessary to do several steps in order to perform EPS to JPG conversion:
1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://apireference.aspose.com/page/net/aspose.page.eps/psdocument) from created earlier input stream.
4. Use [ImageSaveOptions](https://apireference.aspose.com/page/net/aspose.page.eps.device/imagesaveoptions) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
5. Create an instance of [ImageDevice](https://apireference.aspose.com/page/net/aspose.page.eps.device/imagedevice) specifying image type and size if it is necessary.
6. Save PostScript document as image with image save options to an array of arrays of bytes. One array of bytes for one page of input document.
7. Save resulting 2-dimensional arrays of bytes to JPEG files creating for every bytes array a new file output stream.
8. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during conversion of EPS to JPG.

<br>Following code snippet shows how to convert EPS to JPG files in C#:
<br>
```C#
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-.NET
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithDocumentConversion();
// Specifies image format
System.Drawing.Imaging.ImageFormat imageFormat = System.Drawing.Imaging.ImageFormat.Jpeg;
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
See EPS to JPG conversion in [Java](/page/java/convert/eps-to-jpg/) and [C++](/page/cpp/convert/eps-to-jpg/).
{{% /alert %}}

Let's consider [ImageSaveOptions](https://apireference.aspose.com/page/net/aspose.page.eps.device/imagesaveoptions). Using this class we can assign different conversion parameters while converting EPS to JPG.
<br>
- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.
- **SuppressError** controls behaviour of EPS to JPG converter when non-critical errors are appeared. If value is true than it is possible to view a list of such errors after conversion in **Exceptions** field. Default value is true.
- **Debug** allows outputting debug information to console. Default value is false.

{{% alert color="primary" %}}
Evaluate EPS to JPG conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/eps-to-jpg">EPS to JPG Converter</a>. You can convert several EPS files to JPG at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 