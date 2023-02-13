---
title: Add array items in XMP metadata of EPS| C++
type: docs
weight: 17
url: /cpp/xmp-metadata/add-array-items/
description: The process of adding items in XMP metadata of EPS  with Aspose.Page for C++ is explained and illustrated with the code snippets here.
---

<!--
{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a> {{% /alert %}}
-->

In order to add array items in XMP metadata of EPS file it is necessary to do several steps:
1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://reference.aspose.com/page/cpp/class/aspose.page.e_p_s.ps_document) from created earlier input stream.
3. Get an instance of [XmpMetadata](https://reference.aspose.com/page/cpp/class/aspose.page.e_p_s.x_m_p.xmp_metadata) from the PsDocument. If given EPS file doesn't contain XMP metadata the new one
will be created, filled in with values from PS metadata comments and returned to you.
4. Now you can add items to array metadata fields.
5. Initialize an output stream for output EPS file.
6. Save EPS file with changed XMP metadata.

<br>Following code snippet shows how to add array items in XMP metadata in EPS file in C++:
<br>
```C++
// For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-C
// The path to the documents directory.
System::String dataDir = RunExamples::GetDataDir_WorkingWithXMPMetadataInEPS();
// Initialize EPS file input stream
System::SharedPtr<System::IO::FileStream> psStream = System::MakeObject<System::IO::FileStream>(dataDir + u"add_simple_props_input.eps", System::IO::FileMode::Open, System::IO::FileAccess::Read);
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
        
        //Change XMP metadata values
        
        // Add one more title. I will be added at the end of array by default.
        xmp->AddArrayItem(u"dc:title", System::MakeObject<XmpValue>(u"NewTitle"));
        
        // Add one more creator. It will be added in the array by an index (0).
        xmp->AddArrayItem(u"dc:creator", 0, System::MakeObject<XmpValue>(u"NewCreator"));
        
        // Save EPS file with changed XMP metadata
        
        // Create ouput stream
        System::SharedPtr<System::IO::FileStream> outPsStream = System::MakeObject<System::IO::FileStream>(RunExamples::GetOutDir() + u"add_array_items_output.eps", System::IO::FileMode::Create, System::IO::FileAccess::Write);
        
        // Save EPS file
        
        {
            auto __finally_guard_1 = ::System::MakeScopeGuard([&outPsStream]()
            {
                outPsStream->Close();
            });
            
            try
            {
                document->Save(outPsStream);
                outPsStream->Flush();
            }
            catch (...)
            {
                throw;
            }
        }
        
    }
    catch (...)
    {
        throw;
    }
}
```
{{% alert color="primary" %}}
See adding array items in XMP metadata in [Java](/page/java/xmp-metadata/add-array-items/) and [.NET](/page/net/xmp-metadata/add-array-items/).
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