---
title: Working with Shapes | .NET
linktitle: Working with Shapes
type: docs
weight: 40
url: /net/ps/working-with-shapes/
description: How to add shapes to PS file is a question answered by Aspose.Page API solution.  See how to use the functionality in .NET
aliases: /net/ps/add-shapes-in-ps-document/
---

## **Add Shapes in PS Document**

### **Add Rectangle to PS**
In order to add rectangle to [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) with Aspose.Page for .NET library we should do following steps:
1. Create output stream for resulting PS file.
2. Create [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/) object with default options.
3. Create 1-paged PsDocument with already created output stream and save options.
4. Create rectangle **System.Drawing.Drawing2D.GraphicsPath** from the rectangle.
5. Set paint to the current graphics state of PsDocument.
6. Fill the rectangle path.
7. Close page.
8. Save document.

If we need to stroke (outline) a rectangle the first 4 and the last 2 steps will be the same, but points 5 and 6 will be:
<br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 5. Set stroke to the current graphics state of PsDocument.
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 6. Stroke (outline) the rectangle path.

```C#
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    //Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));
    //Set paint
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
    //Fill the rectangle
    document.Fill(path);

    //Create graphics path from the second rectangle
    path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));
    //Set stroke
    document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
    //Stroke (outline) the rectangle
    document.Draw(path);

    //Close current page
    document.ClosePage();

    //Save the document
    document.Save();
}
```
{{% alert color="primary" %}}
See working with shapes in PS document in [Java](/page/java/ps/working-with-shapes/) and [C++](/page/cpp/ps/working-with-shapes/).
{{% /alert %}}

The result of running this code is appeared as
</br></br></br>
<p align="center">
	<img src="AddRectangle_outPS.png">
</p>
</br></br></br>

### **Add Ellipse to PS**

In order to add ellipse to [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) also 8 steps are required:
1. Create output stream for resulting PS file.
2. Create [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/) object with default options.
3. Create 1-paged PsDocument with already created output stream and save options.
4. Create ellipse **System.Drawing.Drawing2D.GraphicsPath** from the rectangle.
5. Set paint to the current graphics state of PsDocument.
6. Fill the ellipse path.
7. Close page.
8. Save document.

If we need to stroke (outline) an ellipse the first 4 and the last 2 steps will be the same, but points 5 and 6 will be:
<br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 5. Set stroke to the current graphics state of PsDocument.
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 6. Stroke (outline) the ellipse path.
```C#
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    //Create graphics path from the first ellipse
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
    //Set paint
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
    //Fill the ellipse
    document.Fill(path);

    //Create graphics path from the second ellipse
    path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
    //Set stroke
    document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
    //Stroke (outline) the ellipse
    document.Draw(path);

    //Close current page
    document.ClosePage();

    //Save the document
    document.Save();
}
```
The result of running this code is appeared as
</br></br></br>
<p align="center">
	<img src="AddEllipse_outPS.png">
</p>
</br></br></br>

As we can see, any shape, both closed and unclosed, that can be put in **System.Drawing.Drawing2D.GraphicsPath**, can be filled or drawn by [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/).
It also can be clipped, but it will be described in other article.

{{% alert color="primary" %}}
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 
