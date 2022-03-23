---
title: What is PDF file?
type: docs
weight: 19
url: /net/what-is-pdf-file/
keywords: what is pdf file, pdf what is it, pdf file, pdf format, what is pdf
description: PDF is one of, if not, the most popular Page Description languages. The format is known to anyone who has a computer or even a smartphone, as it is supported by most interfaces and systems.
lastmod: "2022-02-11"
sitemap:
    changefreq: "weekly"
    priority: 0.8
---

## Introduction

As you already know from the article about ["PDLs"](/page/net/page-description-languages), PDF is a static Page Description Language that has a strict unchangeable structure.

PDF is one of, if not, the most popular Page Description language due to a huge variety of features that developers from Adobe added to its specification.
Moreover, Adobe also provides people with tools able to realize these features in documents. This article is a brief review of the syntax, structure and features of PDF.


##  What is PDF file?

The initial goal of developing PDF or abbreviated Portable Document Format was to create a document format that satisfied numerous requirements of digital document interchange in device-independent and resolution-independent environments. These requirements include interactive view, high-performance navigation, low disk space occupation, co-working on documents, support for different media content, encryption, signing, form creation, presentation, and so on. In spite of the initial intent to provide enterprises with the exhaustive format for digital document interchange, high-quality printing features were also added to the specification, though later.


## Syntax of PDF file

PDF has an imaging model derived from PostScript's one, also use 1-2-characters, long operators, as well as in AI format, and also has postfix BNF syntax, where all necessary operands go before the operator.

<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=800/>
<p align="left">
operand<sub>1</sub>...operand<sub>m</sub> <b>operator</b>
</br>
</p>
</td>
</tr>
</table>
</p>  

Besides operator length, there are some differences between PDF and PostScript operators. In PDF all necessary operands must precede operators while in Postscript operands are obtained from the PostScript stack. In PDF the operator doesn't return a result as it can be in PostScript. PDF operator executes some action to compose a page, for example drawing graphics or text or sets some property in a graphics environment.
In PostScript, operators do all the work.

Usually, the most of PDF files content is compressed with Flate encoding and, this way is binary. Besides compression PDF files also can be encrypted to limit access to document content. Therefore the whole file must be treated as binary. Only in the case when a PDF file is neither compressed nor encrypted and doesn't contain binary content, such as images, sound, video, etc., it can be considered textual.



### PDF specification Objects

In PDF specification object is a synonym of type, while in PostScript there are types that can be primitive and complex and the last can be called "objects".
Therefore all types in PDF, either simple or complex, are objects. PDF language consists of boolean values, integers, real numbers, names, strings, arrays, dictionaries, and streams.
Strings can be in literal or hexadecimal format as it is shown below. 


<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=300/>
<p align="left">
<b>( This is a string )</b>
</br>
<b>&lt;4E6F762073686D6F7A206B6120706F702E&gt;</b>
</p>
</td>
<td style="background: Beige;">
<img width=300/>
<p align="left">
literal format
</br>
hexadecimal format
</p>
</td>
</tr>
</table>
</p>

Arrays are bounded with square brackets. It includes a subtype Rectangle - array with 4 elements.

Dictionaries store the data in key-value pairs where the key is a name or string (for Names dictionary) and the value is object or object reference.
It is enclosed in double-angle brackets. Dictionaries have a <b>Type</b> field that shows what data is stored in a given dictionary.


<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=800/>
<p align="left"><b>
<< /Type /Example
</br>
	&nbsp;&nbsp;/Subtype /DictionaryExample
	</br>
	&nbsp;&nbsp;/Version 0 . 01
	</br>
	&nbsp;&nbsp;/IntegerItem 12
	</br>
	&nbsp;&nbsp;/StringItem ( a string )
	</br>
	&nbsp;&nbsp;/Subdictionary << /Item1 0 . 4
	</br>
		&nbsp;&nbsp;&nbsp;&nbsp;/Item2 true
		</br>
		&nbsp;&nbsp;&nbsp;&nbsp;/LastItem ( not ! )
		</br>
		&nbsp;&nbsp;&nbsp;&nbsp;/VeryLastItem ( OK )
		</br>
	&nbsp;&nbsp;>>
	</br>
>>
</br>
endobj
</b></p>
</td>
</tr>
</table>
</p>

Objects can be direct and indirect. Indirect objects are those that can be referred from other objects by their ID.

</br>
<p align="center">
	<img src="PDF indirect objects.png">
</p>
</br>

Streams are objects that usually contain binary or encoded data. They are human-unreadable and don't have limitations on length.
Usually, PDF files streams contain compressed page content or images or some other media. Stream object consists of a direct dictionary with a length of the stream and an array of filters used for encoding the stream, and encoded data after keyword <b>stream</b>.


<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=800/>
<p align="left"><b>
181 0 obj
</br>
   &nbsp;&nbsp;<<
   </br> 	
      &nbsp;&nbsp;&nbsp;&nbsp;/Length 473 0 R
      </br>
      &nbsp;&nbsp;&nbsp;&nbsp;/Subtype /Image
      </br>
      &nbsp;&nbsp;&nbsp;&nbsp;/Width 2
      </br>
      &nbsp;&nbsp;&nbsp;&nbsp;/Height 19
      </br>
      &nbsp;&nbsp;&nbsp;&nbsp;/BitsPerComponent 8
      </br>
      &nbsp;&nbsp;&nbsp;&nbsp;/ColorSpace /DeviceGray
      </br>
      &nbsp;&nbsp;&nbsp;&nbsp;/Filter [/ASCII85Decode /FlateDecode]
      </br>
   &nbsp;&nbsp;>>
   </br>
stream
</br>
Gb"[2*s&lt;F2i'/7_!,1%/hZ~&gt;
</br>
endstream
</br>
endobj
</b></p>
</td>
</tr>
</table>
</p>

### PDF Operators

Operators are kind of direct objects that make page graphics and, as we mentioned earlier, are represented by 1- or 2-letters keywords.
There are two kinds of PDF operators:
	
	* executing actions or setting properties of the graphics state.

	
<p align="center">
<table>
<tr>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>PDF operator</b></p>
<img width=200/>
<p align="left">
<i>x y <b>m</b>
</br>
<i>x y <b>l</b>
</br>
<i>x<sub>1</sub> y<sub>1</sub> x<sub>2</sub> y<sub>2</sub> x<sub>3</sub> y<sub>3</sub></i> <b>c</b>
</br>
<b>h</b>
</br>
<i>x y width height</i> <b>re</b>
</br>
<i>a b c d e f</i> <b>cm</b>
</br>
<b>S</b>
</br>
<b>s</b>
</br>
<b>f</b>
</br>
<b>F</b>
</br>
<b>W</b>
</br>
<i>font size</i> <b>Tf</b>
</br>
<i>charSpace</i> <b>Tc</b>
</br>
<b>q</b>
</br>
<b>Q</b>
</br>
<i>lineWidth</i> <b>w</b>
</br>
<i>lineCap</i> <b>J</b>
</br>
<i>font size</i> <b>Tf</b>
</br>
<i>charSpace</i> <b>Tc</b>
</p>
</td>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>Description</b></p>
<img width=400/>
<p align="left">
begin a new subpath by moving the current point to coordinates (x, y)
</br>
append a straight line segment from the current point to the point (x, y)
</br>
append a cubic Bezier curve to the current path
</br>
close the current subpath
</br>
append a rectangle to the current path
</br>
modify the current transformation matrix by concatenating the specified matrix
</br>
stroke the path
</br>
the same, but close path
</br>
fill the path
</br>
the same, but close path
</br>
modify the current clipping path by intersecting it with the current path
</br>
set the text font to <i>font</i> and the text font size to <i>size</i>
</br>
set the character spacing to <i>charSpace</i>
</br>
save the current graphics state on the graphics state stack
</br>
restore graphics state from the graphics state stack
</br>
set the line width in the graphics state
</br>
set the line cap style in the graphics state
</br>
set the text font to <i>font</i> and the text font size to <i>size</i>
</br>
set the character spacing to <i>charSpace</i>
</p>
</td>
</tr>
</table>
</p>
	
	* grouping
	
<p align="center">
<table>
<tr>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>PDF operator</b></p>
<img width=200/>
<p align="left">
<b>BT...ET</b>
</br>
<b>BI...EI</b>
</br>
<b>BMC...EMC</b>
</br>
<b>BX...EX</b>
</p>
</td>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>Description</b></p>
<img width=400/>
<p align="left">
begin and end a text object
</br>
begin and end an image object
</br>
begin and end a marked-content sequence
</br>
begin and end a compatibility section
</p>
</td>
</tr>
</table>
</p>
	
Special kinds of grouping operators are <b>BX...EX</b>. They enclose portions of page content where unidentified objects must be ignored.
Thus, they are equivalents of AI <b>%_</b> pseudo-comments.

## PDF file structure

PDF file has four mandatory structural elements.

</br>
<p align="center">
	<img src="PDF file structure.png">
</p>
</br>

1. One-line header, where the version of PDF language is written

<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=800/>
<p align="left">
<b>%PDF-1.5</b>
</p>
</td>
</tr>
</table>
</p>
	
2. Body that contains document's objects. Structure of the body will be described later in this article.

3. Cross-reference table. It is used for quick random access to the document's objects. It contains an offset in bytes to the beginning of the objects from the start of the file.

<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=800/>
<p align="left">
<b>xref</b>
</br><b>
0 6
</br>
0000000003 65535 f
</br>
0000000017 00000 n
</br>
0000000081 00000 n
</br>
0000000000 00007 f
</br>
0000000331 00000 n
</br>
0000000409 00000 n
</b></p>
</td>
</tr>
</table>
</p>

4. Trailer, points to the last cross-reference table and contains a common quantity of objects in cross-reference tables,
The ID of the document and references to:
	* previous cross-reference table if there are several ones in the file;
	* document Root that represented by Catalog dictionary;
	* Meta information dictionary with Author, Creator, Title, Keywords, creation and modification date fields;
	* Encryption dictionary if the document is encrypted.


<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=800/>
<p align="left">
<b>trailer
</br>
&nbsp;&nbsp;<< 
</br>
   &nbsp;&nbsp;&nbsp;&nbsp;/Size 15
   </br>
   &nbsp;&nbsp;&nbsp;&nbsp;/Root 2 0 R
   </br>
   &nbsp;&nbsp;&nbsp;&nbsp;/Info 1 0 R
   </br>
&nbsp;&nbsp;>>
</br>
startxref
</br>
6224</b>
</p>
</td>
</tr>
</table>
</p>

A new cross-reference table and trailer are added after every update of the document. It will be described later in the article.

## Document structure

The PDF document has a tree-like structure where the root is a Catalog dictionary.


</br>
<p align="center">
	<img src="PDF document structure.png">
</p>
</br>

Catalog contains references on the pages description subtree, outline subtree and other document level subtrees and leaf nodes.

<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=800/>
<p align="left"><b>
2 0 obj
</br>
&nbsp;&nbsp;<< /Type /Catalog
</br>
	&nbsp;&nbsp;&nbsp;&nbsp;/Pages 3 0 R
	</br>
	&nbsp;&nbsp;&nbsp;&nbsp;/Outlines 4 0 R
	</br>
	&nbsp;&nbsp;&nbsp;&nbsp;/PageMode /UseOutlines
	</br>
	&nbsp;&nbsp;&nbsp;&nbsp;/ViewerPreferences 5 0 R
	</br>
	&nbsp;&nbsp;&nbsp;&nbsp;/OpenAction [6 0 R /Fit]
	</br>
&nbsp;&nbsp;>>
</br>
endobj
</b></p>
</td>
</tr>
</table>
</p>

Pages tree contains ordering of page-tree nodes and page-leaf nodes. Exactly tree-like structure of a set of pages together with search algorithm allows quick navigating across thousands of pages to find a needed one.

</br>
<p align="left">
	<img src="PDF page content stream.png">
</p>
</br>

Page dictionary contains reference on Content stream that can be compressed as it is on the figure above or uncompressed. In the last case, we would see PDF operators in human-readable text
as in the figure below.

<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=800/>
<p align="left"><b>
7 0 obj
</br>
   &nbsp;&nbsp;<<
   </br> 
      &nbsp;&nbsp;&nbsp;&nbsp;/Length 8 0 R
      </br>
   &nbsp;&nbsp;>>
   </br>
stream
</br>
1 0 0 1 0 0 cm
</br>
0 0 m
</br>
595 0 l
</br>
595 842 l
</br>
0 842 l
</br>
h
</br>
W
</br>
n
</br>
q
</br>
/Alpha1 gs
</br>
0 0 0 rg
</br>
0 0 0 RG
</br>
0 J
</br>
q
</br>
0.96593 0.25882 -0.25882 0.96593 0 0 cm
</br>
1 0 0 1 0 0.25882 cm
</br>
0.02 w
</br>
-0.96593 0 m
</br>
0 -0.25882 l
</br>
0 -0.25882 0 -0.25882 0 -0.25882 c
</br>
0.14294 -0.25882 0.25882 -0.14294 0.25882 0 c
</br>
0.25882 0.14294 0.14294 0.25882 0 0.25882 c
</br>
h
</br>
S
</br>
Q
</br>
endstream
</br>
endobj
</b></p>
</td>
</tr>
</table>
</p>

Besides an array of child nodes (it can be page-tree or page nodes) Pages, the dictionary contains reference to Resources dictionary, that in its turn refers to Fonts, ProcSets, Images (XObject), etc.


<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=800/>
<p align="left"><b>
9 0 obj
</br>
&nbsp;&nbsp;<<
</br>
	&nbsp;&nbsp;&nbsp;&nbsp;/ProcSet 10 0 R
	</br>
	&nbsp;&nbsp;&nbsp;&nbsp;/XObject 11 0 R
	</br>
	&nbsp;&nbsp;&nbsp;&nbsp;/Font 12 0 R
	</br>
	&nbsp;&nbsp;&nbsp;&nbsp;/ExtGState 13 0 R
	</br>
&nbsp;&nbsp;>>
</br>
endobj
</b></p>
</td>
</tr>
</table>
</p>

Annotation and others subtrees will be mentioned casually in Features section

## Features

### Graphics possibilities of PDF format

No sense in mentioning common for most of Page Description Languages possibilities in drawing graphics and text.
We just say that the richness of supported fonts and color spaces are the same as in PostScript.


<p align="center">
<table>
<tr>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="center" style="background: Beige;"><b>Fonts</b></p>
<img width=200/>
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
</br>
</p>
</td>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="center" style="background: Beige;"><b>Color spaces</b></p>
<img width=200/>
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

### Transparency

PDF supports transparency.

### External files

Any media or document file can be embedded to PDF or referred to from a document.

### Hyperlinks

Hyperlinks are supported in PDF.

### Electoral and interactive view

PDF allows showing only parts of the content and its appearance that are necessary for certain usage and hiding the others. It is useful, for example, when importing Adobe Illustrator graphics that have layers some of which are necessary for working in Adobe Illustrator, but are not necessary for viewing in Adobe Acrobat Reader. Another case of electoral view can be an article written in different languages or represented for users with disabilities but saved in one document. There can also be different variants of usage: one view for viewing, designing, and printing.


An interactive view of PDF includes abilities:

* to view/add annotations to parts of documents;
* to edit the document with the possibility to view all editions;
* to order the content of the document in different threads of articles gathered by certain subjects.
> Annotation is a sort of floating box containing some notes, sound, video, or some other content.


### Interactive navigation

Navigating between different parts of documents can be realized in several ways:

* moving through the document from the start to necessary page consecutively page-by-page;
* jumping from one part of the document to another one with outline items;
* jumping from one page to another one by clicking thumbnail images;
* jumping from one part of the document to another one with article thread items;
* jumping from one part of the document to another one using viewports and moving between them by pressing &lt;Tab&gt;.
> Moving by viewports and hiding some parts of the document is realized by means of Viewport and NavigationNode dictionaries.


### Incremental updates

All changes that were made in the PDF document are appended to the document without erasing previous content. And every time the documents are changed new xref (cross-reference table) and trailer are added. The new cross-reference table contains references on added or removed objects and on the previous cross-reference table. Such a mechanism allows putting together the final document content and, at the same time, storing previous states of the document.


### Performance

High performance of navigating through pages is provided by Pages tree-like structure and effective search algorithm. However It can be increased further by combining repetitive graphics elements into one object, called <b>Form XObject</b> and using one object in all necessary places. There is also a way to optimize the whole document for a high-performance view. It is linearization. Linearization was initially invented for effective viewing of PDF documents accessed by the web.
The linearized PDF document is read-only, any change to this will require repeated linearization.

High performance of navigating between document objects is realized by cross-reference tables that store object offsets from the start of the file.


### Compression

Compression of PDF documents, usually Flat encoding, allows the creation of large documents with relatively low disk space occupation. For example, the PDF specification file that contains 758 pages with an outline, thumbnails, images, and tables has about 9 Mb size.


### Security
PDF documents can be encrypted to give differentiated access only to certain users and they can be signed.
The digital signing feature allows authenticating of the identity of the user and the document's content.
Digital Signature binds document state when it is signed with user information. Digital signature can be in any form:
from purely mathematical to retinal scan if corresponding <b>signature handler</b> is provided.


### Interactive forms
It is used for gathering information from users. Interactive forms, or so called <b>AcroForms</b> can validate, format and send user data to a server.

### Presentation

There are several means of presentation in PDF:

* actions that are executed when document is opened;
* actions that are executed when page is opened;
* duration of showing a page;
* effects that appear while transiting from page to page.
	
### Media content

Images, sounds, movie clips and 3D graphics can be added to PDF documents.

### Extraction data

PDF allows adding certain markup that provides external applications with the possibility to extract necessary data.
Document with such markup called <b>Tagged PDF</b>.

### Prepress support

Preparing for publishing includes printer's marks, color separation, output intents and trapping.

## What is the use of a PDF file?

The main application of PDF documents is electronic document interchange and viewing in different environments.

## How do I make a PDF file?

Creation and editing of PDF documents are possible in standalone Adobe Acrobat applications.

## How do I open a PDF file?

You can open and view PDF files in standalone Adobe Acrobat Reader application or in Google Chrome browser with PDF plugin.
Also simple utilities such as Sumatra PDF, Foxit Reader or Free PDFReader, will help you.
Another way is to view PDF online, for example, on Google Drive.




