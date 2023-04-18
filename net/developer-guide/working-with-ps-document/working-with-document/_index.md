---
title: Working with Document | .NET
linktitle: Working with Document
type: docs
weight: 20
url: /net/ps/working-with-document/
description: Adding pages to an PS file is a functionality supported by Aspose.Page API solution.  See how to use the functionality in .NET.
keywords: working with document in PS .NET, working with document in PostScript .NET, working with document in EPS .NET
aliases: /net/ps/create-ps-document/
---

## **Create PS Document**

Aspose.Page for .NET offers two constructors in order to create [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) class. The following code snippet creates a 1-paged PS document:

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

Another constructor allows creating PsDocument object with a defined number of pages:
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
Let's look at the [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/) class that encapsulates possible options helping to create the right PostScript document.
<br>
- **SaveFormat** specifies an output format of documents. Can be PS or EPS. In Aspose.Page library differences between these two formats are reflected only in PostScript comments and a file extension.
Also in accordance with the EPS file specification EPS files should be 1-paged. PS format is used by default.

- **PageSize** specifies the size of the pages in the PS document. However, we can assign different page sizes for every page if it is required. The page size can be obtained from [PageConstants](https://reference.aspose.com/page/net/aspose.page.eps/pageconstants/) class like in following example:
```C#
options.PageSize = PageConstants.GetSize(PageConstants.SIZE_International, PageConstants.ORIENTATION_PORTRAIT);
```
The default page size is "A4" in "Portrait" orientation.
<br>
<br>
- **Margins** specifies blank fields between the page boundaries and left, up, right, and bottom edges of the page content. It can be obtained from PageConstants class.

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


- **EmbedFonts** controls the behavior of PsDocument while saving it to the file. If "false", used fonts will not be written in the PS file. In this case, the PostScript interpreter will throw an error if the used font cannot be found in system folders on the target host.

- **EmbedFontsAs** controls the way how fonts will be embedded in the PS file. At this moment two ways work TrueType and Type3 font formats. The value can be set with help of [FontConstants](https://reference.aspose.com/page/net/aspose.page.eps/fontconstants/) class like the following:

```C#
options.EmbedFontsAs = FontsConstants.EMBED_FONTS_TYPE3
```
The default value is "TrueType".

- **JpegQualityLevel** specifies a level of compression/quality of images in the resulting PS document. The more quality is required the less compression will be and vice versa. Minimal quality is 0, and maximal - 100. The default is 75.

- **AdditionalFontsFolder** specifies locations where to find fonts. System font folders are always included by default.

- **Debug** allows outputting debug information to the console. The default value is false.

<br>
<br>
{{% alert color="primary" %}}
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 
