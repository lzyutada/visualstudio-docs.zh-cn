---
title: 命令的 Vspackage 中的路由 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, routing
- command routing, Visual Studio SDK
ms.assetid: a9c7f9ae-3594-4557-a314-8cf76f5f8772
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5a5f884873e714c12708780a0e52f5f5574727fb
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2018
ms.locfileid: "39512930"
---
# <a name="command-routing-in-vspackages"></a>Vspackage 中的命令传送
命令路由中[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]基于在其中执行的上下文。 它从初始上下文外部路由到全局上下文。  
  
## <a name="in-this-section"></a>本节内容  
 [命令传送算法](../../extensibility/internals/command-routing-algorithm.md)  
 描述命令路由解析的顺序。  
  
 [命令可用性](../../extensibility/internals/command-availability.md)  
 讨论命令路由。  
  
 [使用互操作程序集的命令和菜单](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)  
 讨论托管的代码和 COM 之间的路由命令中的注意事项  
  
## <a name="related-sections"></a>相关章节  
 [选择上下文对象](../../extensibility/internals/selection-context-objects.md)  
 讨论如何确定用户的选定内容上下文焦点窗口上的模型。  
  
 [命令、 菜单和工具栏](../../extensibility/internals/commands-menus-and-toolbars.md)  
 说明如何创建包含菜单、工具栏和命令组合框的 UI。