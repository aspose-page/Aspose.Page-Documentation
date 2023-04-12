---
title: Working with Transparency | .NET
linktitle: Working with Transparency
type: docs
weight: 120
url: /net/ps/working-with-transparency/
description: How to add image to PS file is a question answered by Aspose.Page API solution.  See how to use the functionality in .NET
aliases: /net/ps/add-transparency-in-ps-document/
---

## **Add transparency in PS document**
PostScript doesn't support transparency in painting vector graphics objects. However, translucent (partially transparent) images can be rendered as set of fully transparent and fully opaque pixels.
Such images are called **masks**.
<br>
Aspose.Page for .NET library offers a method that adds transparent image to PS document. As for painting vector graphics: shapes or text, we offer **"pseudo-transparency"**.
**"Pseudo-transparency"** is a process of paling colors that have Alpha component less than 255. It is reached by specific blending of Red, Green and Blue components with Alpha one.
**"Pseudo-transparency"**, of course, doesn't allow to see the lower colored layer from under upper transparent layer, but make an illusion of transparency if the bottom layer is white.

### **Add transparent image in PS document**
As we wrote earlier transparent image can be added to PS document as a **mask** and Aspose.Page for .NET library offers for this purpose a method **AddTransparentImage()**.
This method recognizes whether the image is fully opaque or fully transparent or translucent. If it is fully opaque it is added as the opaque image in **AddImage()** method,
if it is fully transparent it is not added to document at all, if it is tranclucent image it is added as PostScript image **mask**.
<br>
<br>
In the example below we demonstrate a difference of adding transparent image in PS document with **AddImage()** and **AddTransparentImage()**. In order to see the white tranclucent image we set page background color
to non-white.
<br>
<br>
In order to add any image to new [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) with Aspose.Page for .NET library in this example we do following steps:
1. Create output stream for resulting PS file.
2. Create [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/) object with default options. Change background color if it is required.
3. Create 1-paged PsDocument with already created output stream and save options.
4. Create new graphics state.
5. Create **System.Drawing.Bitmap** from image file.
6. Create necessary transformation for the image.
7. Add image to PsDocument as fully opaque image (using **AddImage()** method) if we sure that image is opaque or add one as transparent image (using **AddTransparentImage()** method) if we not sure that image is opaque.
9. Exit from current graphics state to upper level one.
10. Close page.
11. Save the document.

```C#
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTransparentImage_outPS.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    //Set page's background color to see white image on it's own transparent background
    options.BackgroundColor = Color.FromArgb(211, 8, 48);

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);


    document.WriteGraphicsSave();
    document.Translate(20, 100);

    //Create bitmap from translucent image file
    using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
    {
        //Add this image to document as usual opaque RGB image
        document.DrawImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 100, 0), Color.Empty);
    }

    //Again create bitmap from the same image file
    using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
    {
        //Add this image to document as transparent image image
        document.DrawTransparentImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 350, 0), 255);
    }

    document.WriteGraphicsRestore();

    //Close current page
    document.ClosePage();

    //Save the document
    document.Save();
}
```
{{% alert color="primary" %}}
See working with images in PS document in [Java](/page/java/ps/working-with-transparency/) and [C++](/page/cpp/ps/working-with-transparency/).
{{% /alert %}}

The result of running this code is appeared as
</br></br></br>
<p align="center">
	<img src="AddTransparentImage_outPS.png">
</p>
</br></br></br>

### **Adding transparent vector graphics object**
Earlier we wrote that Aspose.Page for .NET library uses paling algorythm for transparent shapes and text, that we called **"pseudo-transparency"**.
In example below we demonstrate difference between two shapes painted with the same color, but in the first shape without Alpha component and in the second case with Alpha component.

```C#
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    float offsetX = 50;
    float offsetY = 100;
    float width = 200;
    float height = 100;

///////////////////////////////// Create rectangle with opaque gradient fill /////////////////////////////////////////////////////////
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(50, 100, 200, 100));

    LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
        Color.FromArgb(40, 128, 70), 0f);
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(200, 0, 0, 100, 50, 100);
    opaqueBrush.Transform = brushTransform;
    Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
    gradientBrush.WrapMode = WrapMode.Clamp;

    document.SetPaint(gradientBrush);
    document.Fill(path);
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

    offsetX = 350;

///////////////////////////////// Create rectangle with translucent gradient fill ///////////////////////////////////////////////////
    //Create graphics path from the first rectangle
    path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    //Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
    LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
    //Create a transform for brush.
    brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    //Set transform
    translucentBrush.Transform = brushTransform;
    //Create GradientBrush object containing the linear gradient brush
    gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
    gradientBrush.WrapMode = WrapMode.Clamp;
    //Set paint
    document.SetPaint(gradientBrush);
    //Fill the rectangle
    document.Fill(path);
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

    //Close current page
    document.ClosePage();

    //Save the document
    document.Save();
}
```
{{% alert color="primary" %}}
See working with images in PS document in [Java](/page/java/ps/working-with-transparency/) and [C++](/page/cpp/ps/working-with-transparency/).
{{% /alert %}}

The result of running this code is appeared as
</br></br></br>
<p align="center">
	<img src="ShowPseudoTransparency_outPS.png">
</p>
</br></br></br>

{{% alert color="primary" %}}
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 
