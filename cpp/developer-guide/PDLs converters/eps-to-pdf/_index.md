---
title: Convert EPS to PDF using C++
type: docs
weight: 20
url: /cpp/convert/eps-to-pdf/
description: EPS to PDF conversion functionality offered by Aspose.Page API solution for C++ is explained and illustrated with the code snippets here.
---

## Overview

This article explains how to **convert EPS to PDF using C++**. It covers the following topics.

- [C++ EPS to PDF](#cpp-eps-to-pdf)
- [C++ Convert EPS to PDF](#cpp-eps-to-pdf)
- [C++ PDF from EPS](#cpp-eps-to-pdf)
- [C++ How to Convert EPS to PDF Programmatically](#cpp-eps-to-pdf)
- [C++ Save EPS as PDF](#cpp-eps-to-pdf)
- [C++ Generate PDF from EPS](#cpp-eps-to-pdf)

**Also See**

- [C++ XPS to PDF](https://docs.aspose.com/page/cpp/convert/xps-to-pdf/)

## C++ EPS to PDF Conversion

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a> {{% /alert %}} 

Aspose.Page for C++ EPS to PDF converter allows to convert Encapsulated PostScript (EPS) file to PDF document on Windows and Linux.

<a name="cpp-eps-to-pdf"><strong>Steps: EPS to PDF Converter API Code in C++</strong></a>

It is necessary to do several steps in order to perform EPS to PDF conversion:

1. Initialize an input stream for input EPS file.
2. Initialize an output stream for output PDF document.
3. Create an instance of [PsDocument](https://reference.aspose.com/page/cpp/class/aspose.page.e_p_s.ps_document) from created earlier input stream.
4. Use [PdfSaveOptions](https://reference.aspose.com/page/cpp/class/aspose.page.e_p_s.device.pdf_save_options) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
5. Create an instance of [PdfDevice](https://reference.aspose.com/page/cpp/class/aspose.page.e_p_s.device.pdf_device) from created earlier output stream.
6. Save PostScript document as PDF with PDF save options.
7. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during conversion of EPS to PDF and saved in **Exceptions** list.

Following C++ code snippet shows how to **convert EPS to PDF document in C++**:

```C++
For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-C
// Initialize PDF output stream
System::SharedPtr<System::IO::FileStream> pdfStream = System::MakeObject<System::IO::FileStream>(outDir() + u"outputPDF_out.pdf", System::IO::FileMode::Create, System::IO::FileAccess::Write);
// Initialize PostScript input stream
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
See EPS to PDF conversion in [.Net](/page/net/convert/eps-to-pdf/) and [Java](/page/java/convert/eps-to-pdf/).
{{% /alert %}}

Let's consider [PdfSaveOptions](https://reference.aspose.com/page/cpp/class/aspose.page.e_p_s.device.pdf_save_options). Using this class we can assign different conversion parameters while converting EPS to PDF.
<br>
- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.
- **SuppressError** controls behaviour of EPS to PDF converter when non-critical errors are appeared. If value is true than it is possible to view a list of such errors after conversion in **Exceptions** field. Default value is true.
- **Debug** allows outputting debug information to console. Default value is false.

{{% alert color="primary" %}}
Evaluate EPS to PDF conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/eps-to-pdf">EPS to PDF Converter</a>. You can convert several EPS files to PDF at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-C). {{% /alert %}} 
