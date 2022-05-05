---
title: What is EPS file?
type: docs
weight: 16
url: /net/what-is-eps-file/
keywords: what is eps file, eps what is it, what is encapsulated postscript, eps file, eps format, encapsulated postscript file, encapsulated postscript format
description: Encapsulated PostScript or EPS described in this article, in short, is one of the Page Description Languages, dynamic one if to be more specific.
lastmod: "2022-02-18"
sitemap:
    changefreq: "weekly"
    priority: 0.8
---

## Introduction

Encapsulated PostScript is one of the [Page Description Languages](/net/page-description-languages/), dynamic one if to be more specific.
In this article, you will find information about this language and EPS files, their structure, and specific features. 
Here we also tried to answer the most asked users' questions, from our experience gained when working on the Aspose.Page solution.

## What is EPS file?

EPS or abbreviated Encapsulated PostScript file is a [PostScript language file](/net/what-is-ps-file/) that contains the description of only one page and is intended for 
embedding (encapsulating) one PostScript file into another one.

</br></br></br>
<p align="center">
	<img src="EPS intro.png">
</p>
</br></br></br>

As encapsulated page description must not break page description of arbitrary PS file, where the encapsulated file is embedded, it has to meet 
some requirements. These requirements are realized by adding special, so-called "structural", comments, represented by lines beginning
with "%%" symbols sequence. At least two such comments are always necessary for any EPS file. They are:

<p align="center">
	<img src="EPS main comments.png">
</p>
where:
</br><b>llx</b>, <b>lly</b> - coordinates of the lower-left corner and
</br><b>urx</b>, <b>ury</b> - coordinates of the upper-right corner of the bounding box.
</br></br>

Also, there are structural comments that are required conditionally. For example, an EPS file that uses operators of PostScript 3 and doesn't have 
an implementation in PostScript 2 operators and printed on a printer with PostScript 2 should note that it is used version 3.
If the EPS file uses some extensions of PostScript it should implicitly let the printer or application know about it. The same is related to
fonts and other resources, such as files, patterns, procsets (procedures), gradients, that are used but not embedded in this file.

<p align="center">
<table>
<tr>
<td >
<p align="left"><b><u>Examples of conditionally required structural comments</u></b></p>
<img width=800/>
<p align="left">
<b>%%LanguageLevel:</b> 2
</br>
<b>%%Extensions:</b> CMYK
</br>
<b>%%DocumentNeededFonts:</b> Times-Roman Times-Italic
</br>
<b>%%DocumentNeededResources:</b> procset Adobe_packedarray 0 0
</br>
<b>%%DocumentNeededFiles:</b> /usr/smith/myfile.epsf
</br>
<b>%%DocumentNeededProcSets:</b> Adobe_MDX
</br>
</p>
</td>
</tr>
</table>
</p>  

Non-observance of EPS requirements can result in erasing target PS file page description while printing or terminate printer job at all.

Besides of required structural comments Adobe recommends including such comments as:
<p align="center">
<table>
<tr>
<td>
<img width=800/>
<p align="left">
<b>%%Creator:</b> J. Smith
</br>
<b>%%Title:</b> (DRAWING.EPS)
</br>
<b>%%CreationDate:</b> February 18, 2022
</br>
</p>
</td>
</tr>
</table>
</p>

Another feature of EPS files, though optional, is the possibility to preview them as an image in the target application. For this purpose, 
EPS uses  %%BeginPreview and %%EndPreview structural comments. The preview image can be represented in Mac PICT or TIFF formats or 
device-independent hexadecimal bitmap. The example of the hex bitmap preview section in the EPS file is shown below.

</br>
<p align="center" style="margin-bottom: 0px;">
	<img src="EPS preview.png">
</p>
where:
</br><b>256</b> - width of the preview image;
</br><b>186</b> - height of the preview image;
</br><b>1</b>&nbsp;&nbsp;&nbsp;&nbsp; - depth (in bits per pixels) of the preview image;
</br><b>186</b> - a number of lines.
</br></br>

An EPS file can contain preview binary image data in Windows Metafile or TIFF format without %%BeginPreview and %%BeginPreview comments.
In this case information about it is contained in a binary header at the very beginning of the file.
It is a sort of EPS file content. In this binary header among other things offset and a length in bytes of binary data are contained.
Often binary image data goes already after page description, after %%EOF (end of file) structural comment.


</br>
<p align="center">
	<img src="EPS binary.png">
</p>
</br>

## Typical structure of EPS files

</br>
<p align="center" style="margin-bottom: 0px;">
	<img src="EPS example.png">
</p>

## What format is an EPS file?

An EPS file is an ASCII-encoded text file that contains PostScript operators and structural comments allowing embedding an EPS file into another 
PostScript file. At this time some binary data can be contained in an EPS file. It can be a 28-bytes length binary header and preview image data 
in Windows Metafile or TIFF formats.


## How do I open EPS files?

EPS files can be opened with standalone Adobe's applications: Acrobat Distiller, Illustrator, Photoshop, or with Apple Preview.
If someone wants just to open to view or demonstrate EPS files they can do it easily and fast 
with [Aspose.Page Viewer](https://products.aspose.app/page/viewer/eps) web application.

## Can I convert an EPS file to JPG?

The quickest way to convert EPS files to JPG is to use
[Aspose.Page Conversion](https://products.aspose.app/page/conversion/eps) web application. Aspose EPS converter supports EPS to PDF, DOC, DOCX, HTML,
TEX, SVG, PNG, JPG, TIFF, BMP, EMF, WMF conversions.
If you are a developer and want to use our library for such conversions, learn [PDLs converters](/page/net/convert/) article 
to find the illustrated with code snippets examples on how to do the conversion.

## Is an EPS file the same as a PDF one?

EPS and PDF files can be compared only if the PDF file has only one page because the EPS file is always one-paged. And even in this case, these 
files are quite different, because PDF is static PDL while PostScript is dynamic PDL. After reading this article you have already known that any 
EPS file is a one-paged PostScript file with required structural comments. There are also a few limitations in a set of used operators, those which 
manage print jobs. But in the rest, EPS files are PS files where page description is created on the fly using procedures, variables, control execution 
operators. At this time PDF always contains static page description. 
See [Introduction to Page Description Languages](/page/net/page-description-languages) article.


## How do I open an EPS file in PowerPoint?

It is not possible to insert an EPS file into a PowerPoint presentation directly. Instead, you can convert the EPS file to one of three 
image formats: PNG, JPG, EMF supported by the program. 
For this, go to [Aspose.Page Conversion](https://products.aspose.app/page/conversion/eps) web application and then you will be able to insert 
the resulting image into the presentation.


## Are EPS files obsolete?

Actually, no. EPS is still used by designers in high-quality polygraphy.

## Can I use EPS files in Canva?

As with PowerPoint, EPS files should be converted to PNG, JPG, or EMF image format 
with a [Converter](https://products.aspose.app/page/conversion/eps) web application, and then the result can be inserted in Canva.

## Do EPS files have DPI?

No, because EPS is not a raster image. Resolution can be defined via printer properties while printing.

## Conclusion

The purpose of this article was to teach you about EPS files from our experience. 
Now we have already have and can offer you a kit of [cross-platform solutions to manage EPS files](https://products.aspose.app/page/applications) 
and [.NET](https://docs.aspose.com/page/net/), [Java](https://docs.aspose.com/page/java/), and [C++](https://docs.aspose.com/page/cpp/) API solutions 
so you can manage the files programmatically.
