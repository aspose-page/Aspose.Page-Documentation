---
title: Change named value in XMP metadata of EPS file using Java
type: docs
weight: 18
url: /java/xmp-metadata/change-named-value/
description: The process of changing named value in XMP metadata of EPS file with Aspose.Page API solution for Java is explained and illustrated with the code here.
---

<!--
{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a> {{% /alert %}}
-->

In order to change named value in XMP metadata of EPS file it is necessary to do several steps:
1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://reference.aspose.com/page/java/com.aspose.eps/psdocument) from created earlier input stream.
3. Get an instance of [XmpMetadata](https://reference.aspose.com/page/java/com.aspose.eps.xmp/xmpmetadata) from the PsDocument. If given EPS file doesn't contain XMP metadata the new one
will be created, filled in with values from PS metadata comments and returned to you.
4. Now you can change named value of structure metadata fileds.
5. Initialize an output stream for output EPS file.
6. Save EPS file with changed XMP metadata.

<br>Following code snippet shows how to change named value in XMP metadata in EPS file in Java:
<br>
```Java
// Set license
new License().setLicense(BaseExamplesTest.LICENSE_PATH);

// The path to the documents directory.
String dataDir = Utils.getDataDir();

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");

PsDocument document = new PsDocument(psStream);

try {
    // Get XMP metadata. If EPS file doesn't contain XMP metadata we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
    XmpMetadata xmp = document.getXmpMetadata();

    // Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
    xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
    
    
    // Initialize output EPS file stream
    FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
    
    // Save document with changed XMP metadata
		try {			
			document.save(outPsStream);
		} finally {
			outPsStream.close();
		}

} finally {
    // close input EPS stream
		psStream.close();
}
```
{{% alert color="primary" %}}
See changing named value in XMP metadata in [.NET](/page/net/xmp-metadata/change-named-value/) and [C++](/page/cpp/xmp-metadata/change-named-value/).
{{% /alert %}}

<!--
{{% alert color="primary" %}}
Evaluate EPS to PDF conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a>. You can convert several EPS files to PDF at once and dowload results in a few seconds.
 {{% /alert %}}
-->
<br>
<br>
{{% alert color="primary" %}}
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-Java). {{% /alert %}}