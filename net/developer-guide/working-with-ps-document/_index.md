---
title: Working with PS Document | .NET
linktitle: Working with PS Document
type: docs
weight: 70
url: /net/working-with-ps/
description: These are articles on how to work with text, shapes, texture and hatch patterns, gradients, images, transparency, and pages in PS or EPS files using Aspose.Page for .NET API solution.
---

`PS` and `EPS` extensions are linked to the PostScript and Encapsulated PostScript languages respectively that were developed by Adobe.

[PS](https://docs.aspose.com/page/net/what-is-ps-file/) is a dynamic Page description language. It uses graphics operators, procedures, control operators and variables.
[EPS](https://docs.aspose.com/page/net/what-is-eps-file/) is a restricted PostScript. Some PostScript operators are prohibited to use in EPS file. At the same time EPS file must conform PostScript Document
Structuring Conventions Specifications that supposes to use structural comments. Generally, EPS was intended for description of 1-paged graphics that can be encapsulated in PostScript files and it's derivations.

Aspose.Page library allows creation of both PS or EPS file with proper graphics elements, but in this guid we will use only PS file type.
So we use for creation of PS file such code:
```C#
using (Stream outPsStream = new FileStream(dir + "document.ps", FileMode.Create))
{
    //Create save options
    PsSaveOptions options = new PsSaveOptions();
    
    // Create new multipaged PS Document
    PsDocument document = new PsDocument(outPsStream, options, true);
}
```
If someone wish to creat EPS file he/she should use following code:
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
See working with PS document in [Java](/page/java/ps/working-with-document/) and [C++](/page/cpp/ps/working-with-document/).
{{% /alert %}}

{{% alert color="primary" %}}
**Aspose.Page library can create only static PS/EPS document. Control operators are not supported.**{{% /alert %}}

{{% alert color="primary" %}}
At this moment Aspose.Page library can only create PostScript documents, not edit it.
{{% /alert %}}


This chapter includes information about working with PS files using Aspose.Page API solution for .NET. There you will find the next articles with the code examples on how the functionality works.


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



