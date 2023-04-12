---
title: Working with Document | .NET
linktitle: Working with Document
type: docs
weight: 20
url: /net/ps/working-with-document/
description: How to add pages to an PS file is a question answered by Aspose.Page API solution.  See how to use the functionality in .NET
aliases: /net/ps/create-ps-document/
---

## **Create PS Document**

Aspose.Page for .NET offers two constructors in order to create [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) class. Following code snippet creates 1-paged PS document:

```C#
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dir + "document.ps", FileMode.Create))
{
    //Create save options
    PsSaveOptions options = new PsSaveOptions();
    //If you want to assign page size other than A4, set page size in options
    options.PageSize = PageConstants.GetSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT);
    //If you want to assign page margins other than empty, set page margins in options
    options.Margins = PageConstants.GetMargins(PageConstants.MARGINS_ZERO);
    //If you plan to use fonts that are located in non system folders, set additional fonts folders in options
    options.AdditionalFontsFolders = new string[] { dir };

    //Set variable that indicates if resulting PostScript document will be multipaged
    bool multiPaged = false;

    // Create new multipaged PS Document with one page opened
    PsDocument document = new PsDocument(outPsStream, options, multiPaged);

    //Close current page
    document.ClosePage();
    //Save the document
    document.Save();
}
```
If PS document is planning to be multi-paged, set **multiPaged** variable to **true**.
<br>
<br>

Another constructor allows creating PsDocument object with defined number of pages:
```C#
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dir + "document.ps", FileMode.Create))
{
    //Create save options
    PsSaveOptions options = new PsSaveOptions();
    
    // Create new multipaged PS Document with 2 pages. These two pages are not created. It must be added by AddPage() method.
    PsDocument document = new PsDocument(outPsStream, options, 2);
    
    //Adding pages and it's content
    
    //Save the document
    document.Save();
}
```
{{% alert color="primary" %}}
See working with PS document in [Java](/page/java/ps/working-with-document/) and [C++](/page/cpp/ps/working-with-document/).
{{% /alert %}}
<br>
Let's look at [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/) class that encapsulates possible options helping to create right PostScript document.
<br>
- **SaveFormat** specifies an output format of document. Can be PS or EPS. In Aspose.Page library differences between these two formats are reflected only in PostScript comments and file extension. Also in accordance to EPS file specification EPS files should be 1-paged. PS format is used by default.

- **PageSize** specifies a size of pages in PS document. However we can assign different page size for every page if it is required. Page size can be obtained from [PageConstants](https://reference.aspose.com/page/net/aspose.page.eps/pageconstants/) class like in following example.
```C#
options.PageSize = PageConstants.GetSize(PageConstants.SIZE_International, PageConstants.ORIENTATION_PORTRAIT);
```
Default page size is "A4" in "Portrait" orientation.
<br>
<br>
- **Margins** specifies blank fields between page boundaries and left, up, right, bottom edges of the page content. It can be obtained from PageConstants class.
```C#
options.Margins = PageConstants.GetMargins(PageConstants.MARGINS_SMALL); // 20 points for each margin
```
Default margins are "ZERO" (0, 0, 0, 0).
<br>
<br>
- **BackGroundColor** specifies a color of page's background. Can be assigned as:
```C#
options.BackgroundColor = Color.FromArgb(211, 8, 48);
```
or:
```C#
options.BackgroundColor = Color.Yellow;
```
Default value is "null" that means no background.
<br>
<br>
- **EmbedFonts** controls behaviour of PsDocument while saving it to file. If "false" used fonts will not be written in PS file. In this case PostScript interpreter will throws an error if used font cannot be found in system folders on target host.

- **EmbedFontsAs** controls a way how fonts will be embedded in PS file. At this moment two ways work: TrueType and Type3 font formats. The value can be set with help of [FontConstants](https://reference.aspose.com/page/net/aspose.page.eps/fontconstants/) class like following:
```C#
options.EmbedFontsAs = FontsConstants.EMBED_FONTS_TYPE3
```
Default value is "TrueType".

- **JpegQualityLevel** specifies a level of compression/quality of images in resulting PS document. The more quality is required the less compression will be and vice versa. Minimal quality is 0, maximal - 100. Default is 75.

- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.

- **Debug** allows outputting debug information to console. Default value is false.

<br>
<br>
{{% alert color="primary" %}}
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 
