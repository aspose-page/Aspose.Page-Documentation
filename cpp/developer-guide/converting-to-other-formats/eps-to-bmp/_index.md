---
title: Convert EPS to BMP
type: docs
weight: 20
url: /cpp/convert/eps-to-bmp/
---

{{% alert color="primary" %}} 

You can check the quality of Aspose.Page EPS to BMP conversion and view the results via free online <a nofollow href="https://products.aspose.app/page/conversion/eps-to-bmp">EPS to BMP Converter</a>
or <a nofollow href="https://products.aspose.app/page/viewer/eps">EPS Viewer</a> {{% /alert %}}

Aspose.Page for C++ EPS to BMP converter allows to convert Encapsulated PostScript (EPS) file to BMP image on Windows and Linux.
<br>It is necessary to do several steps in order to perform EPS to BMP conversion:
1. Initialize an input stream for input EPS file.
2. Create an instance of [PsDocument](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.ps_document) from created earlier input stream.
4. Use [ImageSaveOptions](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.device.image_save_options) to specify **AdditionalFontsFolder** and **SuppressError** boolean value.
5. Create an instance of [ImageDevice](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.device.image_device) specifying image type and size if it is necessary.
6. Save PostScript document as image with image save options to an array of arrays of bytes. One array of bytes for one page of input document.
7. Save resulting 2-dimensional arrays of bytes to BMP files creating for every bytes array a new file output stream.
8. If **SuppressErrors** value was true, as it is by default, It is possible to see what errors were thrown during conversion of EPS to BMP.

<br>Following code snippet shows how to convert EPS to BMP files in C++:
<br>
```C++
For complete examples and data files, please go to https://github.com/aspose-page/Aspose.Page-for-C
// Specify image format
System::SharedPtr<System::Drawing::Imaging::ImageFormat> imageFormat = System::Drawing::Imaging::ImageFormat::get_Bmp();
// Initialize PostScript input stream
System::SharedPtr<System::IO::FileStream> psStream = System::MakeObject<System::IO::FileStream>(dataDir() + u"inputForImage.eps", System::IO::FileMode::Open, System::IO::FileAccess::Read);

System::SharedPtr<PsDocument> document = System::MakeObject<PsDocument>(psStream);

// If you want to convert Postscript file despite of minor errors set this flag
bool suppressErrors = true;

//Initialize options object with necessary parameters.
System::SharedPtr<ImageSaveOptions> options = System::MakeObject<ImageSaveOptions>(suppressErrors);

// If you want to add special folder where fonts are stored. Default fonts folder in OS is always included.
options->set_AdditionalFontsFolders(System::MakeArray<System::String>({ u"{FONT_FOLDER}" }));

// Default image size is 595x842 and it is not mandatory to set it in ImageDevice
System::SharedPtr<Aspose::Page::EPS::Device::ImageDevice> device = System::MakeObject<Aspose::Page::EPS::Device::ImageDevice>(imageFormat);
// But if you need to specify size use constructor with two parameters
//System::SharedPtr<Aspose::Page::EPS::Device::ImageDevice> device = System::MakeObject<Aspose::Page::EPS::Device::ImageDevice>(System::MakeObject<System::Drawing::Size>(595,842), imageFormat);

{
	auto __finally_guard_0 = ::System::MakeScopeGuard([&psStream]()
	{
		psStream->Close();
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

System::ArrayPtr<System::ArrayPtr<uint8_t>> imagesBytes = device->get_ImagesBytes();

int32_t i = 0;


{
	for (System::ArrayPtr<uint8_t> imageBytes : imagesBytes)
	{
		System::String imagePath = System::IO::Path::GetFullPath(outDir() + System::String(u"out_image") + System::Convert::ToString(i) + u"." + System::ObjectExt::ToString(imageFormat).ToLower());
		{
			System::SharedPtr<System::IO::FileStream> fs = System::MakeObject<System::IO::FileStream>(imagePath, System::IO::FileMode::Create, System::IO::FileAccess::Write);
			// Clearing resources under 'using' statement
			System::Details::DisposeGuard<1> __dispose_guard_1({ fs });
			// ------------------------------------------

			try
			{
				fs->Write(imageBytes, 0, imageBytes->get_Length());
			}
			catch (...)
			{
				__dispose_guard_1.SetCurrentException(std::current_exception());
			}
		}
		i++;
	}

}
```
{{% alert color="primary" %}}
See EPS to BMP conversion in [.Net](/page/net/convert/eps-to-bmp/) and [Java](/page/java/convert/eps-to-bmp/).
{{% /alert %}}

Let's consider [ImageSaveOptions](https://apireference.aspose.com/page/cpp/class/aspose.page.e_p_s.device.image_save_options). Using this class we can assign different conversion parameters while converting EPS to BMP.
<br>
- **AdditionalFontsFolder** specifies locations where to find fonts. System fonts folders are always included by default.
- **SuppressError** controls behaviour of EPS to BMP converter when non-critical errors are appeared. If value is true than it is possible to view a list of such errors after conversion in **Exceptions** field. Default value is true.
- **Debug** allows outputting debug information to console. Default value is false.

{{% alert color="primary" %}}
Evaluate EPS to BMP conversion online on our <a nofollow href="https://products.aspose.app/page/conversion/eps-to-bmp">EPS to BMP Converter</a>. You can convert several EPS files to BMP at once and dowload results in a few seconds.
<br>
<br>
You can download examples and data files from [GitHub](https://github.com/aspose-page/Aspose.Page-for-C). {{% /alert %}} 