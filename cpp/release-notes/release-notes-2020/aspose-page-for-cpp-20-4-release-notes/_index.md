---
title: Aspose.Page for CPP 20.4 Release Notes
type: docs
weight: 9
url: /cpp/aspose-page-for-cpp-20-4-release-notes/
description: C++ Library for the developers to manipulate and process PS, EPS, and XPS files. Release Notes of Aspose.Page API solution for C++ | 4-th release of 2020
---

{{% alert color="primary" %}} 

This page contains release notes information for **Aspose.Page for C++ 20.4** release.

{{% /alert %}} 
## **Improvements and Changes**

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|PDFCPP-1256|Fix error on static initialization|Bug|
|PAGENET-102|Memory is not released when converting XPS file to PDF.|Bug|
|PAGENET-129 |Fix background for PS to Image.|Bug|
## **Public API and Backwards Incompatible Changes**
Since Aspose.Page for C++ is auto-ported from Aspose.Page for .NET API, it includes the same API changes as the equivalent .NET API. Additional changes include:

- **New Types**
  - XpsContext
  - FixedPage
  - FixedPart
  - FixedDocument
- **Properties**
  - XpsContext.ActivePage
  - FixedPage.Page
  - XpsElement.Parent
- **Methods**
  - XpsDocument.Assert()
  - XpsContext.Restict(System.Int32)
  - XpsObject.AssertObject()
