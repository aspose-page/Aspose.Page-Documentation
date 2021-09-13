---
title: Convert XPS to BMP
type: docs
weight: 20
url: /cpp/convert/xps-to-bmp/
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page XPS to BMP conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/xps-to-bmp">XPS to BMP Converter</a>
or <a nofollow href="https://products.aspose.app/page/viewer/xps">XPS Viewer</a> {{% /alert %}}

Aspose.Page C++ XPS to BMP converter allows to convert XPS document to BMP image on Windows and Linux.
<br>It is necessary to do several steps in order to perform XPS to BMP conversion:
1. Initialize an input stream for input XPS document.
2. Create an instance of [XpsDocument](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.xps_document) from created earlier input stream.
4. Specify **SmoothingMode**, **Resolution** and other options of [BmpSaveOptions](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.presentation.image.bmp_save_options).
5. Create an instance of [ImageDevice](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.presentation.image.image_device).
6. Save XPS document as image with BMP save options to an array of arrays of bytes. One array of bytes for one page of input document.
7. Save resulting 2-dimensional arrays of bytes to BMP files creating for every bytes array a new file output stream.

<br>Following code snippet shows how to convert XPS to BMP files in C++:
<br>
```C++
For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-C
// Input file
System::String inputFileName = dataDir() + u"input.xps";
//Outut file 
System::String outputFileName = outDir() + u"XPStoImage_out.bmp";
// Initialize XPS input stream
{
	System::SharedPtr<System::IO::Stream> xpsStream = System::IO::File::Open(inputFileName, System::IO::FileMode::Open, System::IO::FileAccess::Read);
	// Clearing resources under 'using' statement
	System::Details::DisposeGuard<1> __dispose_guard_1({ xpsStream });
	// ------------------------------------------

	try
	{
		// Load XPS document form the stream
		System::SharedPtr<XpsDocument> document = System::MakeObject<XpsDocument>(xpsStream, System::MakeObject<XpsLoadOptions>());
		// or load XPS document directly from file. No xpsStream is needed then.
		// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());

		// Initialize options object with necessary parameters.
		System::SharedPtr<BmpSaveOptions> options = [&] { auto tmp_0 = System::MakeObject<BmpSaveOptions>(); tmp_0->set_SmoothingMode(System::Drawing::Drawing2D::SmoothingMode::HighQuality); tmp_0->set_Resolution(300); tmp_0->set_PageNumbers(System::MakeArray<int32_t>({ 1, 2, 6 })); return tmp_0; }();

		// Create rendering device for PDF format
		System::SharedPtr<ImageDevice> device = System::MakeObject<ImageDevice>();

		document->Save(device, options);

		// Iterate through document partitions (fixed documents, in XPS terms)
		for (int32_t i = 0; i < device->get_Result()->get_Length(); i++)
		{
			for (int32_t j = 0; j < device->get_Result()[i]->get_Length(); j++)
			{
				// Initialize image output stream
				{
					System::String str = System::IO::Path::GetDirectoryName(outputFileName) + u"\\" + System::IO::Path::GetFileNameWithoutExtension(outputFileName) + u"_" + (i + 1) + u"_" + (j + 1) + System::IO::Path::GetExtension(outputFileName);
					System::SharedPtr<System::IO::Stream> imageStream = System::IO::File::Open(str, System::IO::FileMode::Create, System::IO::FileAccess::Write);
					// Clearing resources under 'using' statement
					System::Details::DisposeGuard<1> __dispose_guard_0({ imageStream });
					// ------------------------------------------

					try
					{
						imageStream->Write(device->get_Result()[i][j], 0, device->get_Result()[i][j]->get_Length());
					}
					catch (...)
					{
						__dispose_guard_0.SetCurrentException(std::current_exception());
					}
				}
			}
		}
	}
	catch (...)
	{
		__dispose_guard_1.SetCurrentException(std::current_exception());
	}
}
```
{{% alert color="primary" %}}
See XPS to BMP conversion in [.Net](/page/net/convert/xps-to-bmp/) and [Java](/page/java/convert/xps-to-bmp/).
{{% /alert %}}

Let's consider [BmpSaveOptions](https://apireference.aspose.com/page/cpp/class/aspose.page.x_p_s.presentation.image.bmp_save_options). Using this class we can assign different conversion parameters while converting XPS to BMP.
<br>
- **SmoothingMode** assigns a degree of smoothing for lines, curves and edges of filled areas, may be AntiAlias, HighQuality, HighSpeed and Default (none). Default value is HighQuality.
- **Resolution** controls resolution of resulting image. Default value is 96.
- **TextRenderingHint** assigns quality of text rendering, may be AntiAlias, AntiAliasGridFit, ClearTypeGridFit, SingleBitPerPixel, SingleBitPerPixelGridFit, SystemDefault. Default value in XPS to BMP conversion is AntiAliasGridFit.
- **InterpolationMode** defines algorithm that is used when scaling or/and rotating image, may be Bicubic, Bilinear, High, HighQualityBicubic, HighQualityBilinear, Low, NearestNeighbor and Default. Default value is HighQualityBicubic.
- **PageNumbers** represents an array of numbers of pages which will be saved to BMP.

{{% alert color="primary" %}} 
Evaluate XPS to BMP conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/xps-to-bmp">XPS to BMP Converter</a>. You can convert several XPS files to BMP at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-C). {{% /alert %}} 
