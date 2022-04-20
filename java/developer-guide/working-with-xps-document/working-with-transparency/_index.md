---
title: Working with Transparency
type: docs
weight: 60
url: /java/working-with-transparency/
aliases:
- /java/add-transparent-object-inside-xps-document/
- /java/set-opacity-mask/
---

## **Add Transparent Object inside XPS Document**
Aspose.Page for Java offers **XpsPath** Class, with which you can add transparent object on XPS document. You need to specify PathGeometry and add it to **XpsPath.** Following code snippet shows complete functionality to add transparent object on an XPS document:

{{< gist "aspose-com-gists" "bcee4811da013bc7a78dd41af768a9d2" "Examples-src-main-java-com-aspose-page-transparency-AddTransparentObject-TransparentObject.java" >}}

## **Set Opacity Mask**
The solution offers **setOpacityMask()** property, with which you can set opacity mask on XPS document. You need to create PathGeometry and add it to **XpsPath.** An image can be used as an opacity mask and Alpha component of each pixel is used to apply over underlying fill. Generated XPS document will show slanting gradient stripes as a present over source image file. Following code snippet shows complete functionality to set opacity mask:

{{< gist "aspose-com-gists" "bcee4811da013bc7a78dd41af768a9d2" "Examples-src-main-java-com-aspose-page-transparency-SetOpacityMask-SetOpacityMask.java" >}}


