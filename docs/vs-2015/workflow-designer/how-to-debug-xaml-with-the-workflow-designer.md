---
title: 如何： 调试与工作流设计器的 XAML |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 7ac99d5bcacb937db27867a1b02b2076fdce66c0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49176032"
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>如何：使用工作流设计器调试 XAML
工作流是以 XAML 的形式定义的。 工作流的 UI 表示形式建立在定义该工作流的 XAML 树之上。 该调试体验与在 [!INCLUDE[wfd1](../includes/wfd1-md.md)] 中调试工作流类似。 例如，调试 XAML 时，“局部变量”、“监视”和“线程”窗口与它们在 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 调试中的工作方式相同。 此外，在 XAML 调试过程中，“调用堆栈”视图是工作流执行流的基于行的分层视图。  
  
> [!NOTE]
>  如果工作流的 XAML 位于活动所在的同一程序集中，将不包括类名称的程序集部分。 没有类（活动）名称的此部分，将不能在运行时加载 XAML。 建议不要在主项目所在的同一命名空间中定义活动；否则，在设计器中编辑后需要手动编辑 XAML。  
  
### <a name="to-debug-workflow-xaml"></a>调试工作流 XAML  
  
1.  在 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 中打开工作流或活动项目。  
  
2.  你想要调试中所述的活动的活动上设置断点[如何： 在工作流中设置断点](../workflow-designer/how-to-set-breakpoints-in-workflows.md)。  
  
3.  右键单击包含您的工作流定义和选择的.xaml 文件**查看代码**。 您将看到在设计视图中对其设置了断点的活动的 XAML 元素声明所在行中显示了一个断点。  
  
4.  调用调试器，如中所述[如何： 调用工作流调试器](../workflow-designer/how-to-invoke-the-workflow-debugger.md)。  
  
5.  当代码执行到你设置的其中一个断点处时，与该断点关联的 XAML 元素将突出显示。 若要将移动到下一个断点，请使用**F10**或**F11**密钥。  
  
## <a name="see-also"></a>请参阅  
 [如何： 在工作流中设置断点](../workflow-designer/how-to-set-breakpoints-in-workflows.md)   
 [如何：调用工作流调试器](../workflow-designer/how-to-invoke-the-workflow-debugger.md)