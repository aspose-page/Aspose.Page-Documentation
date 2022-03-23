---
title: What is XPS file?
type: docs
weight: 17
url: /net/what-is-xps-file/
keywords: what is xps file, what is xps file, xps what is it, xps file, xps format, xps language
description: This page briefly answers the question "What is XPS file?"
lastmod: "2022-02-11"
sitemap:
    changefreq: "weekly"
    priority: 0.8
---

## Introduction

From the article about [page description languages](/page/net/page-description-languages/) you found out that XPS is one of the static PDLs. The article here is going to give you more information about XPS format and XPS files, their peculiarities, 
structure and usage.

## What is XPS file?
XPS or abbreviated XML Paper Specification file represents a ZIP-compressed package of resources (images, fonts, etc) and XML-based files that reference these resources. XML-based files
store the content of documents and pages and relationships between various parts of the package. It is an important feature of XPS format that all necessary resources of documents are stored in the same package as documents themselves.


### Typical structure of an XPS file.
If we open any XPS file with some ZIP utility we can view the following structure:

</br>
<p align="center">
	<img src="XPS package.png">
</p>
</br>
"Fixed document sequense.fdseq" is a root of package tree. It contains a list of documents in the package.

    <FixedDocumentSequence xmlns="http://schemas.microsoft.com/xps/2005/06">
        <DocumentReference Source="Documents/1/FixedDocument.fdoc" />
    </FixedDocumentSequence>
In the example above the fixed document sequence contains only one document, but It can contain more documents.

"[Content_Type].xml" contains mapping between extensions of package parts and content types described in corresponding XML schemas:

    <?xml version="1.0" encoding="utf-8"?>
    <Types xmlns="http://schemas.openxmlformats.org/package/2006/content-types">
	      <Default Extension="fdseq" ContentType="application/vnd.ms-package.xps-fixeddocumentsequence+xml" />
	      <Default Extension="rels" ContentType="application/vnd.openxmlformats-package.relationships+xml" />
	      <Default Extension="fdoc" ContentType="application/vnd.ms-package.xps-fixeddocument+xml" />
	      <Default Extension="fpage" ContentType="application/vnd.ms-package.xps-fixedpage+xml" />
	      <Default Extension="ODTTF" ContentType="application/vnd.ms-package.obfuscated-opentype" />
	      <Default Extension="png" ContentType="image/png" />
    </Types>

"Document" parts are located in the "Documents" folder and also in their own folder whose name is an index of the document in the "Fixed document sequence" part.

Document’s folder also contains "fpage" or "fixed page" parts and a folder with relationships of the pages.

"FixedDocument.fdoc" contains references on "fixed page" parts and lists of "link targets".
    
    <FixedDocument xmlns="http://schemas.microsoft.com/xps/2005/06">
		    <PageContent Source="Pages/1.fpage">
				    <PageContent.LinkTargets>
					      <LinkTarget Name="Page1" />
					      <LinkTarget Name="Conditions" />
					      <LinkTarget Name="Rfd_Conditions" />
					      <LinkTarget Name="Label2" />
					      ......................................
					  <PageContent.LinkTargets>
		    </PageContent>
		    <PageContent Source="Pages/2.fpage">
		         <PageContent.LinkTargets>
		             <LinkTarget Name="Page2" />
		             <LinkTarget Name="Rectangle" />
		             <LinkTarget Name="peQ5" />
		             ......................................
		         <PageContent.LinkTargets>
		    </PageContent>
		    <PageContent Source="Pages/3.fpage">
		         <PageContent.LinkTargets>
		             <LinkTarget Name="Page3" />
		             <LinkTarget Name="Followup" />
		             <LinkTarget Name="Rfd_Followup" />
		             <LinkTarget Name="Label41" />
		             ......................................
						</PageContent.LinkTargets>
			  </PageContent>
		</FixedDocument>

LinkTarget element defines the named page description element that can be addressed by hyperlink.

"Fixed page" contains one static page description where any graphics element is represented by an XML element with all necessary properties.
Below is the reduced content of the fixed page with an index 1.

    <FixedPage xmlns="http://schemas.microsoft.com/xps/2005/06" xmlns:x="http://schemas.microsoft.com/xps/2005/06/resourcedictionary-key" xml:lang="en-us" Width="784" Height="1024">
				<FixedPage.Resources>
						<ResourceDictionary>
								<ImageBrush x:Key="b0" ViewportUnits="Absolute" TileMode="None" ViewboxUnits="Absolute" Viewbox="0,0,150,84" Viewport="0,0,150,84" ImageSource="/Resources/5acf843b-c331-4268-bedd-1f38575d2cba.png" />
								<ImageBrush x:Key="b1" ViewportUnits="Absolute" TileMode="None" ViewboxUnits="Absolute" Viewbox="0,0,308,222" Viewport="0,0,306.612612612613,221" ImageSource="/Resources/56123998-a878-4552-a78f-652734403449.png" />
								<LinearGradientBrush x:Key="b2" StartPoint="1,1" EndPoint="1,29" ColorInterpolationMode="SRgbLinearInterpolation" MappingMode="Absolute" SpreadMethod="Pad">
		    						<LinearGradientBrush.GradientStops>
		        						<GradientStop Color="sc#0.980392158, 1, 1, 1" Offset="0" />
		        						<GradientStop Color="sc#0.521568656, 1, 1, 1" Offset="1" />
		    						</LinearGradientBrush.GradientStops>
								</LinearGradientBrush>
								<ImageBrush x:Key="b3" ViewportUnits="Absolute" TileMode="None" ViewboxUnits="Absolute" Viewbox="-1.77635683940025E-15,0,30.004187214593,28.0039080669535" Viewport="0,0,34,31.7333333333333" ImageSource="/Resources/1fcae301-7b09-41d4-b09c-adb92c26d9df.png" />
								<ImageBrush x:Key="b4" ViewportUnits="Absolute" TileMode="None" ViewboxUnits="Absolute" Viewbox="0,0,33.92,42.24" Viewport="0,0,33.92,42.24" ImageSource="/Resources/9812220b-fe0b-4df4-946a-391c0ef76f78.png" />
						</ResourceDictionary>
				</FixedPage.Resources>
				<Canvas RenderTransform="0.96150234741784,0,0,0.96150234741784,0,0">
						<Canvas Name="Page1" RenderTransform="1.0400390625,0,0,1.0400390625,0,0">
								<Path Fill="#FFFFFFFF" Data="M0,0L784,0 784,1024 0,1024Z" />
								<Canvas Clip="M0,0L784,0 784,1024 0,1024Z">
									  <Canvas Name="Rfd_Conditions" RenderTransform="1,0,0,1,51,712" />
												<Glyphs Name="Label2" OriginX="517.83" OriginY="22.0533333333333" FontRenderingEmSize="10" FontUri="/Resources/6211f37e-c1a8-4b0a-82b1-9eb64114c039.ODTTF" UnicodeString="Patient Name:" Fill="#FF404040" />
												<Glyphs Name="Label3" OriginX="556.08" OriginY="42.0533333333333" FontRenderingEmSize="10" FontUri="/Resources/6211f37e-c1a8-4b0a-82b1-9eb64114c039.ODTTF" UnicodeString="Acct#:" Fill="#FF404040" />
												<Path Name="Line" Stroke="#FF00529B" StrokeThickness="1" StrokeMiterLimit="10" Fill="#00FFFFFF" RenderTransform="1,0,0,1,41,206" Data="M0,0.5L680,0.5" />
												<Path Name="Image" Fill="{StaticResource b0}" RenderTransform="1,0,0,1,15,7" Data="M0,0L150,0 150,84 0,84Z" />
												<Canvas Name="HxConditionsDissatisfiedPatients" RenderTransform="1,0,0,1,53,714">
														<Path Stroke="#FF000000" StrokeThickness="1" StrokeMiterLimit="10" RenderTransform="0.8,0,0,0.8,2.4,2.4" Data="M0.5,0.5L23.5,0.5 23.5,23.5 0.5,23.5Z" />
														<Glyphs OriginX="33" OriginY="16.16" FontRenderingEmSize="12" FontUri="/Resources/2735f4ff-8c83-44e1-89ed-520ec4c4be53.ODTTF" UnicodeString="Dissatisfied patients" Fill="#FF404040" />
												</Canvas>
												<Path Name="Rectangle3" Stroke="#FF808080" StrokeThickness="1" StrokeMiterLimit="10" Fill="#00FFFFFF" RenderTransform="1,0,0,1,74,951" Data="M0.5,0.5L329.5,0.5 329.5,44.5 0.5,44.5Z" />
												<Canvas Name="Conditions" RenderTransform="1,0,0,1,51,712" />
														<Path Fill="#FF0066CC" Data="M0,12.77L330.4,12.77 330.4,13.47 0,13.47Z" />
												</Canvas>
												<PathGeometry x:Key="all">
										        <PathFigure StartPoint="20,70" IsClosed="true">
										            <PolyLineSegment Points="250,70 250,300 20,300" />
										        </PathFigure>
										        <PathFigure StartPoint="135,70">
										            <ArcSegment Size="115,115" IsLargeArc="true" RotationAngle="0" SweepDirection="Counterclockwise" Point="135,300" />
										            <ArcSegment Size="115,115" IsLargeArc="true" RotationAngle="0" SweepDirection="Counterclockwise" Point="135,70" />
										        </PathFigure>
										        <PathFigure StartPoint="135,70">
										            <PolyQuadraticBezierSegment Points="270,185 135,300" />
										            <PolyQuadraticBezierSegment Points="0,185 135,70" />
										        </PathFigure>
										        <PathFigure StartPoint="250,185">
										            <PolyBezierSegment Points="173.34,85 96.67,285 20,185" />
										            <PolyBezierSegment Points="96.67,85 173.34,285 250,185" />
										        </PathFigure>
										    </PathGeometry>

										</Canvas>
								</Canvas>
						</Canvas>
				</Canvas>
				<Path FixedPage.NavigateUri="http://www.bottomline.com" Fill="#00000000" Data="F1M170,77L500.4,77 500.4,91.58 170,91.58Z" />
		</FixedPage>
		
As we can see there are several graphics elements: "Path", "PathGeometry", and "Glyphs" and elements that group other graphics elements with the same transform and clipping, "Canvas". "Path" and "PathGeometry" can contain vector graphics shape stroked or/and filled with a solid color or complex brush, for example, gradient or image brush. Gradient Brush can be Linear or Radial and Image Brush always contains references on an image in the "Resources" folder. There is now a separate graphics element for a raster image. "Path" element filled with "ImageBrush" is used for this purpose.
> Another notable thing we can find in this page description fragment is that text is contained just in the "Glyphs" element as attribute "unicodeString" instead of as a child of this element as in XML or HTML. Thus, content is not separated from markup. This is why XPS can not be referred to as Markup Languages.

> Syntax of XPS files as well as XML is in Augmented Backus–Naur form (ABNF).

Resources used by the page are located in a separate element "FixedPage.Resources".

Those page resources that have reference on remote (remote for this page not for this XPS file) files, for example, fonts or images,
also have corresponding notes in the relationships file "*.fpage.rels".

    <?xml version="1.0" encoding="utf-8"?>
		<Relationships xmlns="http://schemas.openxmlformats.org/package/2006/relationships">
			<Relationship Type="http://schemas.microsoft.com/xps/2005/06/required-resource" Target="../../../Resources/6211f37e-c1a8-4b0a-82b1-9eb64114c039.ODTTF" Id="R0073733c86464bbd" />
			<Relationship Type="http://schemas.microsoft.com/xps/2005/06/required-resource" Target="../../../Resources/12657e22-f92c-4a63-b836-73270cdb2c34.ODTTF" Id="R0d557b0a44b3469b" />
			<Relationship Type="http://schemas.microsoft.com/xps/2005/06/required-resource" Target="../../../Resources/5acf843b-c331-4268-bedd-1f38575d2cba.png" Id="R031c61ce477c4271" />
			<Relationship Type="http://schemas.microsoft.com/xps/2005/06/required-resource" Target="../../../Resources/2735f4ff-8c83-44e1-89ed-520ec4c4be53.ODTTF" Id="R573b784c29694859" />
			<Relationship Type="http://schemas.microsoft.com/xps/2005/06/required-resource" Target="../../../Resources/56123998-a878-4552-a78f-652734403449.png" Id="R10c1b815f01e4c0c" />
			<Relationship Type="http://schemas.microsoft.com/xps/2005/06/required-resource" Target="../../../Resources/a63cfc17-e44b-47c2-89eb-2f1fed357ae8.ODTTF" Id="R041ee8f892e64451" />
			<Relationship Type="http://schemas.microsoft.com/xps/2005/06/required-resource" Target="../../../Resources/1fcae301-7b09-41d4-b09c-adb92c26d9df.png" Id="R13b12a7d51ce4434" />
			<Relationship Type="http://schemas.microsoft.com/xps/2005/06/required-resource" Target="../../../Resources/9812220b-fe0b-4df4-946a-391c0ef76f78.png" Id="R6ed63a00816c45f5" />
		</Relationships>
		
Resources are stored in folders with the name "Resources". Such folders can be located on different levels of package structure. As a rule, fonts and images are contained there. All fonts have either *.TTF extension for TrueType fonts or *.ODTTF extension for obfuscated TrueType fonts. Obfuscation of fonts is made for suppressing extraction of fonts and using it in other places without permission. Besides of TrueType fonts XPS supports only TrueType fonts collections with *.ODTTC extension. No other font types are supported. Images can be in PNG, JPEG, TIFF or WDP (Windows Media Photo Images) format.
Sometimes among other resources *.dic file is met. It is a Dictionary part. It contains common for documents or pages so-called "remote resources" that don't require separate files. Remote in a sense that they are stored not in a "Document" part but in an external folder. Among these resources can be Brush, PathGeometry, MatrixTransform elements etc. ICC colors that are used in the document also are put as "*.icc" file in the "Resources" folder.
		
### Optional parts of an XPS file.
XPS file can contain additional, non-mandatory, parts for navigating, printing and signing. 

#### Document structure.
Navigation over document parts is realized by "DocumentSructure" part and its child elements "DocumentOutline", "Story", "StoryFragment", 
"Paragraph", "Table" and "NamedElement". Document structure is stored in the Document folder together with pages.

</br>
<p align="center">
	<img src="XPS Document part.png">
</p>
<p align="center">
	<img src="XPS DocumentStructure.png">
</p>
</br>

"DocStructure.struct" file contains DocumentOutline with references on StoryFragments.

    <DocumentStructure xmlns="http://schemas.microsoft.com/xps/2005/06/documentstructure">
 				<DocumentStructure.Outline>
					  <DocumentOutline xml:lang="en-US">
					  		<OutlineEntry OutlineLevel="1" Description="Print Schema Specification" OutlineTarget="../FixedDoc.fdoc#PG_1_LNK_1069"/>
							  <OutlineEntry OutlineLevel="1" Description="Contents" OutlineTarget="../FixedDoc.fdoc#PG_8_LNK_1070"/>
							  <OutlineEntry OutlineLevel="2" Description="About This Specification" OutlineTarget="../FixedDoc.fdoc#PG_24_LNK_1074"/>
							  <OutlineEntry OutlineLevel="2" Description="How This Specification Is Organized"  OutlineTarget="../FixedDoc.fdoc#PG_24_LNK_1075"/>
							  <OutlineEntry OutlineLevel="3" Description="2.1.4.1 &lt;psf:Property&gt;" OutlineTarget="../FixedDoc.fdoc#PG_49_LNK_1124"/>
							  <OutlineEntry OutlineLevel="4" Description="Example 2.1-6. Property syntax example" OutlineTarget="../FixedDoc.fdoc#PG_50_LNK_1125"/>
							  .....................................................................................................................................
						</DocumentOutline>
			  </DocumentStructure.Outline>
			  <Story StoryName="MainStory">
				    <StoryFragmentReference Page="1"/>
					  <StoryFragmentReference Page="2"/>
					  <StoryFragmentReference Page="3"/>
					  .....................................
				</Story>
				<Story StoryName="s1">
				  	<StoryFragmentReference Page="1"/>
				</Story>
				<Story StoryName="s2">
				  	<StoryFragmentReference Page="2"/>
				</Story>
				<Story StoryName="s3">
				  	<StoryFragmentReference Page="3"/>
				</Story>
				......................................
		</DocumentStructure>
		
In the "Fragments" folder story fragments are stored.

<p align="center">
	<img src="XPS DocumentStructure fragments.png">
</p>

Each "Fragment" contains "Paragraphs" with "NamedElements" and "Tables" elements.

    <StoryFragments xmlns="http://schemas.microsoft.com/xps/2005/06/documentstructure">
			 <StoryFragment FragmentType="Content" StoryName="MainStory">
			 		<ParagraphStructure>
				  		<NamedElement NameReference="a5"/>
				      <NamedElement NameReference="a6"/>
				      <NamedElement NameReference="a7"/>
				  </ParagraphStructure>
				  <ParagraphStructure>
				      <NamedElement NameReference="a8"/>
				  </ParagraphStructure>
				  <TableStructure>
					    <TableRowGroupStructure>
							    <TableRowStructure>
								      <TableCellStructure>
									        <ParagraphStructure>
										          <NamedElement NameReference="a28"/>
										          <NamedElement NameReference="a29"/>
									        </ParagraphStructure>
								      </TableCellStructure>
							     		<TableCellStructure>
							     				<ParagraphStructure>
										      		<NamedElement NameReference="a30"/>
										      		<NamedElement NameReference="a31"/>
										      		<NamedElement NameReference="a32"/>
							     				</ParagraphStructure>
							     		</TableCellStructure>
							    </TableRowStructure>
							    <TableRowStructure>
							    		<TableCellStructure>
							     				<ParagraphStructure>
							       					<NamedElement NameReference="a33"/>
							       					<NamedElement NameReference="a34"/>
							     				</ParagraphStructure>
							    		</TableCellStructure>
							     		<TableCellStructure>
							      			<ParagraphStructure>
							       					<NamedElement NameReference="a35"/>
							       					<NamedElement NameReference="a36"/>
							     				</ParagraphStructure>
							     </TableCellStructure>
							    </TableRowStructure>							    
					    </TableRowGroupStructure>
				  </TableStructure>
				  <ParagraphStructure>
				      <NamedElement NameReference="a9"/>
				      <NamedElement NameReference="a10"/>
				  </ParagraphStructure>
				  ...................................................................
			</StoryFragment>
		</StoryFragments>
		
#### Print tickets.
Printing features are implemented via "PrintTicket" parts. It contains printing settings that can be attached to a document sequence, one document or page. "PrintTicket" parts are stored in files with "*_PT.xml" mask where "PT" means PrintTicket. PrintTicket files are located in the "Metadata" folder.

<p align="center">
	<img src="XPS PrintTickets.png">
</p>

Example of PrintTicket.

		<?xml version="1.0" encoding="UTF-8"?>
		<psf:PrintTicket xmlns:psf="http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework"
			xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"
			version="1"
			xmlns:ns0000="http://schemas.microsoft.com/windows/2006/06/printing/printschemakeywords/microsoftxpsdocumentwriter"
			xmlns:psk="http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords">
				<psf:ParameterInit name="ns0000:PageDevmodeSnapshot">
						<psf:Value xsi:type="xsd:string">
								TQBpAGMAcgBvAHMAbwBmAHQAIABYAFAAUwAgAEQAb........=
						</psf:Value>
				</psf:ParameterInit>
				<psf:ParameterInit name="psk:JobCopiesAllDocuments">
						<psf:Value xsi:type="xsd:integer">1</psf:Value>
				</psf:ParameterInit>
				<psf:Feature name="psk:PageMediaSize">
						<psf:Option name="psk:ISOA4">
								<psf:ScoredProperty name="psk:MediaSizeWidth">
										<psf:Value xsi:type="xsd:integer">210000</psf:Value>
								</psf:ScoredProperty>
								<psf:ScoredProperty name="psk:MediaSizeHeight">
										<psf:Value xsi:type="xsd:integer">297000</psf:Value>
								</psf:ScoredProperty>
						</psf:Option>
				</psf:Feature>
				<psf:Feature name="psk:JobInputBin">
						<psf:Option name="psk:AutoSelect"/>
				</psf:Feature>
				<psf:Feature name="ns0000:JobInterleaving">
						<psf:Option name="ns0000:OFF"/>
				</psf:Feature>
				<psf:Feature name="ns0000:JobImageType">
						<psf:Option name="ns0000:JPEGMed"/>
				</psf:Feature>
				<psf:Feature name="psk:PageOrientation">
						<psf:Option name="psk:Portrait"/>
				</psf:Feature>
				<psf:Feature name="psk:DocumentCollate">
						<psf:Option name="psk:Uncollated"/>
				</psf:Feature>
				<psf:Feature name="psk:PageResolution">
						<psf:Option name="ns0000:Option1">
								<psf:ScoredProperty name="psk:ResolutionX">
										<psf:Value xsi:type="xsd:integer">600</psf:Value>
								</psf:ScoredProperty>
								<psf:ScoredProperty name="psk:ResolutionY">
										<psf:Value xsi:type="xsd:integer">600</psf:Value>
								</psf:ScoredProperty>
						</psf:Option>
				</psf:Feature>
				<psf:Feature name="psk:PageOutputColor">
						<psf:Option name="psk:Color">
								<psf:ScoredProperty name="psk:DeviceBitsPerPixel">
										<psf:Value xsi:type="xsd:integer">24</psf:Value>
								</psf:ScoredProperty>
								<psf:ScoredProperty name="psk:DriverBitsPerPixel">
										<psf:Value xsi:type="xsd:integer">24</psf:Value>
								</psf:ScoredProperty>
						</psf:Option>
				</psf:Feature>
		</psf:PrintTicket>

#### Thumbnails.

In "Metadata" folders also thumbnails images are stored if it are.

<p align="center">
	<img src="XPS Thumbnails.png">
</p>

#### SignatureDefinitions.

"SignatureDefinitions" part allows sign, request and validate signing of arbitrary XPS documents parts in accordance to Signing Policy defined in 
"SignatureDefinitions" part.

<p align="center">
	<img src="XPS SignatureDefinitions.png">
</p>

## Support for fonts, colors and images in XPS documents

</br>
<p align="center">
<table>
<tr>
<td style="background: white; border-color: white">
<p align="center"><b>Font formats</b></p>
<img width=300/>
<p align="center">
- Compact Fonts (CFF)
</br>
- TrueType
</p>
</td>
<td style="background: white; border-color: white">
<p align="center"><b>Color space types</b></p>
<img width=300/>
<p align="center">
- sRGB
</br>
- scRGB
</br>
- CMYK
</br>
- N-Channel
</br>
- ICC version 2
</p>
</td>
<td style="background: white; border-color: white">
<p align="center"><b>Image formats</b></p>
<img width=300/>
<p align="center">
- JPEG
</br>
- PNG
</br>
- TIFF
</br>
- Windows Media Photo Image (WDP)
</p>
</td>
</tr>
</table>
</p>

XPS supports only OpenType font format, that is extended by Microsoft TrueType format combining TrueType Font (TTF) and Compact Font (CFF) formats.

## How do I open an XPS file?

XPS file can be opened with Microsoft's XPS Viewer. It is a standard Windows component beginning with Windows Vista.
An Alternative way is to view the XPS file with [Aspose.Page XPS Viewer](https://products.aspose.app/page/viewer/xps) web application.

## Can I convert an XPS file to a PDF?

The quickest way to convert XPS files to PDF is to use
[Aspose.Page Conversion](https://products.aspose.app/page/conversion/xps) web application. Aspose XPS converter supports XPS to PDF, DOC, DOCX, HTML, TEX, SVG, PNG, JPG, TIFF, BMP conversions.
If you are a developer and want to use our library for such conversions, learn [PDLs converters](/page/net/convert/) article 
to find the illustrated with code snippets examples on how to do the conversion.

## Can I open an XPS file in Word?

It is not possible directly, but you can convert an XPS file to Word document via [Aspose.Page Conversion](https://products.aspose.app/page/conversion/xps-to-word) web application and then open it Microsoft Word text editor.

## Can XPS files be converted to Excel?

Yes, you can convert XPS to Excel online in [Aspose.Page Conversion](https://products.aspose.app/page/conversion/xps-to-excel) web application.
XPS document will be recognized as a table. Pictures are not transferred to the resulting XLSX file.

## How do I open an XPS file in Photoshop?

It is not possible directly, but you can open either raster image files resulting from XPS to image (JPG, PNG, TIFF, BMP) conversion in
[Aspose.Page Conversion](https://products.aspose.app/page/conversion/xps) web app or you can just open XPS file with ZIP utility, as it was 
described earlier, find among resources in "Resources" folders necessary image, extract it in your folder and, finally, open it in Adobe Photoshop.

## Is XPS better than PDF?

It depends on your needs. See an article [Comparison of Page Description Languages](/page/net/pdls-comparison). Hope it helps you to make the right decision.

## How do I open an XPS file on my phone?
You can onpen an XPS file in any browser with [Aspose.Page XPS Viewer](https://products.aspose.app/page/viewer/xps) web application.


