---
title: Get XMP metadata from EPS file using Java
type: docs
weight: 12
url: /java/xmp-metadata/get/
description: The process of getting XMP metadata from EPS file with Aspose.Page API solution for Java is explained and illustrated with the code here.
---

<!--
{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a> {{% /alert %}}
-->

In order to extract XMP metadata from EPS file it is necessary to do several steps:
1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://apireference.aspose.com/page/java/com.aspose.eps/psdocument) from created earlier input stream.
3. Get an instance of [XmpMetadata](https://apireference.aspose.com/page/java/com.aspose.eps.xmp/xmpmetadata) from the PsDocument. If given EPS file doesn't contain XMP metadata the new one
will be created, filled in with values from PS metadata comments and returned to you.
4. Now you can view values of  metadata fileds.

<br>Following code snippet shows how to extract XMP metadata from EPS file in Java:
<br>
```Java
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-Java    	
// Set license
new License().setLicense(BaseExamplesTest.LICENSE_PATH);

// The path to the documents directory.
String dataDir = Utils.getDataDir();

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");

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

    // Get a width of a thumbnail image if exists
    if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
        XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
        if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
            System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
    }

    // Get "format" value
    if (xmp.containsKey("dc:format"))
        System.out.println("Format: " + xmp.get("dc:format").toStringValue());

    // Get "DocumentID" value
    if (xmp.containsKey("xmpMM:DocumentID"))
        System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());

} finally {
    // close input EPS stream
	psStream.close();
}
```
{{% alert color="primary" %}}
See extracting XMP metadata in [.NET](/page/net/xmp-metadata/get/) and [C++](/page/cpp/xmp-metadata/get/).
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