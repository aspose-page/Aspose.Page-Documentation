---
title: What is AI file?
type: docs
weight: 19
url: /net/what-is-ai-file/
keywords: what is ai file, what is ai file, ai what is it, ai file, ai format, what is ai
description: If you have ever worked with Adobe Illustrator editor you probably know such a file format as AI. This is one of the written in Postscript Language formats and is described detailly in this article.
lastmod: "2022-02-11"
sitemap:
    changefreq: "weekly"
    priority: 0.8
---

## Introduction

AI files are files created and used by Adobe Illustrator graphics editor. They are written in PostScript language, which you can read about in the article ["What is PS file?"](/page/net/what-is-ps-file).
Remind that PostScript language syntax has postfix notation in Backus&minus;Naur form (BNF).


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


Also as you can remember PS files minimally have a structure, consisting of <i>Prolog</i> and <i>Script</i> parts.

<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=800/>
<p align="left">
<b>%!PS-Adobe-3.0 EPSF</b>
</br>
&lt;header comments&gt;
</br>
<b>%%EndComments</b>
</br>
<b>%%BeginProlog</b>
</br>
{&lt;proc set&gt;}		&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<i>(not required, but is normally present)</i>
</br>
<b>%%EndProlog</b>
</br>
&lt;setup&gt;
</br>
{&lt;layer&gt;}|{&lt;object&gt;}
</br>
{&lt;page trailer&gt;}
</br>
&lt;document trailer&gt;
</br>
<b>%%EOF</b>
</br>
</p>
</td>
</tr>
</table>
</p>				

<i>Prolog</i> is a part where necessary data for subsequent script, rendering and printing is defined. This data can include the version of Postscript language, bounding box, creator, creation date and title. Necessary fonts, global variables and procedures are also should be defined here. Procedures are combined in 
<i>procsets</i>, dictionaries where every procedure is connected to the literal name. And every <i>procsets</i> also has a name. In case of EPS file when necessary font or other resource is not defined in <i>Prolog</i> it should be at least noted with corresponding comments <b>%%DocumentNeededFonts</b>, <b>%%DocumentNeededResources</b>,
<b>%%DocumentNeededProcSets</b>, <b>%%DocumentNeededFiles</b>.
<i>Script</i> contains page graphics descriptions that use procedures, global variables and fonts defined earlier in <i>Prolog</i>. 
Structure of PS/EPS files is marked by special <i>structural comments</i>, lines that begin with <b>%%</b>.



## What is AI file?
AI file or abbreviated Adobe Illustrator file is actually EPS file, as it is claimed by Adobe in AI specification. It contains two comments that are required in EPS files:


<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=800/>
<p align="left">
<b>%!PS-Adobe-3.0 EPSF</b>
</p>
</td>
</tr>
</table>
</p>
and
<p align="center">
<table>
<tr>
<td style="background: Beige;">
<img width=800/>
<p align="left">
<b>%%BoundingBox: ...</b>
</p>
</td>
</tr>
</table>
</p>		
		
But there are some differences between AI and EPS files.

The main difference is operators. Adobe Illustrator operators are one or two-symbols sequences, while PS/EPS use human-readable keywords that contain usually 
more than 2 letters. 

Adobe Illustrator uses more than 130 such 1-2-letter operators and definitions of them are not stored in <i>Prolog</i> of AI file,  as It would be in the case of EPS file, but are stored somewhere in Adobe Illustrator application. Very likely they are loaded in memory when the application starts.
And this is the second main difference between EPS and AI files.


Thus, AI files can be treated as EPS files only in case when Adobe Illustrator is used for creating, editing, viewing, and printing them. For external consumers, who do not have access to licensed stuff of Adobe Illustrator not included in <i>Prolog</i> of AI file, that is AI operators definitions, procedure sets, fonts, etc.,
AI format should be considered as a separate brand new file format.

Some AI operators are just short forms of PS operators, as is shown below.


<p align="center">
<table>
<tr>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>AI operator</b></p>
<img width=300/>
<p align="left">
<i>x y</i> <b>m</b>
</br>
<i>x y</i> <b>l</b>, <i>x y</i> <b>L</b>
</br>
<i>x<sub>1</sub> y<sub>1</sub> x<sub>2</sub> y<sub>2</sub> x<sub>3</sub> y<sub>3</sub></i> <b>c</b>, <i>x<sub>1</sub> y<sub>1</sub> x<sub>2</sub> y<sub>2</sub> x<sub>3</sub> y<sub>3</sub></i> <b>C</b>
</br>
<i>num</i> <b>w
</br>
<b>H</b>
</br>
<b>Xa</b>
</br>
</p>
</td>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>Native PS operator</b></p>
<img width=200/>
<p align="left">
<i>x y</i> <b>moveto</b>
</br>
<i>x y</i> <b>lineto</b>
</br>
<i>x<sub>1</sub> y<sub>1</sub> x<sub>2</sub> y<sub>2</sub> x<sub>3</sub> y<sub>3</sub></i> <b>curveto</b>
</br>
<i>num</i> <b>setlinewidth</b>
</br>
<b>closepath</b>
</br>
<i>red green blue</i> <b>setrgbcolor</b>
</p>
</td>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>Description</b></p>
<img width=400/>
<p align="left">
starts a new subpath of the current path
</br>
appends a straight line segment to the current path
</br>
appends a section of a cubic Bezier curve to the current path
</br>
sets the line width parameter in the graphics state
</br>
closes the current subpath
</br>
sets the current color space in the graphics state to DeviceRGB and the current color
to the component values specified by red, green, and blue
</p>
</td>
</tr>
</table>
</p>

Others represent a more detailed form of PS operators.

<p align="center">
<table>
<tr>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>AI operator</b></p>
<img width=200/>
<p align="left">
<i>x<sub>2</sub> y<sub>2</sub> x<sub>3</sub> y<sub>3</sub></i> <b>v</b>, <i>x<sub>2</sub> y<sub>2</sub> x<sub>3</sub> y<sub>3</sub></i> <b>V</b>
</br>
<i>x<sub>1</sub> y<sub>1</sub> x<sub>3</sub> y<sub>3</sub></i> <b>y</b>, <i>x<sub>1</sub> y<sub>1</sub> x<sub>3</sub> y<sub>3</sub></i> <b>Y</b>
</br>
<i>red green blue</i> <b>Xa</b>
</br>
<i>red green blue</i> <b>XA</b>
</br>
<i>cyan magenta yellow black</i> <b>k</b>
</br>
<i>cyan magenta yellow black</i> <b>K</b>
</br>
<b>F</b>
</br>
<b>f</b>
</br>
<b>S</b>
</br>
<b>s</b>
</br>
<i>[ a b c d tx ty ] llx lly urx ury </br>h w bits ImageType AlphaChannelCount </br>reserved bin-ascii ImageMask</i> <b>XI</b></b>
</p>
</td>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>Description</b></p>
<img width=400/>
<p align="left">
adds a Bezier curve segment to the current path between the current point and the point x3, y3, using the current point and then x2, y2 as the
Bezier direction points
</br>
appends a Bezier curve to the current path between the current point and the point x3, y3 using x1, y1 and x3, y3 as the Bezier
direction points
</br>
setrgbcolor for fill
</br>
setrgbcolor for stroke
</br>
setcmykcolor for fill
</br>
setcmykcolor for stroke
</br>
fills the area enclosed by the current path with the current filling color or pattern, leaving it as an open path
</br>
the same, but close path
</br>
strokes the area enclosed by the current path with the current filling color or pattern, leaving it as an open path
</br>
the same, but close path
</br>
describes a raster image in Adobe Illustrator
</p>
</td>
</tr>
</table>
</p>

And there are brand new operators, for example those who deal with text, gradients or layers. 

<p align="center">
<table>
<tr>
<td style="background: Ivory; border-color: Ivory; margin: 0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>AI operator</b></p>
<img width=300/>
<p align="left">
<b>N</b>
</br>
<b>n</b>
</br>
<b>B</b>
</br>
<b>b</b>
</br>
<i>(path) modified</i> <b>XG</b>
</br>
<i>type</i> <b>To</b>
</br>
<b>TO</b>
</br>
<i>alignment</i> <b>Ta</b>
</br>
<i>a b c d t<sub>y</sub> t<sub>y</sub></i> <b>Tm</b>
</br>
<i>t<sub>y</sub> t<sub>y</sub></i> <b>Td</b>
</br>
<i>name</i> <b>Ln</b>
</br>
<i>[ a b c d tx ty ] llx lly urx ury </br>h w bits ImageType AlphaChannelCount </br>reserved bin-ascii ImageMask</i> <b>XF</b>
</p>
</td>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>Description</b></p>
<img width=400/>
<p align="left">
neither fills nor strokes, leaving it as an open path
</br>
the same, but close path
</br>
fills and strokes, leaving it as an open path
</br>
the same, but close path
</br>
image link operator
</br>
begins a text object. The type argument take on one of the following values: 0 &minus; point text; 1 &minus; area text; 2 &minus; path text
</br>
ends a text object and restores the current transformation matrix
</br>
sets text alignment both horizontally and vertically
</br>
sets the text matrix for text along a path
</br>
translates the text matrix by <i>tx</i> and <i>ty</i> to the beginning of the next line of text
</br>
sets layer name
</br>
describes a raster image in Adobe Illustrator when the actual image data is not included in the file
</p>
</td>
</tr>
</table>
</p>

It is worth mentioning especially grouping operators. They are composed from begin and end operators and have other operators between them.

<p align="center">
<table>
<tr>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>AI operator</b></p>
<img width=300/>
<p align="left">
<b>*u ... *U</b>
</br>
<b>u ... U</b>
</br>
<i>name type nColors</i> <b>Bd ... BD</b>
</br>
<i>topLeftCellIndex selectedIndex</i> <b>Pb ... PB</b>
</br>
<b>Mb ... MB</b>
</br>
<i>visible preview enabled printing </br>dimmed hasMultiLayerMasks </br>colorIndex red green blue</i> <b>Lb ... LB</b>
</p>
</td>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>Description</b></p>
<img width=400/>
<p align="left">
begin compound path, end compound path
</br>
begin compound group, end compound group
</br>
begin gradient definition, end gradient definition
</br>
begin palette, end palette
</br>
begin mask, end mask
</br>
begin layer definition, end layer definition
</p>
</td>
</tr>
</table>
</p>

The third difference is pseudo comments. As we already know PostScript interpreter distinguishes standard comments, lines that begin with '<b>%</b>' and
structural comments that begin with '<b>%%</b>'. Adobe Illustrator adds additional, so-called, "pseudo" comments, that begin with '<b>%_</b>'. These comments are actually brand new, 
peculiar to Adobe Illustrator, operators. They are implemented as comments in order to be ignored by the PostScript interpreter
but are used by Adobe Illustrator and other applications that read and parse AI files. Below is an example of such comments-operators.


<p align="center">
<table>
<tr>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>AI operator</b></p>
<img width=300/>
<p align="left">
<i>colorSpec colorStyle midPoint rampPoint</i> <b>%_Bs</b>
</br>
<i>rampSpec rampType</i> <b>%_Br</b>
</br>
<b>%_Gs</b>
</br>
<b>%_</b>
</p>
</td>
<td style="background: Ivory; border-color: Ivory; margin:0px; padding:0px; border-width:0px;">
<p align="left" style="background: Beige;"><b>Description</b></p>
<img width=400/>
<p align="left">
gradient color stop description
</br>
description of the gradient ramp
</br>
opens the graph section
</br>
make some other peculiar to Adobe Illustrator operators ignorable by PS interpreter
</p>
</td>
</tr>
</table>
</p>

The last difference between AI and EPS files is <i>Revisable Form</i>. Adobe separates <i>Revisable Form</i> and <i>Final Form</i> of a document. <i>Final Form</i> contains only information necessary for viewing or printing pages.
<i>Revisable Form</i> contains other stuff that can be used for editing documents in an application but is not necessary for printing. Some AI operators exist only for <i>Revisable Form</i>. Especially many of these operators are used in working with text. Pseudo comments are all used for <i>Revisable Form</i>. EPS files, in contrast, are documents in <i>Final Form</i>.


## What is AI File used for?

AI file is used for editing, transferring and storing Adobe Illustrator application graphics.

## How do I open an AI File?

AI files can be opened and viewed with standalone Adobe Illustrator application.

## Is PDF the same as AI File?

No, they are different formats and languages. Though PDF and AI files have the same internal page description model, PDF is a static Page Description Language, while AI is a subset of PostScript, dynamic Page Description Language.



