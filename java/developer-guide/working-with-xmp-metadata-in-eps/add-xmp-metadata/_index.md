---
title: Add XMP metadata to EPS file using Java
type: docs
weight: 13
url: /java/xmp-metadata/add/
description: The process of adding XMP metadata to EPS file with Aspose.Page API solution for Java is explained and illustrated with the code snippets here.
---

<!--
{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a> {{% /alert %}}
-->

In order to add XMP metadata to EPS file it is necessary to do several steps:
1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://apireference.aspose.com/page/java/com.aspose.eps/psdocument) from created earlier input stream.
3. Get an instance of [XmpMetadata](https://apireference.aspose.com/page/java/com.aspose.eps.xmp/xmpmetadata) from the PsDocument. If given EPS file doesn't contain XMP metadata the new one
will be created, filled in with values from PS metadata comments and returned to you.
4. Now you can view values of metadata fileds.
5. Initialize an output stream for output EPS file.
6. Save EPS file with new XMP metadata.

<br>Following code snippet shows how to add XMP metadata to EPS file in Java:
<br>
```Java
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-Java
// Set license
new License().setLicense(BaseExamplesTest.LICENSE_PATH);

// The path to the documents directory.
String dataDir = Utils.getDataDir();

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");

PsDocument document = new PsDocument(psStream);

try {
    // Get XMP metadata. If EPS file doesn't contain XMP metadata we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
    XmpMetadata xmp = document.getXmpMetadata();

    // Get "CreatorTool" value
    if (xmp.containsKey("xmp:CreatorTool"))
        System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
    
    // Get "CreateDate" value
    if (xmp.containsKey("xmp:CreateDate"))
        System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());

    // Get "Title" value
    if (xmp.containsKey("dc:title"))
        System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());

    // Get "format" value
    if (xmp.containsKey("dc:format"))
        System.out.println("Format: " + xmp.get("dc:format").toStringValue());

    // Get "creator" value
    if (xmp.containsKey("dc:creator"))
        System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
    
    // Get "MetadataDate" value
    if (xmp.containsKey("xmp:MetadataDate"))
        System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
    
    
    // Initialize output EPS file stream
    FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
    
    // Save document with new XMP metadata
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
See adding XMP metadata in [.NET](/page/net/xmp-metadata/add/) and [C++](/page/cpp/xmp-metadata/add/).
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