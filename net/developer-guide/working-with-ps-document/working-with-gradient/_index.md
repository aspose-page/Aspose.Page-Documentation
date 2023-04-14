---
title: Working with Gradient | .NET
linktitle: Working with Gradient
type: docs
weight: 100
url: /net/ps/working-with-gradient/
description: How to add gradient in PS file is a question answered by Aspose.Page API solution.  See how to use the functionality in .NET
keywords: working with gradient in PS .NET, working with gradient in PostScript .NET, working with gradient in EPS .NET
aliases: /net/ps/add-gradient-in-ps-document/
---

## **Add Gradient in PS Document**
In this article we consider the ways how a gradient can be used in PS document.
<br>
Gradient is a smooth transition of one color to another. It is used for making drawn picture more realistic.
As gradient is a kind of paint, it is expectedly that in .NET it is implemented as a subclass of **System.Drawing.Brush**. Actually, .NET platform has two such brushes:

- **System.Drawing.LinearGradientBrush**
- **System.Drawing.PathGradientBrush**

In order to set a paint or a stroke in [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) we must pass an object of **System.Drawing.Brush** class for a painting and
an object of **System.Drawing.Pen** for a stroking into respective methods. Aspose.Page for .NET library processes all subclasses of **System.Drawing.Brush** that are offered by .NET platform. These are **System.Drawing.SolidBrush**,
**System.Drawing.TextureBrush**, **System.Drawing.LinearGradientBrush**, **System.Drawing.PathGradientBrush** and **System.Drawing.HatchBrush**. **System.Drawing.Pen** class cannot be extended because it is sealed,
but it contains **System.Drawing.Brush** as a property and, thus, Aspose.Page for .NET library can also use complete set of brushes also for drawing lines and outlining shapes and text.
<br>
<br>
In order to *paint* graphics objects with a gradient in Aspose.Page for .NET library it is necessary to create **System.Drawing.LinearGradientBrush** or 
**System.Drawing.PathGradientBrush** and pass it to **SetPaint()** or one of the **FillText()** or **FillAndStrokeText()** methods which accepts **System.Drawing.Brush** as a parameter.
<br>
In order to *outline* graphics objects with a gradient in Aspose.Page for .NET library someone should create **System.Drawing.LinearGradientBrush** or 
**System.Drawing.PathGradientBrush**, than create **System.Drawing.Pen** with this brush and, finally,
pass it to **SetStroke()** or one of the **OutlineText()** or **FillAndStrokeText()** methods which accepts **System.Drawing.Pen** as a parameter.
<br>
<br>
In the example below we demonstrate how to fill a shape and a text and outline a text with a gradient.
<br>
<br>
An algorythm of *painting* graphics objects with a gradient in new PS document includes following steps:
1. Create an output stream for resulting PS file.
2. Create [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/).
3. Create [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) with already created output stream and save options.
4. Create necessary graphics path or font in dependence on what object we are going to fill or outline.
5. Create an object of **System.Drawing.LinearGradientBrush** or **System.Drawing.PathGradientBrush** in dependence on wishfull form of a gradient.
6. Set necessary transformation on this brush.
8. Set the gradient brush as current paint in PsDocument
9. Fill the graphics path with current paint or fill a text. If we use one of the methods for filling the text that accepts **System.Drawing.Brush** as a parameter, previous point can be ignored.
10. Close the page.
11. Save the document.

If we need *stroking (outlining)* graphics objects with a gradient instead of the last 4 points following will be:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;8. Create **System.Drawing.Pen** object with the gradient brush.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;9. Set this pen as current stroke in PsDocument.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;10. Outline the graphics path with current stroke or outline the text. If we use one of the methods for outlining the text that accepts **System.Drawing.Pen**
as a parameter, previous point can be ignored.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;11. Close the page.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;12. Save the document.<br>

We offer 5 code snippets that demonstrate a usage of different gradients
<br>
<br>
In this code snippet we create horizontal linear gradient from two colors, fill a rectangle, fill a text, outline a text with this gradient.
```C#
//Create an output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    //Create a graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    //Create linear gradient brush with the rectangle as bounds, start and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
    //Create a transform for the brush. X and Y scale component must be equal to the width and the height of the rectangle respectively.
    //Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    //Set  the transform
    brush.Transform = brushTransform;

    //Set the paint
    document.SetPaint(brush);

    //Fill the rectangle
    document.Fill(path);

    //Fill the text with the gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));

		//Set current stroke
		document.SetStroke(brush, 5);
    //Outline text with the gradient
    document.OutlineText("ABC", font, 200, 400);

    //Close current page
    document.ClosePage();

    //Save the document
    document.Save();
}
```
The result of running this code is appeared as
</br></br></br>
<p align="center">
	<img src="HorizontalGradient.png">
</p>
</br></br></br>

In this code snippet we create vertical linear gradient from 5 colors and fill a rectangle with this gradient.
```C#
//Create an output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    //Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    //Create an array of interpolation colors
    Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
    float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
    ColorBlend colorBlend = new ColorBlend();
    colorBlend.Colors = colors;
    colorBlend.Positions = positions;

    //Create linear gradient brush with the rectangle as bounds, start and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
    //Set interpolation colors
    brush.InterpolationColors = colorBlend;
    //Create a transform for the brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    //Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    //Rotate the graphics state to get colors change in vertical direction from up to down
    brushTransform.Rotate(90);
    //Set the transform
    brush.Transform = brushTransform;

    //Set the paint
    document.SetPaint(brush);

    //Fill the rectangle
    document.Fill(path);

    //Close current page
    document.ClosePage();

    //Save the document
    document.Save();
}
```
The result
</br></br></br>
<p align="center">
	<img src="VerticalGradient.png">
</p>
</br></br></br> 

In this code snippet we create diagonal linear gradient from 2 colors and fill a rectangle with this gradient.
```C#
//Create an output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    //Create a graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    //Create linear gradient brush with the rectangle as bounds, start and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
        Color.FromArgb(255, 0, 0, 255), 0f);

    //Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    //Translation components are offsets of the rectangle        
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    //Rotate the gradient, than scale and translate to get visible a color transition in required rectangle
    brushTransform.Rotate(-45);
    float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
    float ratio = hypotenuse / 200;
    brushTransform.Scale(-ratio, 1);
    brushTransform.Translate(100 / brushTransform.Elements[0], 0);

    //Set the transform
    brush.Transform = brushTransform;

    //Set the paint
    document.SetPaint(brush);

    //Fill the rectangle
    document.Fill(path);

    //Close current page
    document.ClosePage();

    //Save the document
    document.Save();
}
```
The result
</br></br></br>
<p align="center">
	<img src="DiagonaGradient.png">
</p>
</br></br></br>

In this code snippet we create radial gradient from 2 colors and fill a circle with this gradient.
```C#
//Create an output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "RadialGradient1_outPS.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 200;

    //Create a graphics path from the rectangle bounds
    RectangleF bounds = new System.Drawing.RectangleF(offsetX, offsetY, width, height);
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddEllipse(bounds);

    //Create and fill color blend object
    Color[] colors = { Color.White, Color.White, Color.Blue };
    float[] positions = { 0.0f, 0.2f, 1.0f };
    ColorBlend colorBlend = new ColorBlend();
    colorBlend.Colors = colors;
    colorBlend.Positions = positions;

    GraphicsPath brushRect = new GraphicsPath();
    brushRect.AddRectangle(new RectangleF(0, 0, width, height));

    //Create path gradient brush with the rectangle as bounds
    PathGradientBrush brush = new PathGradientBrush(brushRect);
    //Set interpolation colors
    brush.InterpolationColors = colorBlend;
    //Create a transform for the brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    //Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    //Set the transform
    brush.Transform = brushTransform;

    //Set the paint
    document.SetPaint(brush);

    //Fill the rectangle
    document.Fill(path);

    //Close current page
    document.ClosePage();

    //Save the document
    document.Save();
}
```
The result
</br></br></br>
<p align="center">
	<img src="RadialGradient1.png">
</p>
</br></br></br>

In this code snippet we create radial gradient from 6 colors and fill a rectangle with this gradient.
```C#
//Create an output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "RadialGradient2_outPS.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 200;

    //Create a graphics path from the rectangle bounds
    RectangleF bounds = new System.Drawing.RectangleF(offsetX, offsetY, width, height);
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(bounds);

    //Create and fill color blend object
    Color[] colors = { Color.Green, Color.Blue, Color.Black, Color.Yellow, Color.Beige, Color.Red };
    float[] positions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
    ColorBlend colorBlend = new ColorBlend();
    colorBlend.Colors = colors;
    colorBlend.Positions = positions;

    GraphicsPath brushRect = new GraphicsPath();
    brushRect.AddRectangle(new RectangleF(0, 0, width, height));

    //Create path gradient brush with the rectangle as bounds
    PathGradientBrush brush = new PathGradientBrush(brushRect);
    //Set interpolation colors
    brush.InterpolationColors = colorBlend;
    //Create a transform for the brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    //Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    //Set the transform
    brush.Transform = brushTransform;

    //Set the paint
    document.SetPaint(brush);

    //Fill the rectangle
    document.Fill(path);

    //Close current page
    document.ClosePage();

    //Save the document
    document.Save();
}
```
The result
</br></br></br>
<p align="center">
	<img src="RadialGradient2.png">
</p>
</br></br></br>

{{% alert color="primary" %}}
See working with gradient in PS document in [Java](/page/java/ps/working-with-gradient/) and [C++](/page/cpp/ps/working-with-gradient/).
{{% /alert %}}


{{% alert color="primary" %}}
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 
