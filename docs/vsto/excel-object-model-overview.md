---
title: Excel 对象模型概述
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Worksheet object
- Range object
- object models [Office development in Visual Studio], Excel
- object models [Office development in Visual Studio], Office
- Workbook class
- objects [Office development in Visual Studio], Office object models
- Excel object model
- Office object models
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8ca93cae45eed272b683275896efcf83229ca9a3
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49880788"
---
# <a name="excel-object-model-overview"></a>Excel 对象模型概述
  若要开发使用 Microsoft Office Excel 的解决方案，可与由 Excel 对象模型提供的对象进行交互。 本主题介绍最重要的对象：  
  
- <xref:Microsoft.Office.Interop.Excel.Application>  
  
- <xref:Microsoft.Office.Interop.Excel.Workbook>  
  
- <xref:Microsoft.Office.Interop.Excel.Worksheet>  
  
- <xref:Microsoft.Office.Interop.Excel.Range>  
  
  [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
  对象模型紧跟用户界面。 <xref:Microsoft.Office.Interop.Excel.Application> 对象表示整个应用程序，并且每个 <xref:Microsoft.Office.Interop.Excel.Workbook> 对象都包含 `Worksheet` 对象的集合。 在这里，表示单元格的主要抽象是 <xref:Microsoft.Office.Interop.Excel.Range> 对象，它使你能够使用单独的单元格或单元格组。  
  
  除 Excel 对象模型中，在 Visual Studio 中的 Office 项目还提供*主机项*并*主机控件*可扩展 Excel 对象模型中的一些对象。 主机项和主机控件的行为类似于它们扩展的 Excel 对象，但它们还具有其他功能（如数据绑定功能）和其他事件。 有关详细信息，请参阅[通过使用扩展的对象自动化 Excel](../vsto/automating-excel-by-using-extended-objects.md)并[主机项和主机控件概述](../vsto/host-items-and-host-controls-overview.md)。  
  
  本主题概要介绍 Excel 对象模型。 资源可从中了解整个 Excel 对象模型的详细信息，请参阅[使用 Excel 对象模型文档](#ExcelOMDocumentation)。  
  
  ![视频链接](../vsto/media/playvideo.gif "链接至视频")相关的视频演示，请参阅[如何实现： 使用事件处理程序在 Excel 2007 外接程序？](http://go.microsoft.com/fwlink/?LinkID=130291)，并[如何实现： 使用形状以创建气泡图在 Excel？](http://go.microsoft.com/fwlink/?LinkID=130313).  
  
## <a name="access-objects-in-an-excel-project"></a>访问 Excel 项目中的对象  
 时为 Excel 创建新的 VSTO 外接程序项目，Visual Studio 会自动创建*ThisAddIn.vb*或*ThisAddIn.cs*代码文件。 可以通过使用 `Me.Application` 或 `this.Application` 访问应用程序对象。  
  
 为 Excel 创建新的文档级项目时，可选择创建新的 Excel 工作簿或 Excel 模板项目。 Visual Studio 在新的 Excel 项目中为工作簿和模板项目自动创建以下代码文件。  
  
|Visual Basic|C#|  
|------------------|---------|  
|ThisWorkbook.vb|ThisWorkbook.cs|  
|Sheet1.vb|Sheet1.cs|  
|Sheet2.vb|Sheet2.cs|  
|Sheet3.vb|Sheet3.cs|  
  
 可以在项目中使用 `Globals` 类来从各个类的外部访问 `ThisWorkbook`、`Sheet1`、`Sheet2` 或 `Sheet3`。 有关详细信息，请参阅[对 Office 项目中的对象的全局访问](../vsto/global-access-to-objects-in-office-projects.md)。 下面的示例调用<xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A>方法`Sheet1`而不考虑是否将代码放置在之一`Sheet` *n*类或`ThisWorkbook`类。  
  
 [!code-csharp[Trin_VstcoreExcelAutomation#82](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#82)]
 [!code-vb[Trin_VstcoreExcelAutomation#82](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#82)]  
  
 由于 Excel 文档中的数据已高度结构化，因此该对象模型是分层模型且非常简单。 Excel 提供了数百个对象可能会希望在与其进行交互，但可以通过将重点放在可用的对象的一小部分来获取的对象模型的一个不错的起点。 这些对象包括以下四种：  
  
- 应用程序  
  
- Workbook  
  
- Worksheet  
  
- 范围  
  
  许多使用 Excel 完成的工作都是围绕这四种对象及其成员进行的。  
  
### <a name="application-object"></a>应用程序对象  
 Excel <xref:Microsoft.Office.Interop.Excel.Application> 对象表示 Excel 应用程序本身。 <xref:Microsoft.Office.Interop.Excel.Application> 对象公开了大量有关正在运行的应用程序、应用于该实例的选项以及在该实例内部开启的当前用户对象的信息。  
  
> [!NOTE]  
>  不应将 Excel 中 <xref:Microsoft.Office.Interop.Excel.ApplicationClass.EnableEvents%2A> 对象的 <xref:Microsoft.Office.Interop.Excel.Application> 属性设置为 **false**。 将此属性设置为 false 可防止 Excel 引发任何事件，包括主机控件的事件。  
  
### <a name="workbook-object"></a>工作簿对象  
 <xref:Microsoft.Office.Interop.Excel.Workbook> 对象表示 Excel 应用程序中的单个工作簿。  
  
 Visual Studio 中的 Office 开发工具通过提供 <xref:Microsoft.Office.Interop.Excel.Workbook> 类型来扩展 <xref:Microsoft.Office.Tools.Excel.Workbook> 对象。 此类型使你可以访问 <xref:Microsoft.Office.Interop.Excel.Workbook> 对象的所有功能。 有关详细信息，请参阅[工作簿主机项](../vsto/workbook-host-item.md)。  
  
### <a name="worksheet-object"></a>Worksheet 对象  
 <xref:Microsoft.Office.Interop.Excel.Worksheet> 对象是 <xref:Microsoft.Office.Interop.Excel.Worksheets> 集合的成员。 <xref:Microsoft.Office.Interop.Excel.Worksheet> 的许多属性、方法和事件与由 <xref:Microsoft.Office.Interop.Excel.Application> 或 <xref:Microsoft.Office.Interop.Excel.Workbook> 对象提供的成员相同或类似。  
  
 Excel 提供一个 <xref:Microsoft.Office.Interop.Excel.Sheets> 集合作为 <xref:Microsoft.Office.Interop.Excel.Workbook> 对象的属性。 <xref:Microsoft.Office.Interop.Excel.Sheets> 集合的每个成员都是 <xref:Microsoft.Office.Interop.Excel.Worksheet> 或 <xref:Microsoft.Office.Interop.Excel.Chart> 对象。  
  
 Visual Studio 中的 Office 开发工具通过提供 <xref:Microsoft.Office.Interop.Excel.Worksheet> 类型来扩展 <xref:Microsoft.Office.Tools.Excel.Worksheet> 对象。 此类型使你可以访问 <xref:Microsoft.Office.Interop.Excel.Worksheet> 对象的所有功能以及承载托管控件和处理新事件等新功能。 有关详细信息，请参阅[工作表主机项](../vsto/worksheet-host-item.md)。  
  
### <a name="range-object"></a>Range 对象  
 <xref:Microsoft.Office.Interop.Excel.Range> 对象是你将在 Excel 应用程序中使用最多的对象。 在可以操作 Excel 内的任何区域之前，必须将其表达为 <xref:Microsoft.Office.Interop.Excel.Range> 对象，并使用该范围的方法和属性。 一个 <xref:Microsoft.Office.Interop.Excel.Range> 对象，表示一个单元格、行、列、包含一个或多个单元格块的单元格选定区域（选定区域可能是连续的，也可能不是连续的）或甚至多个工作表上的一组单元格）。  
  
 Visual Studio 通过提供 <xref:Microsoft.Office.Tools.Excel.NamedRange> 和 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 类型来扩展 <xref:Microsoft.Office.Interop.Excel.Range> 对象。 这些类型具有与 <xref:Microsoft.Office.Interop.Excel.Range> 对象相同的大部分功能以及数据绑定功能等新功能和新事件。 有关详细信息，请参阅[NamedRange 控件](../vsto/namedrange-control.md)并[XmlMappedRange 控件](../vsto/xmlmappedrange-control.md)。  
  
##  <a name="ExcelOMDocumentation"></a> 使用 Excel 对象模型文档  
 有关 Excel 对象模型的完整信息，可以参考 Excel 主互操作程序集 (PIA) 引用和 VBA 对象模型引用。  
  
### <a name="primary-interop-assembly-reference"></a>主互操作程序集引用  
 Excel PIA 参考文档介绍 Excel 的主互操作程序集中的类型。 本文档可从以下位置： [Excel 2010 主互操作程序集引用](http://go.microsoft.com/fwlink/?LinkId=189585)。  
  
 有关设计的 Excel PIA，例如在 PIA 和如何实现 PIA 中的事件中类和接口之间的差别的详细信息请参阅[的中的 Office 主互操作程序集类和接口概述](http://go.microsoft.com/fwlink/?LinkId=189592).  
  
### <a name="vba-object-model-reference"></a>VBA 对象模型引用  
 VBA 对象模型引用在 Excel 对象模型被公开到 Visual Basic for Applications (VBA) 代码时记录该对象模型。 有关详细信息，请参阅[Excel 2010 对象模型引用](http://go.microsoft.com/fwlink/?LinkId=199768)。  
  
 VBA 对象模型引用中的所有对象和成员都对应于 Excel PIA 中的类型和成员。 例如，VBA 对象模型引用中的工作表对象对应于<xref:Microsoft.Office.Interop.Excel.Worksheet>Excel PIA 中的对象。 虽然 VBA 对象模型引用提供大多数属性、方法和事件的代码示例，但如果要在使用 Visual Studio 创建的 Excel 项目中使用本引用中的 VBA 代码，则必须将其转换为 Visual Basic 或 Visual C# 代码。  
  
### <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|-----------|-----------------|  
|[Excel 解决方案](../vsto/excel-solutions.md)|说明可以如何创建 Microsoft Office excel 的文档级自定义项和 VSTO 外接程序。|  
|[使用范围](../vsto/working-with-ranges.md)|提供演示如何使用范围执行常见任务的示例。|  
|[使用工作表](../vsto/working-with-worksheets.md)|提供演示如何使用工作表执行常见任务的示例。|  
|[使用工作簿](../vsto/working-with-workbooks.md)|提供演示如何使用工作簿执行常见任务的示例。|  
  
  