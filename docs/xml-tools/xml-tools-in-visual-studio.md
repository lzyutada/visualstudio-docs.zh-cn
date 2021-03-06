---
title: XML 工具
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
f1_keywords:
- vb.xmldesigner
helpviewer_keywords:
- XML [Visual Studio], resources
- Enterprise Templates, XML and
- discovery files, XML
- server controls, XML and
- Web server controls, XML
- XSL
- XML [Visual Studio], data sources
- XML schemas
- XML [Visual Studio], SGML relationship to
- CSS, style sheets for XML
- XML [Visual Studio], .NET Framework classes
- data [Visual Studio], XML
- classes [Visual Studio], XML
- style sheets, for XML
- Web services
- SGML, XML
- XML [Visual Studio]
- datasets [Visual Basic], XML Schemas
- XSD schemas
- XSL, style sheets
- XMLDataDocument class
ms.assetid: 1fd5de47-2d61-4180-9539-c2c4bf9ab768
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f87c06e2bfc3885c0f52230e927933ff3cb0d87c
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53054993"
---
# <a name="xml-tools-in-visual-studio"></a>Visual Studio 中的 XML 工具

*可扩展标记语言 (XML)* 是一种标记语言，用于描述数据提供一种格式。 该语言使跨越多个平台进行更准确的内容声明和获得更有意义的搜索结果变得更加容易。 此外，XML 实现了表示与数据的分离。 例如，在 HTML 中，使用标记来告诉浏览器将数据显示为粗体或斜体；而在 XML 中，标记只用于描述数据，例如城市名、温度和大气压。 在 XML 中，使用样式表等可扩展样式表语言 (XSL) 和级联样式表 (CSS) 来呈现在浏览器中的数据。 XML 将数据与表示及处理相分离。 这一特点使你能够通过应用不同的样式表和应用程序，按照所需的方式显示和处理数据。

XML 是为在 Web 上传送而优化了的 SGML 的子集。 它是由万维网联合会 (W3C) 定义的。 此标准化确保了结构化的数据是统一和独立于应用程序或供应商。

XML 是核心的 Visual Studio 和.NET Framework 的许多功能。 以下文章列表名称的工具和 Visual Studio 和.NET Framework 中提供的功能与 XML 相关。

有关详细信息，请参阅<xref:System.Xml?displayProperty=fullName>文档。

## <a name="reference"></a>参考

[Microsoft.VisualStudio.XmlEditor](http://go.microsoft.com/fwlink/?LinkID=165699)公开[XML 编辑器](http://go.microsoft.com/fwlink/?LinkId=228249)分析通过树[System.Xml.Linq](http://go.microsoft.com/fwlink/?LinkId=228250)为任意 XML 文档。

[XML 标准参考](https://msdn.microsoft.com/79c78508-c9d0-423a-a00f-672e855de401)提供有关 XML 技术，包括 XML、 文档类型定义 (DTD)、 XML 架构定义语言 (XSD) 和 XSLT 的信息。

<xref:System.Xml?displayProperty=fullName> 介绍类和其他元素构成<xref:System.Xml>命名空间，并对每个项提供更多详细信息的链接。

<xref:System.Xml.Serialization?displayProperty=fullName> 介绍类和其他元素构成<xref:System.Xml.Serialization>命名空间并提供指向有关每个项的更多详细信息。

## <a name="related-sections"></a>相关章节

[XML 文档对象模型 (DOM)](/dotnet/standard/data/xml/xml-document-object-model-dom)描述如何<xref:System.Xml.XmlDocument>和及其关联的类符合 W3C 文档对象模型 (Core) 等级 1 和 2 级命名空间支持规范。

[处理 XML 数据与 XmlReader 和 XmlWriter](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc189001\(v\=vs.95\))

[XSLT 转换](/dotnet/standard/data/xml/xslt-transformations)描述如何<xref:System.Xml.Xsl.XslCompiledTransform>类实现 XSLT 1.0 建议。

[处理 XML 数据使用 XPath 数据模型](/dotnet/standard/data/xml/process-xml-data-using-the-xpath-data-model)描述如何<xref:System.Xml.XPath.XPathNavigator>类可以处理 XML 数据存储在<xref:System.Xml.XPath.XPathDocument>或<xref:System.Xml.XmlDocument>对象。 <xref:System.Xml.XPath.XPathNavigator> 类以 XQuery 1.0 和 XPath 2.0 数据模型为基础，可用于导航和编辑 XML 数据。

[XML 架构对象模型 (SOM)](/dotnet/standard/data/xml/xml-schema-object-model-som)说明了用来创建和操作 XML 架构，通过提供的类<xref:System.Xml.Schema.XmlSchema>类来加载和编辑架构。