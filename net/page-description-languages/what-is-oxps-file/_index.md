---
title: What is OXPS file?
type: docs
weight: 18
url: /net/what-is-oxps-file/
keywords: what is oxps file, oxps what is it, oxps file, oxps format, what is openxps, openxps file
description: OXPS files are often considered to be the same as XPS files. There are differences between these two formats though. Both formats are covered by our solution along with EPS and PS."
lastmod: "2022-02-11"
sitemap:
    changefreq: "weekly"
    priority: 0.8
---

## Introduction

From the article about [XPS](/page/net/what-is-xps-file/) you have got familiar with XPS files. You've learned that XPS is one of the static PDLs with a fixed layout. 
XPS file is internally represented by a ZIP archive containing one or more documents, in the traditional meaning of this word, and all the necessary resources for 
these documents. All internal parts of the archive are either text files written in XML-based language or binary resources, such as OpenType fonts or images. 
The article here is going to provide you with information about the differences between XPS and OXPS formats and describe OXPS files.


## What is OXPS file?
OXPS or OpenXPS or Open XML Paper Specification is an XPS that was raised in 2009 to international standard (ECMA-388) and was renamed to separate the previous specification 
that is not a standard from the new specification that is a standard. We can assume that the standardization of XPS and adding of the word "Open" to the name were made by Microsoft 
in order to encourage corporate users of electronic documents to extend XPS for their needs and, thus, to increase the number of XPS users. Such an assumption is easy to accept 
bearing in mind that XPS is much less popular than PDF, an alternative to which XPS was intended initially. 
Though Microsoft claims OpenXPS is open for extensions, it is worth saying that yet earlier, before 2009, XPS (not OXPS) clearly implies extensions of the specification.

A possible reason for raising XPS to international standard can be initial XPS formally didn't guarantee conformance between producers and consumers of extended XPS documents. 
Thus, actually, in most cases, an OXPS file is an XPS one, and the difference between them is formal. The only feature that was added to OXPS is the possibility to add 3D content.

## Comparison of XPS and OXPS files

Let's compare internal files of XPS and OXPS packages. For this purpose we take a 1-page document "jagged.xps" containing a simple drawing, open it with the standard Windows XPS Viewer

</br>
<p align="center">
	<img src="OXPS jagged.png">
</p>
</br>

and print it with Microsoft XPS Document Writer to OXPS file.

Now we have XPS and OXPS files having visually the same content. And now we can compare internal parts of packages.

### FixedDocumentSequense.fdseq

</br>
<p align="center">
	<img src="OXPS fdseq diff.png">
</p>

### [Content_Type].xml

</br>
<p align="center">
	<img src="OXPS content-type diff.png">
</p>

### FixedDocument.fdoc

</br>
<p align="center">
	<img src="OXPS fdoc diff.png">
</p>

### 1.fpage (Fixed page)

</br>
<p align="center">
	<img src="OXPS fpage diff.png">
</p>
</br>

As we can see in FixedDocumentSequense.fdseq, [Content_Types].xml and FixedDocument.fdoc only XML namespace schema is changed, that was expected,

<p style="background: Ivory; padding: 10px;">
<b>xmlns="http://schemas.microsoft.com/xps/2005/06"</b> was in XPS
</br>
</br>
<b>xmlns="http://schemas.openxps.org/oxps/v1.0"</b>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;     has become in OXPS
</p>

and XML header 

<p style="background: Ivory; padding: 10px;">
<b>&lt;?xml version="1.0" encoding="UTF-8"?&gt;</b>
</p>

has been added in OXPS files.

In <i>1.fpage</i> file besides already noted differences has been added some optimization of resources usage in <i>Canvas</i> element. Resources, in the given case are <i>PathGeometry</i>, 
that are used in <i>Canvas</i> more than one time transited in separate element <i>Canvas.Resources</i>. As for the other differences in <i>1.fpage</i>, for example, in <i>ImageBrush</i> element, 
there is no actual diffence there. It is just different order of printing XML attributes in the elements.

Changes in other files are similar to the ones described above. A structure of folders is left unchanged.

### Conclusion

So, we could make sure that the differences between XPS and OXPS files are rather formal. As for the 3D feature, that was added to OXPS, It seems wasn't used at all for this time. 
At least Google doesn't find such usage of OXPS.


## How do I open an OXPS file?

It is claimed that OXPS files cannot be opened with Windows standard XPS Viewer (was added as a standard component beginning with Windows 7). It is true only if the XPS file contains some extensions. In all other cases, XPS Viewer can be used to open and view OXPS files.


## Can I convert OXPS to PDF?

The conversion is possible by using online or desktop converter applications. The quickest way to convert OXPS files to PDF is to use
[Aspose.Page Conversion](https://products.aspose.app/page/conversion/oxps) web application. Aspose OXPS converter supports XPS to PDF, DOC, DOCX, HTML, TEX, SVG, PNG, JPG, TIFF, BMP conversions.
If you are a developer and want to use our library for such conversions, learn [PDLs converters](/page/net/convert/) article 
to find the illustrated with code snippets examples on how to do the conversion.


## Can I open an OXPS file in Word?

It is not possible directly, but you can convert OXPS file to Word document via some specific software like
[Aspose.Page Conversion](https://products.aspose.app/page/conversion/oxps-to-word) web application and then open it Microsoft Word text editor.

## Can OXPS files be converted to Excel?

Yes, you can convert OXPS to Excel online in [Aspose.Page Conversion](https://products.aspose.app/page/conversion/oxps-to-excel) web application.
The OXPS document will be recognized as a table. Note that the pictures are not transferred to resulting XLSX file.



