---
title: Get XMP metadata from EPS file using C++
type: docs
weight: 12
url: /cpp/xmp-metadata/get/
---

<!--
{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a> {{% /alert %}}
-->

In order to extract XMP metadata from EPS file it is necessary to do several steps:
1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.ps_document) from created earlier input stream.
3. Get an instance of [XmpMetadata](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.x_m_p.xmp_metadata) from the PsDocument. If given EPS file doesn't contain XMP metadata the new one
will be created, filled in with values from PS metadata comments and returned to you.
4. Now you can view values of  metadata fields.

<br>Following code snippet shows how to extract XMP metadata from EPS file in C++:
<br>
```C++
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-C
// The path to the documents directory.
System::String dataDir = RunExamples::GetDataDir_WorkingWithXMPMetadataInEPS();
// Initialize EPS file input stream
System::SharedPtr<System::IO::FileStream> psStream = System::MakeObject<System::IO::FileStream>(dataDir + u"get_input.eps", System::IO::FileMode::Open, System::IO::FileAccess::Read);
// Create PsDocument instance from stream
System::SharedPtr<PsDocument> document = System::MakeObject<PsDocument>(psStream);


{
    auto __finally_guard_0 = ::System::MakeScopeGuard([&psStream]()
    {
        psStream->Close();
    });
    
    try
    {
        // Get XMP metadata. If EPS file doesn't contain XMP metadata we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
        System::SharedPtr<XmpMetadata> xmp = document->GetXmpMetadata();
        
        // Get "CreatorTool" value
        if (xmp->Contains(u"xmp:CreatorTool"))
        {
            System::Console::WriteLine(System::String(u"CreatorTool: ") + xmp->idx_get(u"xmp:CreatorTool")->ToStringValue());
        }
        
        // Get "CreateDate" value
        if (xmp->Contains(u"xmp:CreateDate"))
        {
            System::Console::WriteLine(System::String(u"CreateDate: ") + xmp->idx_get(u"xmp:CreateDate")->ToStringValue());
        }
        
        // Get a width of a thumbnail image if exists
        if (xmp->Contains(u"xmp:Thumbnails") && xmp->idx_get(u"xmp:Thumbnails")->get_IsArray())
        {
            System::SharedPtr<XmpValue> val = xmp->idx_get(u"xmp:Thumbnails")->ToArray()->idx_get(0);
            if (val->get_IsNamedValues() && val->ToDictionary()->ContainsKey(u"xmpGImg:width"))
            {
                System::Console::WriteLine(System::String(u"Thumbnail Width: ") + val->ToDictionary()->idx_get(u"xmpGImg:width")->ToInteger());
            }
        }
        
        // Get "format" value
        if (xmp->Contains(u"dc:format"))
        {
            System::Console::WriteLine(System::String(u"Format: ") + xmp->idx_get(u"dc:format")->ToStringValue());
        }
        
        // Get "DocumentID" value
        if (xmp->Contains(u"xmpMM:DocumentID"))
        {
            System::Console::WriteLine(System::String(u"DocumentID: ") + xmp->idx_get(u"xmpMM:DocumentID")->ToStringValue());
        }
        
    }
    catch (...)
    {
        throw;
    }
}
```
{{% alert color="primary" %}}
See extracting XMP metadata in [Java](/page/java/xmp-metadata/get/) and [.NET](/page/net/xmp-metadata/get/).
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