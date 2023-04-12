---
title: Working with Text | .NET
linktitle: Working with Text
type: docs
weight: 40
url: /net/xps/working-with-text/
description: How to add text to an XPS file is a question answered by Aspose.Page API solution.  See how to use the functionality in .NET
aliases: /net/add-text-in-xps-document/, /net/working-with-text/
---

## **Add Text in XPS Document**
Aspose.Page for .NET offers [XpsGlyphs](https://reference.aspose.com/page/net/aspose.page.xps.xpsmodel/xpsglyphs/) class, with which you can add text on XPS documents. You need to specify any brush provided by the API.
The example below uses [XpsSolidColorBrush](https://reference.aspose.com/page/net/aspose.page.xps.xpsmodel/xpssolidcolorbrush/)
 and saves the object of [XpsDocument](https://reference.aspose.com/page/net/aspose.page.xps/xpsdocument/) class. The following code snippet shows complete functionality to add text on an XPS document:



{{< gist "aspose-com-gists" "6f0d8b5420af1af6af2d064587dd6803" "Examples-Aspose.Page.Examples.CSharp-WorkingWithText-AddTextXPS-1.cs" >}}

If you need change direction form left-to-right to right-to-left, as in Hebrew or Arabic texts, change BidiLevel property, which default value is "0", that is left-to-right.
```C#
glyphs.BidiLevel = 1;
```

