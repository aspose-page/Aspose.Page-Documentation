---
title: Convert XPS to PDF
type: docs
weight: 20
url: /cpp/convert/xps-to-pdf/
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page XPS to PDF conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/xps-to-pdf">XPS to PDF Converter</a> {{% /alert %}} 

Aspose.Page C++ XPS to PDF converter allows to convert XPS document to PDF document on Windows and Linux.
<br>It is necessary to do several steps in order to perform XPS to PDF conversion:
1. Initialize an output stream for output PDF document.
2. Initialize an input stream for input XPS document.
3. Create an instance of [XpsDocument](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_document) from created earlier input stream.
4. Specify **TextCompression**, **ImageCompression**, **JpegQualityLevel**, and other options of [PdfSaveOptions](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.presentation.pdf.pdf_save_options).
5. Create an instance of [PdfDevice](https://apireference.aspose.com/page/cpp/aspose.page.xps.presentation.pdf/pdfdevice) from created earlier output stream.
6. Save XPS document as PDF with PDF save options. 

<br>Following code snippet shows how to convert XPS to PDF document in C++:
<br>
```C++
//For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-C
// Input file
System::SharedPtr<System::IO::Stream> pdfStream = System::IO::File::Open(RunExamples::outDir() + u"XPStoPDF.pdf", System::IO::FileMode::Create, System::IO::FileAccess::Write);
// Clearing resources under 'using' statement
System::Details::DisposeGuard<1> __dispose_guard_1({ pdfStream });
// ------------------------------------------
try {
	System::SharedPtr<System::IO::Stream> xpsStream = System::IO::File::Open(RunExamples::dataDir() + u"input.xps", System::IO::FileMode::Open, System::IO::FileAccess::Read);
	// Clearing resources under 'using' statement
	System::Details::DisposeGuard<1> __dispose_guard_0({ xpsStream });
	// ------------------------------------------

	try
	{
		// Load XPS document form the stream
		System::SharedPtr<XpsDocument> document = System::MakeObject<XpsDocument>(xpsStream, System::MakeObject<XpsLoadOptions>());
		// or load XPS document directly from file. No xpsStream is needed then.
		// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());

		// Initialize options object with necessary parameters.
		System::SharedPtr<Aspose::Page::Xps::Presentation::Pdf::PdfSaveOptions> options = [&] { auto tmp_0 = System::MakeObject<Aspose::Page::Xps::Presentation::Pdf::PdfSaveOptions>(); tmp_0->set_JpegQualityLevel(100); tmp_0->set_ImageCompression(Aspose::Page::Xps::Presentation::Pdf::PdfImageCompression::Jpeg); tmp_0->set_TextCompression(Aspose::Page::Xps::Presentation::Pdf::PdfTextCompression::Flate); tmp_0->set_PageNumbers(System::MakeArray<int32_t>({ 1, 2, 6 })); return tmp_0; }();

		// Create rendering device for PDF format
		System::SharedPtr<Aspose::Page::Xps::Presentation::Pdf::PdfDevice> device = System::MakeObject<Aspose::Page::Xps::Presentation::Pdf::PdfDevice>(pdfStream);

		document->Save(device, options);
	}
	catch (...)
	{
		__dispose_guard_0.SetCurrentException(std::current_exception());
	}
}
catch (...)
{
	__dispose_guard_1.SetCurrentException(std::current_exception());
}
```
{{% alert color="primary" %}}
See XPS to PDF conversion in [.Net](/page/net/convert/xps-to-pdf/) and [Java](/page/java/convert/xps-to-pdf/).
{{% /alert %}}

Let's consider [PdfSaveOptions](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.presentation.pdf.pdf_device). Using this class we can assign different conversion parameters while converting XPS to PDF.
<br>
- **JpegQualityLevel** controls a quality of images in PDF document if **ImageCompression** algorithm is JPEG and can be from 0 to 100.
- **ImageCompression** algorithm encapsulated in [PdfImageCompression](https://apireference.aspose.com/page/cpp/namespace/aspose.page.x_p_s.presentation.pdf#ab2200bafd8809e7ff3bf07043d5af4ca) Enumeration, may be Run Length Encoding (RLE), Flate, Lempel-Ziv-Welch (LZW) with base or optimized pedictor, JPEG , none (raw image bytes) and auto (the most appropriate compression for each image). Default is auto compression.
- **TextCompression** algorithm encapsulated in [PdfTextCompression](https://apireference.aspose.com/page/cpp/namespace/aspose.page.x_p_s.presentation.pdf#ad0737945642d29436c5880622affebf7) Enumeration, may be Run Length Encoding (RLE), Flate, Lempel-Ziv-Welch (LZW) and none. Default value in XPS to PDF conversion is Flate.
- **EncryptionDetails** encapsulated in [PdfEncryptionDetails](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.presentation.pdf.pdf_encryption_details). It allows setting encryption algorithm, permisions, owner and user passwords for PDF document.
- **PageNumbers** represents an array of numbers of pages which will be saved to PDF.
- **OutlineTreeExpansionLevel** and **OutlineTreeHeight** controls view of document outline.

{{% alert color="primary" %}}
Evaluate XPS to PDF conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/xps-to-pdf">XPS to PDF Converter</a>. You can convert several XPS files to PDF at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-C). {{% /alert %}} 