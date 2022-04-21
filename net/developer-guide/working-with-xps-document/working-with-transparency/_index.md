---
title: Working with Transparency
type: docs
weight: 60
url: /net/working-with-transparency/
aliases: 
- /net/set-opacity-mask/
- /net/add-transparent-object-inside-xps-document/
---

## **Set Opacity Mask**

### **Set Opacity Mask Object**
Aspose.Page for .NET offers **OpacityMask** property, with which you can set opacity mask on XPS document. You need to specify PathGeometry and add it to **XpsPath.** An image can be used as an opacity mask and Alpha component of each pixel is used to apply over underlying fill. Generated XPS document will show slanting gradient stripes as a present over source image file. Following code snippet shows complete functionality to set opacity mask:



{{< gist "aspose-com-gists" "6f0d8b5420af1af6af2d064587dd6803" "Examples-Aspose.Page.Examples.CSharp-WorkingWithTransparency-SetOpacityMask-1.cs" >}}

## **Add Transparent Object inside XPS Document**

### **Add Transparent Object**
The solution offers **XpsPath** Class, with which you can add transparent object on XPS document. You need to specify PathGeometry and add it to **XpsPath.** Following code snippet shows complete functionality to add transparent object on an XPS document:

{{< gist "aspose-com-gists" "6f0d8b5420af1af6af2d064587dd6803" "Examples-Aspose.Page.Examples.CSharp-WorkingWithTransparency-AddTransparentObject-1.cs" >}}
