---
title: Add XMP metadata to EPS file using C++
type: docs
weight: 13
url: /cpp/xmp-metadata/add/
---

<!--
{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a> {{% /alert %}}
-->

In order to add XMP metadata to EPS file it is necessary to do several steps:
1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.ps_document) from created earlier input stream.
3. Get an instance of [XmpMetadata](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.x_m_p.xmp_metadata) from the PsDocument. If given EPS file doesn't contain XMP metadata the new one
will be created, filled in with values from PS metadata comments and returned to you.
4. Now you can view values of metadata fileds.
5. Initialize an output stream for output EPS file.
6. Save EPS file with new XMP metadata.

<br>Following code snippet shows how to add XMP metadata to EPS file in C++:
<br>
```C++
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-C
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithXMPMetadataInEPS();
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            

try
{
    // Get XMP metadata. If EPS file doesn't contain XMP metadata we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
    XmpMetadata xmp = document.GetXmpMetadata();

    // Check metadata values extracted from PS metadata comments and set up in new XMP metadata

    // Get "CreatorTool" value
    if (xmp.Contains("xmp:CreatorTool"))
        Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());

    // Get "CreateDate" value
    if (xmp.Contains("xmp:CreateDate"))
        Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());

    // Get "format" value
    if (xmp.Contains("dc:format"))
        Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());

    // Get "title" value
    if (xmp.Contains("dc:title"))
        Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());

    // Get "creator" value
    if (xmp.Contains("dc:creator"))
        Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());

    // Get "MetadataDate" value
    if (xmp.Contains("xmp:MetadataDate"))
        Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());

    // Save EPS file with new XMP metadata
    
    // Create ouput stream
    using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
    {
        // Save EPS file
        document.Save(outPsStream);
    }

}
finally
{
    psStream.Close();
}
```
{{% alert color="primary" %}}
See adding XMP metadata in [Java](/page/java/xmp-metadata/add/) and [.NET](/page/net/xmp-metadata/add/).
{{% /alert %}}

<!--
{{% alert color="primary" %}}
Evaluate EPS to PDF conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a>. You can convert several EPS files to PDF at once and dowload results in a few seconds.
 {{% /alert %}}
-->
<br>
<br>
{{% alert color="primary" %}}
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-C). {{% /alert %}}