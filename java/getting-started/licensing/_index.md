---
title: Licensing | Java
linktitle: Licensing
type: docs
weight: 60
url: /java/licensing/
description: Java Library for the developers to process PS, EPS, and XPS files. Learn how to evaluate Aspose.Page API solution for Java.
---

## **Evaluation Version Limitations**
We want our customers to test our components thoroughly before buying so the evaluation version allows you to use it as you would normally. However, the unlicensed product:

- Allows converting of PostScript files which size is no more than 500 KB and resulting PDF document in such cases will contain evaluation mark. 
- Will not allow manipulating more than 4 XPS elements and resulting document or image in such cases will also contain evaluation mark i.e. "**Evaluation Only. Created with Aspose.Page. Copyright 2002-2019 Aspose Pty Ltd**" at the top.
## **Apply License using File or Stream Object**
The license can be loaded from a file or stream object. The easiest way to set a license is to put the license file in the same folder as the aspose-xps-xx.x.jar file and specify the filename, without a path, as shown in the example below.

{{% alert color="primary" %}} 

If you use are using any other Aspose for Java component along with Aspose.Page for Java, please specify a complete namespace for License like com.aspose.page.License.

{{% /alert %}} 
### **Loading a License from File**
The easiest way to apply a license is to put the license file in the same folder as the aspose-page-xx.x.jar file and specify just the filename without a path.

When you call the setLicense method, the license name that you pass should be that of your license file. For example, if you change the license file name to "Aspose.Page.Java.lic.xml" pass that filename to the com.aspose.page.License.setLicense(…) method. The license file can be specified for Aspose.Page for Java or you can use Aspose.Total for Java license file.

{{< gist "aspose-com-gists" "bcee4811da013bc7a78dd41af768a9d2" "Examples-src-main-java-com-aspose-page-utilities-Utils-setLicenseFromFile.java" >}}

### **Loading a License from a Stream Object**
The following example shows how to load a license from a stream.

{{< gist "aspose-com-gists" "bcee4811da013bc7a78dd41af768a9d2" "Examples-src-main-java-com-aspose-page-utilities-Utils-setLicenseFromStream.java" >}}
