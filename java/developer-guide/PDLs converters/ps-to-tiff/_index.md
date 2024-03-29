---
title: Convert PostScript to TIFF using Java
type: docs
weight: 20
url: /java/convert/ps-to-tiff/
description: PS to TIFF conversion functionality included in Aspose.Page API solution for Java is explained and illustrated with the code snippets here.
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page PS to TIFF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/ps-to-tiff">PostScipt to TIFF Converter</a>
or <a nofollow href="https://products.aspose.app/page/viewer/ps">PostScript Viewer</a> {{% /alert %}}

Aspose.Page for Java PS to TIFF converter allows to convert PostScript (PS) file to TIFF image on any OS for which Java Virtual Machine exists.
<br>It is necessary to do several steps in order to perform PS to TIFF conversion:
1. Initialize an input stream for input PS file.
2. Create an instance of [PsDocument](https://reference.aspose.com/page/java/com.aspose.eps/psdocument) from created earlier input stream.
4. Use [ImageSaveOptions](https://reference.aspose.com/page/java/com.aspose.eps.device/imagesaveoptions) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
5. Create an instance of [ImageDevice](https://reference.aspose.com/page/java/com.aspose.eps.device/imagedevice) specifying image type and size if it is necessary.
6. Save PostScript document as image with image save options to an array of arrays of bytes. One array of bytes for one page of input document.
7. Save resulting 2-dimensional arrays of bytes to TIFF files creating for every bytes array a new file output stream.
8. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during conversion of PS to TIFF.

<br>Following code snippet shows how to convert PS to TIFF files in Java:
<br>
```Java
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-Java
// The path to the documents directory.
String dataDir = Utils.getDataDir();
//Initialize image format
ImageFormat imageFormat = ImageFormat.TIFF;
// Initialize Encapsulated PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");

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
    String imagePath = dataDir + "PSToImage" + i + "." + imageFormat.toString().toLowerCase();
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
See PS to TIFF conversion in [.NET](/page/net/convert/ps-to-tiff/) and [C++](/page/cpp/convert/ps-to-tiff/).
{{% /alert %}}

Let's consider [ImageSaveOptions](https://reference.aspose.com/page/java/com.aspose.eps.device/imagesaveoptions). Using this class we can assign different conversion parameters while converting PS to TIFF.
<br>
- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.
- **SuppressError** controls behaviour of PS to TIFF converter when non-critical errors are appeared. If value is true than it is possible to view a list of such errors after conversion in **Exceptions** field. Default value is true.
- **Debug** allows outputting debug information to console. Default value is false.

{{% alert color="primary" %}}
Evaluate PS to TIFF conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/ps-to-tiff">PS to TIFF Converter</a>. You can convert several PS files to TIFF at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-Java). {{% /alert %}} 