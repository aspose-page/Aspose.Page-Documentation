---
title: Working with PS Document | .NET
linktitle: Working with PS Document
type: docs
weight: 70
url: /net/working-with-ps/
description: These articles is about working with text, shapes, tiling patterns, gradients, images and pages in PS or EPS files using Aspose.Page for .NET API solution.
keywords: working with PS document .NET, working with PostScript document .NET, working with EPS file .NET
---

`PS` and `EPS` extensions are linked to the PostScript and Encapsulated PostScript languages respectively that Adobe developed.

[PS](https://docs.aspose.com/page/net/what-is-ps-file/) is a dynamic Page description language. It uses graphics operators, procedures, control operators and variables.
[EPS](https://docs.aspose.com/page/net/what-is-eps-file/) is a restricted PostScript. Some PostScript operators are prohibited from using EPS files. At the same time, the EPS file must conform to PostScript Document Structuring Conventions Specifications that suppose to use structural comments. Generally, EPS was intended for the description of 1-paged graphics that can be encapsulated in PostScript files and their derivations.

Aspose.Page library allows the creation of both PS or EPS files with proper graphics elements, but in this guide, we will use only the PS file type. 
So we use for the creation of PS file such code:
```C#
using (Stream outPsStream = new FileStream(dir + "document.ps", FileMode.Create))
{
    //Create save options
    PsSaveOptions options = new PsSaveOptions();
    
    // Create new multipaged PS Document
    PsDocument document = new PsDocument(outPsStream, options, true);
}
```
If someone wish to create EPS file they should use the following code:
```C#
using (Stream outPsStream = new FileStream(dir + "document.eps", FileMode.Create))
{
    //Create save options
    PsSaveOptions options = new PsSaveOptions();
    //Set format of saved document as EPS
    options.SaveFormat = PsSaveFormat.EPS;
    
    // Create new EPS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
}
```
{{% alert color="primary" %}}
See working with PS documents in [Java](/page/java/ps/working-with-document/) and [C++](/page/cpp/ps/working-with-document/).
{{% /alert %}}

{{% alert color="primary" %}}
**Aspose.Page library can create only static PS/EPS documents. Control operators are not supported.**{{% /alert %}}

{{% alert color="primary" %}}
At this moment Aspose.Page library can only create PostScript documents, not edit it.
{{% /alert %}}


This chapter includes information about working with PS files using Aspose.Page API solution for .NET. There you will find the next articles with the code examples of how the functionality works.


- [Working with Document](https://docs.aspose.com/page/net/ps/working-with-document/)
- [Working with Pages](https://docs.aspose.com/page/net/ps/working-with-pages/)
- [Working with Shapes](https://docs.aspose.com/page/net/ps/working-with-shapes/)
- [Working with Transformations](https://docs.aspose.com/page/net/ps/working-with-transformations/)
- [Working with Clips](https://docs.aspose.com/page/net/ps/working-with-clips/)
- [Working with Text](https://docs.aspose.com/page/net/ps/working-with-shapes/)
- [Working with Images](https://docs.aspose.com/page/net/ps/working-with-images/)
- [Working with Texture Patterns](https://docs.aspose.com/page/net/ps/working-with-texture-patterns/)
- [Working with Hatch Patterns](https://docs.aspose.com/page/net/ps/working-with-hatch-patterns/)
- [Working with Gradient](https://docs.aspose.com/page/net/ps/working-with-gradient/)
- [Working with Transparency](https://docs.aspose.com/page/net/ps/working-with-transparency/)



