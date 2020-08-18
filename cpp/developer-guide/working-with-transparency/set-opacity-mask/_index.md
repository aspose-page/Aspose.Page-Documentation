---
title: Set Opacity Mask
type: docs
weight: 20
url: /cpp/set-opacity-mask/
---

# **Set Opacity Mask Object**
It is possible to set opacity mask on an XPS document. Aspose.Page for C++ can be used to create/read an XPS document and set Opacity mask on such documents. The API uses image as an opacity mask where the Alpha component of each pixel is used to apply over underlying fill. The resultant XPS document will show slanting gradient stripes as present over source image file. To set the opacity mask on an XPS document, the following steps can be used.

1. Create a new object of XpsDocument class
1. Add a canvas to the document object using the XpsCanvas class
1. Create an object [XpsPath](https://apireference.aspose.com/cpp/page/class/aspose.page.x_p_s.xps_model.xps_path/) class with required parameters
1. Set the opacity mask on the path
1. Create an XpsImageBrush class object
1. Save the document to disc using Save method



{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-SetOpacityMask-SetOpacityMask.cpp" >}}
