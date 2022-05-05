---
title: Comparison of Page Description Languages
type: docs
weight: 20
url: /net/comparison-of-page-description-languages/
keywords: comparison of page description languages, pdl, comparison of pdls, pdf vs xps, ps vs pdf
description: Which PDL is better PS, XPS, OXPS, EPS, PDF, or AI. Is it even correct to compare them? Can really one of them replace another one? Let's find out!
lastmod: "2022-02-11"
sitemap:
    changefreq: "weekly"
    priority: 0.8
---

## Criteria for evaluation

We have already described 6 [Page Description Languages](/page/net/page-description-languages/) (PDLs): [PS](/net/what-is-ps-file/), [EPS](/net/what-is-eps-file/), [AI](/net/what-is-ai-file/), [XPS](/net/what-is-xps-file/), 
[OXPS](/net/what-is-oxps-file/) and [PDF](/net/what-is-pdf-file/). It is not really correct to compare these PDLs because some of them can be called documents and others cannot. However, we will give it a try.

In order to get some quantitative evaluation from comparison, we offer a set of evaluation criteria and will rate PDL by these criteria by a 5-point system.
Some criteria will just show the presence or absence of some feature and will be evaluated just "1" for presence and "0" for the absence of the feature.
Other criteria will evaluate the quantity and variety of sub-features.


We offer to consider page description languages by such criteria:
* electronic document exchange;
* navigation;
* printing (including high-quality publishing systems);
* support by viewing tools;
* creation and edition;
* hyperlinks;
* transparency;
* 3D content;
* media content.

## Electronic document exchange

We begin the evaluation with electronic document exchange because it is a very important possibility for corporations. This feature includes support for co-working and digital signature, compression, support for different devices and resolutions, encryption, and the ability to extract data.

<b>PDF</b> has all of these features and therefore it is rated by <b>5</b>.

XPS doesn't support co-working, because it is not intended for editing at all. It also doesn't have the ability to extract data. So we can rate <b>XPS</b> and also <b>OXPS</b>
(because it is on 99% XPS) by <b>3</b> by this criterion.

PostScript and derived from it EPS and AI are not a document in its traditional mean. Besides, EPS and AI are just 1-page illustrations. Therefore we rate <b>PS</b>, <b>EPS</b>, 
<b>AI</b> by this criterion by <b>1</b>.


## Navigation

<b>PDF</b> has many ways to navigate through the pages and viewports: outline, thumbnail images, viewports, and articles. So we can rate it by <b>5</b> for navigation.

XPS has an outline, thumbnail images, possibility to move by structural elements such as sections, paragraphs, tables, and so on. So we can set <b>5</b> for <b>XPS/OXPS</b> too.

PostScript doesn't have navigation with an exception of natural one, page-by-page. EPS and AI are 1-paged illustrations and, thus, don't have navigation too.
Therefore <b>PS</b>, <b>EPS</b>, <b>AI</b> PDLs are got <b>1</b> for navigation.


## Printing (including high-quality publishing systems)

PDF, as well as PostScript, EPS, and AI share the same imaging model initially developed by Adobe exactly for high-fidelity printing in the device- and resolution-independent environments. Therefore PDF as well as PS, EPS, AI supports many color spaces (DeviceGray, DeviceRGB, DeviceCMYK, DeviceN, Spot, CIE-based, ICC) and fonts (Adobe Type 0,


Adobe Type 1, Adobe Type 3, Compact Fonts (CFF), Chameleon, TrueType, CID-keyed), color transition and separation, trapping and halftoning. So we rate <b>PDF</b>, <b>PS</b>,
<b>EPS</b> and <b>AI</b> by <b>5</b> for printing possibilities.

XPS was intended to be printed on ordinary office printers, so it supports less of color spaces (sRGB, scRGB, CMYK, N-Channel, ICC version 2) and only 2 types of fonts (TrueType 
and Compact Fonts (CFF)), doesn't support color transition and separation, trapping, and halftoning. Therefore we rate <b>XPS, OXPS</b> by <b>3</b> for printing.


## Support by viewing tools

PDF has the most support among a variety of viewers not including Adobe Acrobat Reader and it can be viewed even in browsers if the corresponding plugin is installed. So we rate <b>PDF</b> by <b>5</b> for this criteria.

PS and EPS can be viewed only by a small set of special applications, for example, EPSViewer or Gimp, therefore we set <b>3</b> for <b>PS</b> and <b>EPS</b>.

AI files, as I concluded from my research, can be viewed only with Adobe Illustrator and possibly some other vector graphics editor. We rate <b>AI</b> by <b>2</b>.

XPS can be viewed with Microsoft's XPSViewer in Windows or some PDF viewers in Linux. We rate <b>XPS</b> by <b>3</b>.

## Creation and edition

PS, EPS, AI, and PDF can be created and edited with paid Adobe applications such as Adobe Illustrator, Adobe Photoshop, Adobe Acrobat. Besides Adobe tools all graphics in these files can be created and edited with a free Inkscape application. PS, EPS and AI files also can be created and edited manually in a simple text editor. PDF cannot be edited manually in a text editor because it has a cross-reference table and trailer that contains object offset in bytes from the beginning of the file.

XPS is only created by printing some documents to XPS Writer in Windows only. And it cannot be edited with special applications because these applications don't exist.



But we can manually decompress an XPS file with any ZIP utility, do some changes manually and return changed pages back to the archive. So we give <b>5</b> for creation/edition 
to <b>PS</b>, <b>EPS</b>, <b>AI</b> files, <b>4</b> - to <b>PDF</b> and <b>2</b> to <b>XPS</b> files.


## Transparency

Though Adobe Imaging model doesn't support transparency PDF does. It contains, so called <i>transparency</i> groups that, in turn, contain PDF graphics objects having the same
transparency. Therefore an appropriate viewer and, possibly, printer can process graphics elements as transparent. Besides transparency groups images with alpha channels are also supported by PDF.
So we can say that <b>PDF</b> supports transparency on <b>4</b> points from 5, while
<b>EPS</b> and <b>AI</b> support transparency only as <i>alpha</i> channel in raster images. We rate them by <b>3</b> for supporting transparency.

PS doesn't even support alpha channels in images. So <b>PS</b> gets <b>1</b>.

<b>XPS</b> supports transparency on group's (canvases) and element's (paths, glyphs, images) levels and, thus, get solid <b>5</b> for support of transparency.


## Summary

Let's visualize the before given grades with the table, to get the winner of "the best PDL" contest.


<p align="center">
	<table>
		<thead>
		  <tr style="margin:0px; padding:10px;">
		      <th style="background: Beige; padding:10px; border: 2px solid lightgray;"><p align="left"><b>Criterion</b></p></th>
		      <th style="background: Beige; padding:10px; border: 2px solid lightgray;"><p align="center"><b>PS</b></p></th>
		      <th style="background: Beige; padding:10px; border: 2px solid lightgray;"><p align="center"><b>EPS</b></p></th>
		      <th style="background: Beige; padding:10px; border: 2px solid lightgray;"><p align="center"><b>AI</b></p></th>
		      <th style="background: Beige; padding:10px; border: 2px solid lightgray;"><p align="center"><b>XPS</b></p></th>
		      <th style="background: Beige; padding:10px; border: 2px solid lightgray;"><p align="center"><b>OXPS</b></p></th>
		      <th style="background: Beige; padding:10px; border: 2px solid lightgray;"><p align="center"><b>PDF</b></p></th>
		  </tr>
		</thead>
	<tbody>
		<tr>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
					<p align="left">
						<b>Electronic document exchange</b>
					</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					1				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					1				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					1				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					3				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">			
				<p align="center">
					3				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					5				
				</p>
			</td>
		</tr>
		<tr>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
					<p align="left">
						<b>Navigation</b>
					</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					1				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					1				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					1				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					5				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">			
				<p align="center">
					5				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					5				
				</p>
			</td>
		</tr>
		<tr>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
					<p align="left">
						<b>Printing (including high-quality publishing systems)</b>
					</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					5				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					5				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					5				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					3				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">			
				<p align="center">
					3				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					5				
				</p>
			</td>
		</tr>
		<tr>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
					<p align="left">
						<b>Support by viewing tools</b>
					</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					3				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					3				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					2				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					3				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">			
				<p align="center">
					3				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					5				
				</p>
			</td>
		</tr>
		<tr>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
				<p align="left">
					<b>Creation and edition</b>
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					4				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					4				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					4				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					2				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">			
				<p align="center">
					2				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					4				
				</p>
			</td>
		</tr>
		<tr>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
				<p align="left">
					<b>Transparency</b>
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					1				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					3				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					3				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					5				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">			
				<p align="center">
					5				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					4				
				</p>
			</td>
		</tr>
		<tr>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
				<p align="left">
					<b>Hyperlinks</b>
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					1				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">			
				<p align="center">
					1				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					1				
				</p>
			</td>
		</tr>
		<tr>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
				<p align="left">
					<b>3D content</b>
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">			
				<p align="center">
					1				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					1				
				</p>
			</td>
		</tr>
		<tr>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
				<p align="left">
					<b>Audio content</b>
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">			
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					1				
				</p>
			</td>
		</tr>
		<tr>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
				<p align="left">
					<b>Video content</b>
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">			
				<p align="center">
					0				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Ivory; border: 2px solid lightgray;">
				<p align="center">
					1				
				</p>
			</td>
		</tr>
		<tr>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
				<p align="left">
					<b>Summary</b>
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
				<p align="center">
					15				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
				<p align="center">
					17				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
				<p align="center">
					16				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
				<p align="center">
					22				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">			
				<p align="center">
					23				
				</p>
			</td>
			<td style="margin:0px; padding:10px; background: Beige; border: 2px solid lightgray;">
				<p align="center">
					32				
				</p>
			</td>
		</tr>
	</table>
</p>

As we can see PDF has got the most rate in our kinda analysis. By now, if relying on the criteria we've chosen, it is the most universal page description language and it is confirmed by its popularity.


