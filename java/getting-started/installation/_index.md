---
title: Installation | Java
linktitle: Installation
type: docs
weight: 50
url: /java/installation/
---

## **Installing Aspose.Page for Java from Aspose Repository**
Aspose hosts all Java APIs on [Aspose Artifactory](https://repository.aspose.com/webapp/#/artifacts/browse/tree/General/repo/com/aspose/). You can easily use [Aspose.Page for Java](https://repository.aspose.com/webapp/#/artifacts/browse/tree/General/repo/com/aspose/aspose-page) API directly in your Maven Projects with simple configurations.
### **Specify Aspose Repository Configuration**
First, you need to specify the Aspose Repository configuration/location in your Maven pom.xml as follows:

{{< highlight java >}}

 <repositories>

     <repository>

         <id>snapshots</id>

         <name>repo</name>

         <url>http://repository.aspose.com/repo/</url>

     </repository>

</repositories>

{{< /highlight >}}
### **Define Aspose.Page for Java API Dependency**
Then define Aspose.Page for Java API dependency in your pom.xml as follows:

{{< highlight java >}}

 <dependencies>

    <dependency>

        <groupId>com.aspose</groupId>

        <artifactId>aspose-page</artifactId>

        <version>19.12</version>

    </dependency>

</dependencies>

{{< /highlight >}}

After performing the above steps, Aspose.Page for Java dependency will finally be defined in your Maven-based project.
