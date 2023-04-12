---
title: Working with Transparency | .NET
linktitle: Working with Transparency
type: docs
weight: 60
url: /net/xps/working-with-transparency/
description: How to work with transparency of an XPS file is a question answered by Aspose.Page API solution. See how to use the functionality in .NET
aliases: 
- /net/working-with-transparency/
- /net/set-opacity-mask/
- /net/add-transparent-object-inside-xps-document/
---

## **Set Opacity Mask**

### **Set Opacity Mask Object**
Aspose.Page for .NET offers OpacityMask property to set opacity mask on XPS path. You need to specify [XpsPathGeometry](https://reference.aspose.com/page/net/aspose.page.xps.xpsmodel/xpspathgeometry/) and 
add it to [XpsPath](https://reference.aspose.com/page/net/aspose.page.xps.xpsmodel/xpspath/). An image can be used as an opacity mask and the Alpha component of each pixel is used to apply over the underlying fill. 
Generated XPS document will show slanting gradient stripes as a present over the source image file. The following code snippet shows complete functionality to set the opacity mask:



{{< gist "aspose-com-gists" "6f0d8b5420af1af6af2d064587dd6803" "Examples-Aspose.Page.Examples.CSharp-WorkingWithTransparency-SetOpacityMaskXPS-1.cs" >}}

## **Add Transparent Object inside XPS Document**

### **Add Transparent Object**
The solution offers [XpsPath](https://reference.aspose.com/page/net/aspose.page.xps.xpsmodel/xpspath/) class, with which you can add transparent objects on an XPS document. 
You need to specify [XpsPathGeometry](https://reference.aspose.com/page/net/aspose.page.xps.xpsmodel/xpspathgeometry/) and add it to XpsPath. 
The following code snippet shows complete functionality to add transparent objects on the XPS document:

{{< gist "aspose-com-gists" "6f0d8b5420af1af6af2d064587dd6803" "Examples-Aspose.Page.Examples.CSharp-WorkingWithTransparency-AddTransparentObjectXPS-1.cs" >}}
