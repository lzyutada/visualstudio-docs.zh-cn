---
title: 如何： 以编程方式创建新的 Visio 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], creating Visio documents
- documents [Office development in Visual Studio], creating Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4142ebe86ea69fbb0a74f25c2a7053a60c527cdb
ms.sourcegitcommit: be938c7ecd756a11c9de3e6019a490d0e52b4190
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50671555"
---
# <a name="how-to-programmatically-create-new-visio-documents"></a>如何： 以编程方式创建新的 Visio 文档
  创建新的 Microsoft Office Visio 绘图文档时，会将其添加到所打开 Visio 文档的 `Microsoft.Office.Interop.Visio.Documents` 集合中。 随后，`Microsoft.Office.Interop.Visio.Documents.Add` 方法会创建一个新的 Visio 绘图文档。 有关详细信息，请参阅 [Microsoft.Office.Interop.Visio.Documents.Add](/office/vba/api/Visio.Documents.Add) 方法的 VBA 参考文档。  
  
## <a name="create-new-blank-documents"></a>创建新的空白文档  
  
### <a name="to-create-a-new-document"></a>创建新文档  
  
-   使用 `Microsoft.Office.Interop.Visio.Documents.Add` 方法创建一个不基于模板的新空白文档。  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#1](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#1](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#1)]  
  
## <a name="create-documents-copied-from-existing-documents"></a>创建从现有文档复制文档  
 `Microsoft.Office.Interop.Visio.Documents.Add` 方法可创建从现有 Visio 文档复制而来的新文档。 你必须提供相应关系图的文件名和完全限定路径。  
  
### <a name="to-create-a-new-document-that-is-copied-from-an-existing-document"></a>创建从现有文档复制而来的新文档  
  
-   调用 `Microsoft.Office.Interop.Visio.Documents.Add` 方法并指定 Visio 关系图的路径。  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#2](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#2](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#2)]  
  
## <a name="create-stencils-copied-from-existing-stencils"></a>创建从现有模具复制的模具  
 [Microsoft.Office.Interop.Visio.Documents.Add](/office/vba/api/Visio.Documents.Add) 方法可创建从现有 Visio 模具复制而来的新模具。 你必须提供相应模具的文件名和完全限定路径。  
  
### <a name="to-create-a-new-stencil-that-is-copied-from-an-existing-stencil"></a>创建从现有模具复制而来的新模具  
  
-   调用 `Microsoft.Office.Interop.Visio.Documents.Add` 方法并指定相应模具的路径。  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#3](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#3](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#3)]  
  
## <a name="create-documents-based-on-existing-templates"></a>创建基于现有模板的文档  
 `Microsoft.Office.Interop.Visio.Documents.Add`方法可创建新文档 ( *.vsd*文件)，它基于现有 Visio 模板 ( *.vst*文件)。 此方法会复制作为模板工作区一部分的模具、样式和设置。 你必须提供模板的文件名称和完全限定路径。  
  
### <a name="to-create-a-new-document-that-is-based-on-an-existing-template"></a>创建基于现有模板的新文档  
  
-   调用 `Microsoft.Office.Interop.Visio.Documents.Add` 方法并指定相应模板的路径。  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#4](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#4)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#4](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#4)]  
  
## <a name="compile-the-code"></a>编译代码  
 此代码示例要求满足以下条件：  
  
-   名为的 Visio 文档`myDrawing.vsd`必须位于一个名为目录`Test`中*我的文档*文件夹 （对于 Windows XP 及更早版本） 或*文档*文件夹 （对于 Windows Vista)。  
  
-   名为的 Visio 文档`myStencil.vss`必须位于一个名为目录`Test`中*我的文档*文件夹 （对于 Windows XP 及更早版本） 或*文档*文件夹 （对于 Windows Vista)。  
  
-   名为的 Visio 文档`myTemplate.vst`必须位于一个名为目录`Test`中*我的文档*文件夹 （对于 Windows XP 及更早版本） 或*文档*文件夹 （对于 Windows Vista)。  
  
## <a name="see-also"></a>请参阅  
 [Visio 解决方案](../vsto/visio-solutions.md)   
 [Visio 对象模型概述](../vsto/visio-object-model-overview.md)   
 [如何： 以编程方式打开 Visio 文档](../vsto/how-to-programmatically-open-visio-documents.md)   
 [如何： 以编程方式关闭 Visio 文档](../vsto/how-to-programmatically-close-visio-documents.md)   
 [如何： 以编程方式保存 Visio 文档](../vsto/how-to-programmatically-save-visio-documents.md)   
 [如何： 以编程方式打印 Visio 文档](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  