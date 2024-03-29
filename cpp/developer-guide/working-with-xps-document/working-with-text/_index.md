---
title: Working with Text | C++
linktitle: Working with Text
type: docs
weight: 10
url: /cpp/working-with-text/
description: How to add text to an XPS file is a question answered by Aspose.Page API solution.  See how to use the functionality in C++
aliases: /cpp/add-text-in-xps-document/
---
## **Add Text**
### **Add Text to XPS Document**
Aspose.Page for C++ lets you add text to an XPS document in your C++ applications. The [**XpsGlyphs**](https://reference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_model.xps_glyphs) class lets you add text to an XPS document by specifying the brush of your choice. Text can be added to an XPS document using the following steps:

1. Create a new instance of [XPSDocument](https://reference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_document) class
1. Create a brush using the [XpsSolidColorBrush](https://reference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_model.xps_solid_color_brush) class
1. Add glyph to the document object with required font information
1. Save the file using the Save method of XPSDocument class

The following code snippet shows complete functionality for adding text to an XPS document using C++.



{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-AddText-AddText.cpp" >}}
### **Add Text Using Encoding String**
Aspose.Page for C++ offers [**XpsGlyphs**](https://reference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_model.xps_glyphs) Class, with which you can add text using Encoding String on an XPS document. You need to specify a brush using **BidiLevel** property of **XpsGlyphs** class. Following code snippet shows complete functionality to add text using encoding string:



{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-AddTextUsingUnicodeString-AddTextUsingUnicodeString.cpp" >}}
