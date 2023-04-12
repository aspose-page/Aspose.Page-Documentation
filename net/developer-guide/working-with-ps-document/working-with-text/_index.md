---
title: Working with Text | .NET
linktitle: Working with Text
type: docs
weight: 70
url: /net/ps/working-with-text/
description: How to add textt in PS file is a question answered by Aspose.Page API solution.  See how to use the functionality in .NET
aliases: /net/ps/add-text-in-ps-document/
---

## **Add Text in PS Document**
In this article we consider the ways how a text can be added to PS document.
<br>
Obviously, a text should be written in a document with some font. Fonts can be stored in system folders, and in this case we call it **system fonts**, and can be stored in custom
folders, that are folders in which someone put fonts for particular usage. Usually these fonts  are absent in system folders. We call such fonts **custom fonts**.
Aspose.Page for .NET library offers methods for using both **system** and **custom** fonts. 
<br>
<br>
For using system fonts we just fill or outline a text with native .NET's **System.Drawing.Font**. Numbers in the method call are x and y coordinate of the top-left corner of the text.
```C#
document.FillText(str, new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold), 50, 100);
```
For using custom fonts we, firstly add **custom fonts** folder in PsSaveOptions, then fetch [Aspose.Page.Font.DrFont](https://reference.aspose.com/page/net/aspose.page.font/drfont/). 
And finally fill or outline text with this DrFont object.
```C#
options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
Aspose.Page.Font.DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 100);
```
Another options in working with text is also belongs to font. Font that is used to print text in PostScript document can be embedded in this file or not embedded. 
In the first case the text will always be rendered in any PostScript viewer or editor because it always lies with the text. In the second case we should expect that used font exists in system folders
on target host. If used font doesn't exist PostScript interpretator can throw an error.
<br>
The third option is also about font, because font it is main thing in adding text. Font used for filling or drawing (or may be clipping) a text can be embedded in PS file in various forms. 
Now TrueType and Type3 font types in embedding are supported.
<br>
In example below we demonstrate usage of various methods of adding text in PS document with Aspose.Page for .NET library.
<br>
<br>
An algorythm of adding text in new PS document includes following steps:
1. Create output stream for resulting PS file.
2. Create [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/). If we will use custom font we add custom fonts folder(s) in save options.
3. Create [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) with already created output stream and save options.
4. Create necessary font, **system** or **custom**.
5. Fill or outline text with created font. Here we can assign **System.Drawing.Brush** or **System.Drawing.Pen** in dependence whether we fill or draw the text. Or we can fill and outline text
in one method. If we use a method without **System.Drawing.Brush** or **System.Drawing.Pen** text will be filled or outlined with current paint/stroke in current graphics state.
6. Close page.
7. Save document.
<br>

We split example code on little code snippets in order to separate initial preparation fo PS document, usage of every method for adding text and completion of the document
<br>
<br>
In this piece of code we create an outpustream and PsSaveOptions, add custom fonts folder for using custom font in the code, create PsDocument object, set common for all methods text as a string variable, 
and create fontSize variable that also used in every used method.
```C#
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    // Set custom fonts folder. It will be added to system fonts folders for finding needed font.
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    //A text to write to PS file
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```
Here we demonstrate usage of **system font** for filling text with current color of graphics state (that is black) and with new **SolidBrush**.
```C#
////////////////////////////////////// Using sysem font (located in system fonts folders) for filling text //////////////////
    System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
    //Fill text with default or already defined color. In given case it is black.
    document.FillText(str, font, 50, 100);
    //Fill text with Blue color.
    document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
```
The result
</br></br></br>
<p align="center">
	<img src="AddText1_outPS.png">
</p>
<p align="center">
	<img src="AddText2_outPS.png">
</p>
</br></br></br> 

Now we fill the text with **custom font**.
```C#
////////////////////////////////////// Using custom font (located in custom fonts folders) for filling text /////////////////
	  DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
	  //Fill text with default or already defined color. In given case it is black.
	  document.FillText(str, drFont, 50, 200);
	  //Fill text with Blue color.
	  document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
```
The result
</br></br></br>
<p align="center">
	<img src="AddText3_outPS.png">
</p>
<p align="center">
	<img src="AddText4_outPS.png">
</p>
</br></br></br>

Here we demonstrate usage of **system font** for outlining text with current stroke of graphics state (that is black) and with new **Pen**.
```C#
////////////////////////////////////// Using sysem font (located in system fonts folders) for outlining text ////////////////
	  //Outline text with default or already defined pen. In given case it is black colored 1-points width pen.
	  document.OutlineText(str, font, 50, 300);
	  //Outline text with blue-violet colored 2-points width pen.
	  document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
```
The result
</br></br></br>
<p align="center">
	<img src="AddText5_outPS.png">
</p>
<p align="center">
	<img src="AddText6_outPS.png">
</p>
</br></br></br>

Now we outline the text with **custom font**.
```C#
////////////////////////////////////// Using custom font (located in custom fonts folders) for outlining text /////////////////
		//Outline text with default or already defined pen. In given case it is black colored 1-points width pen.
		document.OutlineText(str, drFont, 50, 450);
		//Outline text with blue-violet colored 2-points width pen.
		document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));		
///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
```
The result
</br></br></br>
<p align="center">
	<img src="AddText8_outPS.png">
</p>
<p align="center">
	<img src="AddText9_outPS.png">
</p>
</br></br></br>

Here we demonstrate usage of **system font** for filling and outlining text with new **SolidBrush** and **Pen**.
```C#
    //Fill text with orange color and stroke with blue colored 2-points width pen.
    document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```
The result
</br></br></br>
<p align="center">
	<img src="AddText7_outPS.png">
</p>
</br></br></br>

And finally we fill and outline the text with **custom font**.
```C#
		//Fill text with orange color and stroke with blue colored 2-points width pen.
		document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```
The result
</br></br></br>
<p align="center">
	<img src="AddText10_outPS.png">
</p>
</br></br></br>

Close current page, save the document.
```C#
    //Close current page
    document.ClosePage();
    
    //Save the document
    document.Save();
```

{{% alert color="primary" %}}
See working with text in PS document in [Java](/page/java/ps/working-with-text/) and [C++](/page/cpp/ps/working-with-text/).
{{% /alert %}}

In example above used fonts are embedded in PostScript file as TrueType fonts, because it is default behaviour of saving fonts in PsDocument class.
If you need change this behaviour, pelase, use [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/) like following:
```C#
		//Do not embed used fonts.
		options.EmbedFonts = false;
```
```C#
		//Embed used fonts as Type3 fonts.
		options.EmbedFontsAs = FontConstants.EMBED_FONTS_TYPE3;
```

{{% alert color="primary" %}}
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 
