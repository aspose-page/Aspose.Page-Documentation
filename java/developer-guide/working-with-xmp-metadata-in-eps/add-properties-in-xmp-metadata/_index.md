---
title: Add properties in XMP metadata of EPS file using Java
type: docs
weight: 15
url: /java/xmp-metadata/add-properties/
description: The process of adding properties in XMP metadata of EPS file with Aspose.Page for Java is explained and illustrated with the code snippets here.
---

<!--
{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a> {{% /alert %}}
-->

In order to add properties in XMP metadata of EPS file it is necessary to do several steps:
1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://apireference.aspose.com/page/java/com.aspose.eps/psdocument) from created earlier input stream.
3. Get an instance of [XmpMetadata](https://apireference.aspose.com/page/java/com.aspose.eps.xmp/xmpmetadata) from the PsDocument. If given EPS file doesn't contain XMP metadata the new one
will be created, filled in with values from PS metadata comments and returned to you.
4. Now you can add properties of metadata fileds.
5. Initialize an output stream for output EPS file.
6. Save EPS file with changed XMP metadata.

<br>Following code snippet shows how to add properties in XMP metadata of EPS file in Java:
<br>
```Java
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-Java
// Set license
new License().setLicense(BaseExamplesTest.LICENSE_PATH);

// The path to the documents directory.
String dataDir = Utils.getDataDir();

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);

try {
    // Get XMP metadata. If EPS file doesn't contain XMP metadata we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
    XmpMetadata xmp = document.getXmpMetadata();

    // Add date property "xmp:Date1" value
    TimeZone.setDefault( TimeZone.getTimeZone("UTC"));
    Date now = new Date();            
    xmp.put("xmp:Date1", new XmpValue(now));
    
    // Add integer property "xmp:Intg1" value
    xmp.put("xmp:Intg1", new XmpValue(111));
    
    // Add double property "xmp:Double1" value
    xmp.put("xmp:Double1", new XmpValue(111.11D));
    
    // Add string property "xmp:String1" value
    xmp.put("xmp:String1", new XmpValue("ABC"));
    
    
    // Initialize output EPS file stream
    FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
    
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
See adding properties in XMP metadata in [.NET](/page/net/xmp-metadata/add-properties/) and [C++](/page/cpp/xmp-metadata/add-properties/).
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