---
title: 默认命令、 组和工具栏位置 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands [Visual Studio], default groups
- toolbars [Visual Studio], default
- commands [Visual Studio], default editor
- command groups
- commands [Visual Studio], default IDE
- commands [Visual Studio], default product
ms.assetid: 35342110-d639-4577-8367-00b21dcc6f07
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: da5716460c428098b2b6cc3bb78a51c3831201b2
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2018
ms.locfileid: "39498225"
---
# <a name="default-command-group-and-toolbar-placement"></a>默认命令、 组和工具栏位置
有关产品一致性和稳定性，UI 会默认情况下，显示特定命令组和[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]为命令和命令组提供了定义。 Vspackage 还可以使用标准命令和命令组。  
  
 默认命令组划分为三个类别： IDE 命令、 产品命令和编辑器命令。  
  
## <a name="default-ide-commands"></a>默认 IDE 命令  
 默认 IDE 工具栏包括共享的所有产品中包含的命令[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。 其中包括与通用项目操作，如相关的命令**保存**命令和**添加项**命令。 Vspackage 不应将添加到或减去此工具栏中，有一个例外： 如果产品或 VSPackage 将添加一个新的工具窗口，则应将窗口添加到可用的工具窗口的列表上**视图**菜单。 新产品或 Vspackage 可以添加其自己的工具栏。  
  
## <a name="default-product-commands"></a>默认产品命令  
 每个产品可以提供具有其自身包含重要和常用命令的默认工具栏的 IDE。 最好是，但是，若要使用现有的菜单和工具栏尽可能放入其他特定于任务的工具栏根据需要。  
  
 工具栏的 priority 字段确定其行位置。 零个优先级菜单栏下的第三行 （第 3 行），将工具栏 （第 1 行） 和**标准**工具栏 （第 2 行）。 因此，其他工具栏将显示在行 （优先级 + 3）。 后续工具栏置于同一行中，当空间;否则，它们将自动移到下一行。  
  
## <a name="default-editor-commands"></a>默认编辑器命令  
 提供自定义编辑器的 VSPackage 应提供一个包含最重要，在该编辑器中常用命令的默认工具栏。 在编辑器处于活动状态，并且应在编辑器处于不活动状态时隐藏时，应显示编辑器工具栏。 以控制此可见性`VisibilityConstraints`的元素 *.vsct*文件。  
  
 编辑器工具栏应置于 IDE 和产品工具栏下方。  
  
## <a name="see-also"></a>请参阅  
 [IDE 定义的命令、 菜单和组](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)   
 [Vspackage 如何添加用户界面元素](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)