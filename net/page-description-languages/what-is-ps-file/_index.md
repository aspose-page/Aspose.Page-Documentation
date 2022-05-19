---
title: What is PS file?
type: docs
weight: 15
url: /net/what-is-ps-file/
keywords: what is ps file, ps what is it, what is postscript, ps file, ps format, ps language, postscript file, postscript format, postscript language
description: PS as one of the PDLs languages is thoroughly explained here. Along with it this page briefly answers the question "What is a PS file?"
lastmod: "2022-02-11"
sitemap:
    changefreq: "weekly"
    priority: 0.8
---

## Introduction

From the article about [page description languages](/page/net/page-description-languages/) you found out that Postscript language is one of PDLs,
a dynamic one if to be more specific. The article here is going to give you more information about PS format and PS files, their peculiarities, 
structure and usage.

So, What is PS file? </br>

PS file is a file containing page(s) description written in PostScript language from Adobe. PostScript refers to dynamic PDLs that contain not only 
graphics primitive operators, but also procedures, control operators, and variables.  

PostScript was invented as a high-fidelity mean to control the output of graphics to printing and display devices allowing to obtain high-quality
vector and raster graphics and text even on publishing systems with high resolution and separated colors printing devices. On the other hand, it was 
necessary to have a way for storing and transferring pages description that occupies not that much memory as arrays of pixels do, and that can be 
easily edited via computer applications.  

PostScript language has operators for working with: graphics state, path construction, painting, operand stack, execution control, glyphs and fonts, 
numbers, arrays, matrixes, strings, booleans, files, resources. Examples of path construction and execution control operators are represented 
in the table below.

<p align="center">
<table>
<tr>
<td style="background: white; border-color: white">
<p align="center"><b>Examples of path construction operators</b></p>
<img width=400/>
<p align="center">
moveto, rmoveto
</br>
lineto, rlineto
</br>
curveto, rcurveto
</br>
arc, arcn, arct, arcto
</br>
closepath
</br>
clippath
</br>
</p>
</td>
<td style="background: white; border-color: white">
<p align="center"><b>Examples of execution control operators</b></p>
<img width=400/>
<p align="center">
ifelse
</br>
for, forall
</br>
loop
</br>
repeat
</br>
exit
</p>
</td>
</tr>
</table>
</p>  

Using control operators together with variables allows doing thorough positioning of text. Also declaring repetitive sequences of operators in 
procedures in a prolog of PS program a volume of PS files can be significantly decreased. These repetitive actions may be, for example,the 
printing of page numbers, titles, borders, a company logo image. Another case of procedures usage may be different ways of page rendering depending 
on what version of PostScript interpreter is installed on the device. Or it can be the processing of the error, for example, resulting from the 
absence of some font or another resource on the device.  

Developers of PostScript have made an effort to enclose by possibilities of language maximum quantity of output device types.
Therefore it supports big sets of font and color space types.

<p align="center">
<table>
<tr>
<td style="background: white; border-color: white">
<p align="center"><b>Fonts</b></p>
<img width=400/>
<p align="center">
- Adobe Type 0
</br>
- Adobe Type 1
</br>
- Compact Fonts (CFF)
</br>
- Chameleon
</br>
- TrueType
</br>
- CID-keyed
</br>
</p>
</td>
<td style="background: white; border-color: white">
<p align="center"><b>Color spaces</b></p>
<img width=400/>
<p align="center">
- DeviceGray
</br>
- DeviceRGB
</br>
- DeviceCMYK
</br>
- DeviceN
</br>
- Separated colors
</br>
- Spot
</br>
- CIE-based
</p>
</td>
</tr>
</table>
</p>

## Syntax and structure

 PostScript uses BNF (Backus�Naur form) postfix notation where the operator goes after its operands.

</br></br></br>
<p align="center">
	<img src="PS syntax.png">
</p>
</br></br></br>

PS file consists of prolog and a script. Prolog is located at the beginning of PS file and contains common for all pages
and entire document variables, procedures, fonts, gradients. After the prolog script goes. 

</br></br></br>
<p align="center">
	<img src="PS file structure.png">
</p>
</br></br></br>

The script describes pages and it is explicitly divided into pages.
At the beginning of each page \"page setup\" section can be found. Necessary transformations and page\'s graphics properties are set up here. 
At the end of the page graphics state that was before page setup is returned back. These manipulations are performed by \"gsave\" 
and \"grestore\" operators.

## What is PS format?

Strictly speaking, PS or abbreviated PostScript is not a format, because if it was a format then the format of what? If it was a format of a document, 
then we could say that PostScript is not a document but a programming language. If it was a format of a file, then we could say that format of 
the .PS file is a text in ASCII encoding. More correctly would be to call it PostScript (programming) language or 
PostScript dynamic [PDL](/page/net/page-description-languages/) or [PS file](/page/net/what-is-a-ps-file/).

## How do I open a .PS file?

PS files can be opened with standalone Adobe's applications: Acrobat Distiller, Illustrator, Photoshop, or with Apple Preview.
If someone wants just to open to view or demonstrate PS files they can do it easily 
and fast with [Aspose.Page Viewer](https://products.aspose.app/page/viewer/ps) web application.

## How do I convert PS to JPG, or other image format?

The quickest way to convert PS file to JPG or PDF is to use
[Aspose.Page Conversion](https://products.aspose.app/page/conversion/ps) web application. Aspose PS converter supports PS to PDF, DOC, DOCX, HTML,
TEX, SVG, PNG, JPG, TIFF, BMP, EMF, WMF conversions.
If you are a developer and want to use our library for such conversions, learn [PDLs converters](https://docs.aspose.com/page/net/convert/) article 
to find the illustrated with code snippets examples on how to do the conversion.

## How do I merge PS files?

In this case again Aspose.Page applications come in handy. Just use our
[Merger](https://products.aspose.app/page/merger/ps) web application and combine your PS files into one PDF file.
