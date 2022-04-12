---
title: Merge EPS files to PDF using C++
type: docs
weight: 20
url: /cpp/merge/eps/
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS merging and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS Merger</a> {{% /alert %}} 

Aspose.Page for C++ EPS merger allows to merge Encapsulated PostScript (EPS) files to PDF document on Windows and Linux.
<br>It is necessary to do several steps in order to perform EPS to PDF merge:
1. Initialize an input stream for the first input EPS file.
2. Initialize an output stream for output PDF document.
3. Create an array of EPS files that will be merged with the first one.
4. Create an instance of [PsDocument](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.ps_document) from created earlier input stream.
5. Use [PdfSaveOptions](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.device.pdf_save_options) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
6. Create an instance of [PdfDevice](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.device.pdf_device) from created earlier output stream.
7. Save EPS document as PDF with PDF save options.
8. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during merging of EPS to PDF and saved in **Exceptions** list.

<br>Following code snippet shows how to merge EPS files to PDF document in C++:
<br>
```C++
For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-C
// Initialize PDF output stream
System::SharedPtr<System::IO::FileStream> pdfStream = System::MakeObject<System::IO::FileStream>(outDir() + u"outputPDF_out.pdf", System::IO::FileMode::Create, System::IO::FileAccess::Write);
// Initialize EPS input stream
System::SharedPtr<System::IO::FileStream> psStream = System::MakeObject<System::IO::FileStream>(dataDir() + u"input.eps", System::IO::FileMode::Open, System::IO::FileAccess::Read);
System::SharedPtr<PsDocument> document = System::MakeObject<PsDocument>(psStream);

// If you want to convert Postscript file despite of minor errors set this flag
bool suppressErrors = true;

//Initialize options object with necessary parameters.
System::SharedPtr<PdfSaveOptions> options = System::MakeObject<PdfSaveOptions>(suppressErrors);
// If you want to add special folder where fonts are stored. Default fonts folder in OS is always included.
options->set_AdditionalFontsFolders(System::MakeArray<System::String>({ u"{FONT_FOLDER}" }));

// Default page size is 595x842 and it is not mandatory to set it in PdfDevice
System::SharedPtr<Aspose::Page::EPS::Device::PdfDevice> device = System::MakeObject<Aspose::Page::EPS::Device::PdfDevice>(pdfStream);
// But if you need to specify size and image format use following line
//Aspose.Page.EPS.Device.PdfDevice device = new Aspose.Page.EPS.Device.PdfDevice(pdfStream, new System.Drawing.Size(595, 842));


{
	auto __finally_guard_0 = ::System::MakeScopeGuard([&psStream, &pdfStream]()
	{
		psStream->Close();
		pdfStream->Close();
	});

	try
	{
		document->Save(device, options);
	}
	catch (...)
	{
		throw;
	}
}
```
{{% alert color="primary" %}}
See EPS merge in [.Net](/page/net/merge/eps/) and [Java](/page/java/merge/eps/).
{{% /alert %}}

Let's consider [PdfSaveOptions](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.device.pdf_save_options). Using this class we can assign different conversion parameters while merging EPS to PDF.
<br>
- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.
- **SuppressError** controls behaviour of EPS to PDF merger when non-critical errors are appeared. If value is true than it is possible to view a list of such errors after merging in **Exceptions** field. Default value is true.
- **Debug** allows outputting debug information to console. Default value is false.

{{% alert color="primary" %}}
Evaluate EPS merging online on our <a nofollow href="https://products.aspose.app/page/merge/eps">EPS Merger</a>.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-C). {{% /alert %}} 