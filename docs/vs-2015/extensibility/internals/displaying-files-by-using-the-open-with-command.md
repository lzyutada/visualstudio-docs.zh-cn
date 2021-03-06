---
title: 通过使用命令打开显示文件 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- project types, supporting Open With command
- Open With command
- persistence, supporting Open With command
ms.assetid: 53794bc3-1b73-4d40-954e-cfade1abddcf
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 716e9f1551681b9e194bd300522f55ab5e927dab
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51816446"
---
# <a name="displaying-files-by-using-the-open-with-command"></a>使用“通过命令打开”显示文件
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

一个项目可以询问要显示在 IDE**打开**对话框。 此请求会提示用户打开具有的标准编辑器选择的文件。 以下步骤介绍了此过程。  
  
1.  项目调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>，将值指定为 OSE_UseOpenWithDialog`OSEOpenDocEditor`参数。  
  
2.  基于文档的文件扩展名，IDE 确定列出注册表中的编辑器打开指定的文档，并显示此信息**打开**对话框。  
  
    > [!NOTE]
    >  让中必须包含一个内部函数编辑器的项目**打开**对话框必须用于每个此类编辑器注册编辑器工厂。 内部函数编辑器仅函数以及特定类型的项目，它的实现中强制实施<xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>方法。 IDE 提供核心文本编辑器和二进制编辑器内置编辑器工厂。 IDE 还创建编辑器工厂的实例代表每个已注册的 Windows 文件关联。 此类文件的一个示例是 Microsoft Word。  
  
3.  只要用户选择某个项从**打开**对话框中，然后在 IDE 打开文档通过调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>方法。 有关详细信息，请参阅[如何： 打开标准编辑器](../../extensibility/how-to-open-standard-editors.md)。  
  
## <a name="see-also"></a>请参阅  
 [打开和保存项目项](../../extensibility/internals/opening-and-saving-project-items.md)   
 [使用打开文件命令显示文件](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)   
 [如何：打开标准编辑器](../../extensibility/how-to-open-standard-editors.md)

