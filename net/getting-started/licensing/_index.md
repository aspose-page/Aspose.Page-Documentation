---
title: Licensing
type: docs
weight: 60
url: /net/licensing/
---

## **Evaluation Version Limitations**
We want our customers to test our components thoroughly before buying so the evaluation version allows you to use it as you would normally. However, the unlicensed product:

- Allows converting of PostScript files which size is no more than 500 KB and resulting PDF document in such cases will contain evaluation mark. 
- Will not allow manipulating more than 4 XPS elements and resulting document or image in such cases will also contain evaluation mark i.e. "**Evaluation Only. Created with Aspose.Page. Copyright 2002-2019 Aspose Pty Ltd**" at the top.
## **Apply License using File or Stream Object**
The license can be loaded from a file or stream object. The easiest way to set a license is to put the license file in the same folder as the Aspose.Page.dll file and specify the file name, without a path, as shown in the example below.

{{% alert color="primary" %}} 

If you use are using any other Aspose for .NET component along with Aspose.Page for .NET, please specify the namespace for License like Aspose.Page.License.

{{% /alert %}} 
### **Loading a License from File**
The easiest way to apply a license is to put the license file in the same folder as the Aspose.Page.dll file and specify just the file name without a path.



{{< gist "aspose-com-gists" "6f0d8b5420af1af6af2d064587dd6803" "Examples-Aspose.Page.Examples.CSharp-GettingStarted-LoadLicenseFromFile-1.cs" >}}

When you call the SetLicense method, the license name that you pass should be that of your license file. For example, if you change the license file name to "Aspose.Page.lic.xml" pass that file name to the Page.SetLicense(…) method.
### **Loading a License from a Stream Object**
The following example shows how to load a license from a stream.

{{< gist "aspose-com-gists" "6f0d8b5420af1af6af2d064587dd6803" "Examples-Aspose.Page.Examples.CSharp-GettingStarted-LoadLicenseFromStreamObject-1.cs" >}}
### **Using as Embedded Resource**
To apply a license, you can [load it from file or stream](). Another neat way of packaging the license with your application is to include it as an embedded resource into one of the assemblies that calls Aspose.Page for .NET.

To include the file as an embedded resource:

1. In Visual Studio .NET, include the .lic file into the project by clicking the **File** menu and selecting **Add Existing Item**.
1. Select the file in the Solution Explorer.
1. In the Properties window, set the **Build Action** to **Embedded Resource**.

MergedAPI is the application's default namespace.



{{< gist "aspose-xps" "f5c734fb2e994c809bd907e3c9c6a009" "Examples-CSharp-GettingStarted-SetLicenseUsingEmbeddedResource-1.cs" >}}


One point which needs consideration - Please note that the embedded resources are included in assembly the way they are added i.e. if you add text file as an embedded resource in the application and open the resultant EXE in notepad, you will see the exact contents of a text file. So when using license file as an embedded resource, anyone can open a .exe file in some simple text editor and see/extract the contents of embedded license.

Therefore, in order to put an extra layer of security when embedding the license with the application, you can compress/encrypt license and after that, you can embed it into the assembly. A free utility DotNetZip (<http://dotnetzip.codeplex.com/>) can help to fulfil this requirement. Suppose we have Aspose.Total.NET.lic license file, so let's make Aspose.Total.NET.lic.zip with password test and embed this zip file into solution. The following code snippet can be used to initialize the license:



{{< gist "aspose-com-gists" "6f0d8b5420af1af6af2d064587dd6803" "Examples-Aspose.Page.Examples.CSharp-GettingStarted-SetLicenseUsingEmbeddedResource-1.cs" >}}
