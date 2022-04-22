---
title: Change named value in XMP metadata of EPS file using .NET
type: docs
weight: 18
url: /net/xmp-metadata/change-named-value/
---

<!--
{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a> {{% /alert %}}
-->

In order to change named value in XMP metadata of EPS file it is necessary to do several steps:
1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://apireference.aspose.com/page/net/aspose.page.eps/psdocument) from created earlier input stream.
3. Get an instance of [XmpMetadata](https://apireference.aspose.com/page/net/aspose.page.eps.xmp/xmpmetadata) from the PsDocument. If given EPS file doesn't contain XMP metadata the new one
will be created, filled in with values from PS metadata comments and returned to you.
4. Now you can change named value of structure metadata fileds.
5. Initialize an output stream for output EPS file.
6. Save EPS file with changed XMP metadata.

<br>Following code snippet shows how to change named value in XMP metadata in EPS file in C#:
<br>
```C#
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-.NET
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_WorkingWithXMPMetadataInEPS();
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "change_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            

try
{
    // Get XMP metadata. If EPS file doesn't contain XMP metadata we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
    XmpMetadata xmp = document.GetXmpMetadata();

    //Change XMP metadata values

    // Change named value "stDim:unit" in "xmpTPg:MaxPageSize" structure.
    xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));

    // Add named value "stDim:newKey" in "xmpTPg:MaxPageSize" structure.
    xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));

    // Save EPS file with changed XMP metadata

    // Create ouput stream
    using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
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
See changing named value in XMP metadata in [Java](/page/java/xmp-metadata/change-named-value/) and [C++](/page/cpp/xmp-metadata/change-named-value/).
{{% /alert %}}

<!--
{{% alert color="primary" %}}
Evaluate EPS to PDF conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a>. You can convert several EPS files to PDF at once and dowload results in a few seconds.
 {{% /alert %}}
-->
<br>
<br>
{{% alert color="primary" %}}
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-.NET). {{% /alert %}}