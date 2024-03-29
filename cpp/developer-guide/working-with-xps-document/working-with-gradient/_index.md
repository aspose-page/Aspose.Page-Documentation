---
title: Working with Gradient | C++
linktitle: Working with Gradient
type: docs
weight: 40
url: /cpp/working-with-gradient/
description: How to add vertical, horizontal or linear gradient to an XPS file is a question answered by Aspose.Page API solution. Learn the functionality for C++
aliases: /cpp/add-gradient-in-xps-document/
---
## **Add Gradient in XPS Document**
### **Add Horizontal Gradient**
Aspose.Page for C++ lets you add horizontal gradient to an XPS document. The [XpsGrandientBrush](https://reference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_model.xps_gradient_brush/) class is used to specify the XpsGredientStop and [XpsPath](https://reference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_model.xps_path) information to the [XpsDocument](https://reference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_document) object which represents the XPS file. The following C++ code shows how to add horizontal gradient information to a document.

1. Create an object of [XpsDocument](https://reference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_document) class
1. Specify the XpsGradientStop and [XpsPath](https://reference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_model.xps_path) parameters for the XPS document
1. Set the rendering information
1. Save the document


{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-AddHorizontalGradient-AddHorizontalGradient.cpp" >}}
### **Add Vertical Gradient**
Just as you can add the Horizontal gradient, you can use Aspose.Page for C++ to add vertical gradient information to the XPS document. The following C++ code sample shows how to add a verticle gradient to an XPS document.


{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-AddVerticalGradient-AddVerticalGradient.cpp" >}}
### **Add Linear Gradient**
You can also add linear gradient to an XPS document using Aspose.Page for C++ as shown in the following code sample.


{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-AddLinearGradient-AddImage.cpp" >}}



