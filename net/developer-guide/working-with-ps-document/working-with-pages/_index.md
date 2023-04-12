---
title: Working with Pages | .NET
linktitle: Working with Pages
type: docs
weight: 30
url: /net/ps/working-with-pages/
description: How to add pages to PS file is a question answered by Aspose.Page API solution.  See how to use the functionality in .NET
aliases: /net/ps/add-pages-to-ps-document/
---

## **Add Pages to PS Document**

Aspose.Page for .NET offers two ways of adding pages to [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument/) object.
<br>
Following code snippet creates 2-paged PS document by 8 steps:
1. Create output stream for resulting PS file.
2. Create [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/) object with default options.
3. Create 2-paged PsDocument with already created output stream and save options.
4. Open the first page with default page size of document (A4 in Portrait orientation).
5. Close the page.
6. Open the second page with new size.
7. Close the page.
8. Save document.

```C#
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);

    //Add the first page
    document.OpenPage();

    //Add content

    //Close the first page
    document.ClosePage();

    //Add the second page with different size
    document.OpenPage(400, 700);

    //Add content

    //Close the second page
    document.ClosePage();

    //Save the document
    document.Save();
}
```
{{% alert color="primary" %}}
See working with pages in PS document in [Java](/page/java/ps/working-with-pages/) and [C++](/page/cpp/ps/working-with-pages/).
{{% /alert %}}

Following code snippet creates also 2-paged PS document, but by 7 steps:
1. Create output stream for resulting PS file.
2. Create [PsSaveOptions](https://reference.aspose.com/page/net/aspose.page.eps.device/pssaveoptions/) object with default options.
3. Create multi-paged PsDocument with already created output stream and save options. In this case the first page is already opened and it's size is default page size of document (A4 in Portrait orientation).
4. Close the page.
5. Open the second page with new size.
6. Close the page.
7. Save document.
This way of adding pages is usefull when document has 1 page or it is uknown if it will be 1- or 2-paged document.

```C#
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document2.ps", FileMode.Create))
{
    //Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    //Set variable that indicates if resulting PostScript document will be multipaged
    bool multiPaged = true;

    // Create new multipaged PS Document with one page opened
    PsDocument document = new PsDocument(outPsStream, options, multiPaged);

    //Add content

    //Close the first page
    document.ClosePage();

    //Add the second page with different size
    document.OpenPage(500, 300);

    //Add content

    //Close the second page
    document.ClosePage();

    //Save the document
    document.Save();
}
```
{{% alert color="primary" %}}
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}} 


