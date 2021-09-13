---
title: Add Transparent Object inside XPS Document
type: docs
weight: 10
url: /cpp/add-transparent-object-inside-xps-document/
---

# **Add Transparent Object**
Aspose.Page for C++ lets you add transparent objects to an XPS document in your applications. The [XpsPath](https://apireference.aspose.com/cpp/page/class/aspose.page.x_p_s.xps_model.xps_path/) class is used to achieve this using simple code. In order to add a transparent object to the XPS document, the following steps can be used.

1. Create a new object using the [XpsDocument](https://apireference.aspose.com/cpp/page/class/aspose.page.x_p_s.xps_document/) class
1. Create an XpsPath object with required parameters
1. Set rendering transformation information for the path
1. Use the set_Opacity method to specify the opacity value
1. Save the XPS document using the Save method.

{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-AddTransparentObject-AddTransparentObject.cpp" >}}
