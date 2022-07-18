---
title: Get XMP metadata from EPS file using .NET
type: docs
weight: 12
url: /net/xmp-metadata/get/
description: The process of getting XMP metadata from EPS file with Aspose.Page API solution for .NET is explained and illustrated with the code here.
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page XMP Metadata working with <a nofollow href="https://products.aspose.app/page/metadata/eps">Metadata</a> web app. {{% /alert %}}

In order to extract XMP metadata from EPS file it is necessary to do several steps:
1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://reference.aspose.com/page/net/aspose.page.eps/psdocument) from created earlier input stream.
3. Get an instance of [XmpMetadata](https://reference.aspose.com/page/net/aspose.page.eps.xmp/xmpmetadata) from the PsDocument. If given EPS file doesn't contain XMP metadata the new one
will be created, filled in with values from PS metadata comments and returned to you.
4. Now you can view values of  metadata fields.

<br>Following code snippet shows how to extract XMP metadata from EPS file in C#:
<br>
```C#
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-.NET
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithXMPMetadataInEPS();
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            

try
{
    // Get XMP metadata. If EPS file doesn't contain XMP metadata we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
    XmpMetadata xmp = document.GetXmpMetadata();

    // Get "CreatorTool" value
    if (xmp.Contains("xmp:CreatorTool"))
        Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
    
    // Get "CreateDate" value
    if (xmp.Contains("xmp:CreateDate"))
        Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());

    // Get a width of a thumbnail image if exists
    if (xmp.Contains("xmp:Thumbnails") && xmp["xmp:Thumbnails"].IsArray)
    {
        XmpValue val = xmp["xmp:Thumbnails"].ToArray()[0];
        if (val.IsNamedValues && val.ToDictionary().ContainsKey("xmpGImg:width"))
            Console.WriteLine("Thumbnail Width: " + val.ToDictionary()["xmpGImg:width"].ToInteger());
    }

    // Get "format" value
    if (xmp.Contains("dc:format"))
        Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());

    // Get "DocumentID" value
    if (xmp.Contains("xmpMM:DocumentID"))
        Console.WriteLine("DocumentID: " + xmp["xmpMM:DocumentID"].ToStringValue());

}
finally
{
    psStream.Close();
}
```
{{% alert color="primary" %}}
See extracting XMP metadata in [Java](/page/java/xmp-metadata/get/) and [C++](/page/cpp/xmp-metadata/get/).
{{% /alert %}}

{{% alert color="primary" %}}
Evaluate XMP metadata working online on our <a nofollow href="https://products.aspose.app/page/metadata/eps">Metadata</a> application.
 {{% /alert %}}
 
{{% alert color="primary" %}}
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}}