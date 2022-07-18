---
title: Working with Transparency | C++
linktitle: Working with Transparency
type: docs
weight: 60
url: /cpp/working-with-transparency/
description: How to work with transparency of an XPS file is a question answered by Aspose.Page API solution. See how to use the functionality in C++
aliases:
- /cpp/set-opacity-mask/
- /cpp/add-transparent-object-inside-xps-document/
---
 ## **Set Opacity Mask**

 ### **Set Opacity Mask Object**
It is possible to set opacity mask on an XPS document. Aspose.Page for C++ can be used to create/read an XPS document and set Opacity mask on such documents. The API uses image as an opacity mask where the Alpha component of each pixel is used to apply over underlying fill. The resultant XPS document will show slanting gradient stripes as present over source image file. To set the opacity mask on an XPS document, the following steps can be used.

1. Create a new object of XpsDocument class
1. Add a canvas to the document object using the XpsCanvas class
1. Create an object [XpsPath](https://reference.aspose.com/cpp/page/class/aspose.page.x_p_s.xps_model.xps_path/) class with required parameters
1. Set the opacity mask on the path
1. Create an XpsImageBrush class object
1. Save the document to disc using Save method


{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-SetOpacityMask-SetOpacityMask.cpp" >}}


## **Add Transparent Object inside XPS Document**

### **Add Transparent Object**
Aspose.Page for C++ lets you add transparent objects to an XPS document in your applications. The [XpsPath](https://reference.aspose.com/cpp/page/class/aspose.page.x_p_s.xps_model.xps_path/) class is used to achieve this using simple code. In order to add a transparent object to the XPS document, the following steps can be used.

1. Create a new object using the [XpsDocument](https://reference.aspose.com/cpp/page/class/aspose.page.x_p_s.xps_document/) class
1. Create an XpsPath object with required parameters
1. Set rendering transformation information for the path
1. Use the set_Opacity method to specify the opacity value
1. Save the XPS document using the Save method.

{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-AddTransparentObject-AddTransparentObject.cpp" >}}
