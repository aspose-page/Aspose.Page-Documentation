---
title: Working with Pages
type: docs
weight: 30
url: /cpp/working-with-pages/
aliases: /cpp/add-pages-to-xps-document/
---
## **Add Pages to XPS Document**

An XPS document can comprise of one or more pages. Aspose.Page for C++ allows adding pages to an XPS document without the requirement of any other software.
### **Add Pages**
The XpsDocument class of API exposes the InsertPage method that is used to add pages to an XPS document. In order to add pages to XPS document, use the following steps.

1. Create an object of [XpsDocument](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_document) class
1. Use the AddPage method to add a new page to the collection of the pages of the document
1. Save the document using the Save method of XpsDocument class

{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-AddPage-AddPage.cpp" >}}


