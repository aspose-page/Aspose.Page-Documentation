---
title: Introduction to Page Description Languages (PDLs)
type: docs
weight: 10
url: /net/page-description-languages/
keywords: page description language, pdl is, pdl
description: This page introducts Page Description Languages (PDL)
lastmod: "2022-02-11"
sitemap:
    changefreq: "weekly"
    priority: 0.8
---
Here is the introduction to the group of articles to teach you about Page Description Languages. You will find the descriptions of the terms,
examples of PDLs and their classification.

## What is page description language?

PDLs serves as a binding link between computer applications, such as graphics tools, text editors, etc, and output devices:
publishing (printing) systems and displays. Most printing systems treat printed pages as a rectangle of m pixels in a width and n pixels in a height.
Of course, it is not convenient to store such large files in memory, edit them, and transfer them over the distributed network.
Page Description Languages describe the appearance of a page at a higher level than an array of pixels.

Some of PDLs were invented by printer producer companies. For example, PCL (HP printers language) and HP-GL/2 (HP plotters
language) were invented by Hewlett-Packard, AFP (IBM and Ricoh printers language) was devised by IBM. The other ones were developed by software
companies, like Adobe with PostScript and PDF languages or Microsoft's XPS. Every company that invented its own PDL also developed a corresponding
interpreter. The interpreter is a program that is also often called "driver", which translates high-level PDL to an array of pixels that in this order
is transferred to native low-level software of a printer.

</br></br></br>
<p align="center">
	<img src="PDL diagram.png">
</p>
</br></br></br>

## Classification of Page Description Languages.

To be precise there is no actual classification of PDLs, but they are divided into two groups. They can be static and dynamic. 

Static languages, such as PDF or XPS, store only static data structure but allow to efficiently access its elements via
navigational information. Files that contain page descriptions in static language can be called "documents". 

In contrast to static languages, dynamic languages create page appearance on the fly using procedures for repetitive actions and
calculation of positions, changing used operators and resources in dependence on device conditions. A set of dynamic Page Description Languages compose
Adobe PostScript (PS) and Encapsulated PostScript (EPS) as a subset of PS. HP's PCL5 with macroses also can be referred to as dynamic PDLs.

</br></br>
<p align="center">
	<img src="PDL set.png">
</p>

## What is the difference between page description language and a markup language?
Page description languages and markup languages are different classifications of computer languages.
While markup languages are used just for separation of content and marks that define a way to process content, PDLs are used for 
documents where pages are strictly separated, and it doesn't separate marks and content.
At least such an idea wasn't considered when the PDL concept was developed. 
So markup language can describe pages if the content of a file is a page content, and it will be at the same PDL, but can also describe some data that 
doesn't relate to pages. PDL always describes page.

To strictly separate marks and content at the page, marks are represented by tags, which are some keywords enclosed with "<" and ">" or "/>".
This way markup language file is much more ordered and human-readable. It is the second main difference between markup and page description languages. 

The main intention of page description languages is a rendering of a page to a printing or display device, while markup languages can be used
without a rendering at all. For example, Extensible Markup language (XML), one of the most popular markup languages, is often used only for storing
and transferring data.

Another example of popular markup language is HTML. It marks content that are not separated on pages. So now you have the answer to the frequently
asked question, if HTML is a page description language or not.

XPS is a page description language and, at the first sight, can be also treated as markup language because has XML-based interior. 
But if we stare at this XML we can see that a content of the pages is inserted directly into elements (tags), that is not separated from rules 
for processing it. It breaks the main property of markup languages. Though Microsoft actively uses term "markup" in XPS specification,
It is not actually markup in a sense of Markup languages, such as XML or HTML.

## Conclusion

Not only did we try to tell you about the page description languages here, but also explained the difference between PDLs and markup languages.
It is also worth mentioning that in Aspose.Page family, we now have a big kit of tools to make it easier to manage files of PDL format.
Among the solutions, we have apps to [view](https://products.aspose.app/page/viewer), [convert](https://products.aspose.app/page/conversion),
[merge to pdf](https://products.aspose.app/page/merger) XPS, EPS, and PS files.
