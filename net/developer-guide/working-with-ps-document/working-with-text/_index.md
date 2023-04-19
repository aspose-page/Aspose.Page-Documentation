---
title: Working with Text | .NET
linktitle: Working with Text
type: docs
weight: 70
url: /net/ps/working-with-text/
description: How to add textt in PS file is a question answered by Aspose.Page API solution.  See how to use the functionality in .NET
keywords: working with text in PS .NET, working with text in PostScript .NET, working with text in EPS .NET
aliases: /net/ps/add-text-in-ps-document/
---

## **Add Text in PS Document**
In this article, we consider the ways how a text can be added to a PS document.
<br>
Obviously, the text should be written in a document with some font. Fonts can be stored in system folders, and in this case, we call them **system fonts**and can be stored in custom
folders, which are folders in which someone put fonts for particular usage. Usually, these fonts are absent in system folders. We call such fonts **custom fonts**.
Aspose.Page for .NET library offers methods for using both **system** and **custom** fonts. 
<br>
<br>
For using system fonts we just fill or outline a text with native .NET's **System.Drawing.Font**. Numbers in the method's call are x and y coordinates of the top-left corner of the text.
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
Another option is working with text that also belongs to a font. The font that is used to print text in the PostScript document can be embedded in this file or not embedded. 
In the first case, the text will always be rendered in any PostScript viewer or editor because it always lies with the text. In the second case, we should expect that the used font exists in system folders
on the target host. If the used font doesn't exist PostScript interpreter can throw an error.
<br>
The third option is also about a font because a font is the main thing in adding text. A font used for filling or drawing (or may be clipping) a text can be embedded in a PS file in various forms. 
Now TrueType and Type3 font types in embedding are supported.
<br>
In the example below we demonstrate the usage of various methods of adding text in a PS document with Aspose.Page for .NET library.
<br>
<br>
An algorithm for adding a text in new PS document includes the following steps:
1. Create an output stream for the resulting PS file.
2. Create [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/). If we will use a custom font we add custom fonts folder(s) in the save options.
3. Create [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) with the already created output stream and save options.
4. Create necessary font, **system** or **custom**.
5. Fill or outline the text with the created font. Here we can assign **System.Drawing.Brush** or **System.Drawing.Pen** in dependence whether we fill or draw the text. Or we can fill and outline the text
in one method. If we use a method without **System.Drawing.Brush** or **System.Drawing.Pen**, the text will be filled or outlined with current paint/stroke in the current graphics state.
6. Close the page.
7. Save the document.
<br>

We split the example code into little code snippets in order to separate the initial preparation for the PS document, the usage of every method for adding text, and the completion of the document.
<br>
<br>
In this piece of code, we create an outputstream and PsSaveOptions, add a custom fonts folder for using the custom font in the code, create a PsDocument object, set common for all methods text as a string variable, 
and create fontSize variable that is also used in every used method.

```C#
//Create a output stream for PostScript document
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
Here we demonstrate the usage of **system font** for filling the text with the current color of the graphics state (that is black) and with the new **SolidBrush**.
```C#
////////////////////////////////////// Using sysem font (located in system fonts folders) for filling the text //////////////////
    System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
    //Fill the text with default or already defined color. In given case it is black.
    document.FillText(str, font, 50, 100);
    //Fill the text with Blue color.
    document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
```
The result
</br></br></br>
<p align="center">
	<img src="AddText1.png">
</p>
<p align="center">
	<img src="AddText2.png">
</p>
</br></br></br> 

Now we fill the text with **custom font**.
```C#
////////////////////////////////////// Using custom font (located in custom fonts folders) for filling the text /////////////////
	  DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
	  //Fill the text with default or already defined color. In given case it is black.
	  document.FillText(str, drFont, 50, 200);
	  //Fill the text with Blue color.
	  document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
```
The result
</br></br></br>
<p align="center">
	<img src="AddText3.png">
</p>
<p align="center">
	<img src="AddText4.png">
</p>
</br></br></br>

Here we demonstrate the usage of **system font** for outlining the text with the current stroke of graphics state (that is black) and with the new **Pen**.
```C#
////////////////////////////////////// Using sysem font (located in system fonts folders) for outlining the text ////////////////
	  //Outline the text with default or already defined pen. In given case it is black colored 1-points width pen.
	  document.OutlineText(str, font, 50, 300);
	  //Outline the text with blue-violet colored 2-points width pen.
	  document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
```
The result
</br></br></br>
<p align="center">
	<img src="AddText5.png">
</p>
<p align="center">
	<img src="AddText6.png">
</p>
</br></br></br>

Now we outline the text with **custom font**.
```C#
////////////////////////////////////// Using custom font (located in custom fonts folders) for outlining the text /////////////////
		//Outline the text with default or already defined pen. In given case it is black colored 1-points width pen.
		document.OutlineText(str, drFont, 50, 450);
		//Outline the text with blue-violet colored 2-points width pen.
		document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));		
///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
```
The result
</br></br></br>
<p align="center">
	<img src="AddText8.png">
</p>
<p align="center">
	<img src="AddText9.png">
</p>
</br></br></br>

Here we demonstrate the usage of **system font** for filling and outlining the text with new **SolidBrush** and **Pen**.
```C#
    //Fill the text with orange color and stroke with blue colored 2-points width pen.
    document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```
The result
</br></br></br>
<p align="center">
	<img src="AddText7.png">
</p>
</br></br></br>

And finally we fill and an outline the text with **custom font**.
```C#
		//Fill the text with orange color and stroke with blue colored 2-points width pen.
		document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```
The result
</br></br></br>
<p align="center">
	<img src="AddText10.png">
</p>
</br></br></br>

Close the current page, save the document.
```C#
    //Close current page
    document.ClosePage();
    
    //Save the document
    document.Save();
```

{{% alert color="primary" %}}
See working with a text in PS documents in [Java](/page/java/ps/working-with-text/) and [C++](/page/cpp/ps/working-with-text/).
{{% /alert %}}

In the example above, there are used fonts embedded in the PostScript file as TrueType fonts, because it is the default behavior of saving fonts in PsDocument class.
If you need to change this behavior, please, use [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/) like the following:
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
