---
title: 记录 Windows |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio SDK, document windows
ms.assetid: 50081d48-987f-43db-8bf9-51b7cf76e9c0
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c620de56e3658c3aef33da136930221578b9be4a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472082"
---
# <a name="document-windows"></a>文档窗口
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[文档 Windows](https://docs.microsoft.com/visualstudio/extensibility/internals/document-windows)。  
  
在 Visual Studio 中，*文档窗口*是带边框的子窗口的多文档界面 (MDI) 窗口与相关联。 文档窗口通常用于显示和修改源代码或文本，但它们还可以托管其他功能的类型。 文档窗口：  
  
-   可以将组织中的父代 MDI 中单独的水平或垂直选项卡组中，以便可以同时查看多个文件。  
  
-   可以按任意顺序在 MDI 父停靠。  
  
-   可以自由浮动。  
  
-   链接到其他 MDI 窗口的选项卡顺序。  
  
 用于分组的命令，在文档窗口选项卡的快捷菜单上可以找到停靠和浮动。  
  
 有关在 Visual Studio 中的窗口行为的详细信息，请参阅[自定义窗口布局](../../ide/customizing-window-layouts-in-visual-studio.md)。  
  
## <a name="document-window-implementation"></a>文档窗口实现  
 通过实现编辑器创建文档窗口。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>接口用于创建实例化一个编辑器的一部分的文档窗口。 有关详细信息，请参阅[在编辑器中的旧接口](../../extensibility/legacy-interfaces-in-the-editor.md)。  
  
> [!NOTE]
>  若要提供向后和向前导航点在窗口中的，实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsBackForwardNavigation>接口。 在文本编辑器使用文本标记来标识文档中的导航点。  
  
## <a name="the-running-document-table"></a>运行文档表  
 IDE 使用正在运行的 document 表 (RDT) 来跟踪每个文档窗口的状态。 RDT 是哪个文档通过 windows 通知的事件，如解决方案已关闭时或编辑文件的机制。 有关详细信息，请参阅[运行文档表](../../extensibility/internals/running-document-table.md)。  
  
## <a name="see-also"></a>请参阅  
 [文档加载延迟](../../extensibility/internals/delayed-document-loading.md)
