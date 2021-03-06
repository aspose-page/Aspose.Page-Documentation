---
title: Add Grid using Visual Brush
type: docs
weight: 10
url: /cpp/add-grid-using-visual-brush/
---

# **Add Grid**
Aspose.Page for C++ API lets you add a grid to the XPS document. Grid can be added to new as well as existing XPS documents using simple lines of code in C++ applications. This can be achieved using XpsVisualBrush class that is used to specify the properties of the grid with XpsPathGeometry and XpsCanvas objects. To add a grid to the XPS document, use the following steps.

1. Create a Document object using the XpsDocument class
1. Create an XpsPathGeometry object with defined required Segments
1. Create an object of XpsCanvas and set rendering Transformation
1. Set Fill and Opacity properties
1. Save the document using the Save method



{{< gist "aspose-com-gists" "1128d967b432793ca43e26bceca820d0" "example-source-AddGrid-AddGrid.cpp" >}}
