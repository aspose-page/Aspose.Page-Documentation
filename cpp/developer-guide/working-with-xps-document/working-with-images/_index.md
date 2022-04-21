---
title: Working with Images
type: docs
weight: 20
url: /cpp/working-with-images/
aliases: /cpp/add-image-inside-xps-documents/
---

## **Add Image inside XPS Documents**

### **Add Image**
Aspose.Page for C++ API lets you create/read XPS documents and add image to it. This can be done by creating a Matrix and an ImageBrush to add the image to the XPS file. In order to add an image to XPS document, use the following steps.

1. Create an object of [XpsDocument](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_document) class
1. Create [XpsPath](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_model.xps_path) object with defined Path Geometry
1. Set Render Transformation for the path
1. Save the document to disc using the Save method


{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-AddImage-AddImage.cpp" >}}
### **Add Tiled Image**
The solution offers [**XpsPath**](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_model.xps_path) Class, with which you can add image on XPS document. You need to create Matrix and an ImageBrush, then specify [**XpsTileMode**](https://apireference.aspose.com/page/cpp/namespace/aspose.page.x_p_s.xps_model#ab108058633c51d92b4a707c2d60b850e)**.Tile** mode and save XpsDocument. Following code snippet shows complete functionality to add tiled image on an XPS document:

{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-AddTiledImage-AddTiledImage.cpp" >}}

