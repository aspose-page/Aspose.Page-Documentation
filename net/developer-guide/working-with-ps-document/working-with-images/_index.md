---
title: Working with Images | .NET
linktitle: Working with Images
type: docs
weight: 80
url: /net/ps/working-with-images/
description: How to add image to PS file is a question answered by Aspose.Page API solution.  See how to use the functionality in .NET
keywords: working with images in PS .NET, working with images in PostScript .NET, working with images in EPS .NET
aliases: /net/ps/add-image-in-ps-document/
---

## **Add Image in PS Document**

Aspose.Page for .NET library offers two methods for adding images to PS document:
- for opaque images;
- for transparent images;

It was made because PostScript doesn't support transparency, but translucent images, however, can be rendered as a set of fully transparent and fully opaque pixels. Such images are called **masks**. If we want to see the translucent image in the PS document as **mask**, that will better reflect the transparency of the image, we should do some checking and preprocessing of such an image.
The check and the preprocessing require time. Therefore, if someone's sure that the image is fully opaque, it is better to use the first method, because it saves execution time.

The second method recognizes whether the image is fully opaque or fully transparent or translucent. If it is fully opaque it is added as the opaque image in the first method,
if it is fully transparent it is not added to the document at all, if it is the translucent image it is added as a PostScript image **mask**.
<br>
<br>
In the example below we demonstrate how to add a fully opaque image. Adding a transparent image will be demonstrated in the "Working with Transparency" article.
<br>

In order to add an image to a new [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) with Aspose.Page for .NET library in this example we take the following steps:
1. Create an output stream for the resulting PS file.
2. Create [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/) object with default options.
3. Create a 1-paged PsDocument with an already created output stream and save options.
4. Create a new graphics state.
5. Create **System.Drawing.Bitmap** from image file.
6. Create the necessary transformation for the image.
7. Add the image to the PsDocument object.
9. Exit from the current graphics state to upper level one.
10. Close the page.
11. Save the document.

```C#
//Create an output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddImage_outPS.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    
    document.WriteGraphicsSave();
    document.Translate(100, 100);

    //Create a Bitmap object from image file
    using (Bitmap image = new Bitmap(dataDir + "TestImage Format24bppRgb.jpg"))
    {
        //Create image transform
        System.Drawing.Drawing2D.Matrix transform = new System.Drawing.Drawing2D.Matrix();
        transform.Translate(35, 300);
        transform.Scale(3, 3);
        transform.Rotate(-45);

        //Add the image to document
        document.DrawImage(image, transform, Color.Empty);
    }

    document.WriteGraphicsRestore();

    //Close current page
    document.ClosePage();

    //Save the document
    document.Save();
}
}
```
{{% alert color="primary" %}}
See working with images in PS documents in [Java](/page/java/ps/working-with-images/) and [C++](/page/cpp/ps/working-with-images/).
{{% /alert %}}

The result of running this code is appeared as
</br></br></br>
<p align="center">
	<img src="AddImage.png">
</p>
</br></br></br>

{{% alert color="primary" %}}
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 
