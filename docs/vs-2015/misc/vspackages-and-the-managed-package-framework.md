---
title: Vspackage 和托管的包框架 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managed package framework
- VSPackages, managed package framework
- managed VSPackages, managed package framework
ms.assetid: e8d80e0f-6b5b-4baf-a7df-59fd808c60cd
caps.latest.revision: 16
manager: douge
ms.openlocfilehash: 2e265a342ec32abea40ab9b352b5735079462a46
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49227976"
---
# <a name="vspackages-and-the-managed-package-framework"></a>VSPackage 和托管包框架
通过创建 VSPackage 使用托管包框架 (MPF) 类而不是通过使用 COM 互操作类，可以减少开发时间。  
  
 有两种方法来创建托管的 VSPackage:  
  
-   使用[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]包项目模板  
  
     有关详细信息，请参阅[演练： 创建菜单命令通过使用 Visual Studio 包模板](http://msdn.microsoft.com/library/1985fa7d-aad4-4866-b356-a125b6a246de)。  
  
-   生成你的 VSPackage 而无需[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]包项目模板  
  
     例如，可以复制示例 VSPackage，并更改 Guid 和名称。 你可以找到的 VSX 部分中的示例[代码库](http://code.msdn.microsoft.com/vsx/)。  
  
## <a name="in-this-section"></a>本节内容  
 [托管包框架类](../misc/managed-package-framework-classes.md)  
 描述并列出 MPF 类命名空间和 DLL 文件。  
  
## <a name="related-sections"></a>相关章节  
 [演练： 使用 Visual Studio 包模板创建菜单命令](http://msdn.microsoft.com/library/1985fa7d-aad4-4866-b356-a125b6a246de)  
 介绍如何创建托管的 VSPackage。  
  
 [托管的 VSPackage](../misc/managed-vspackages.md)  
 引入了适用于托管代码的 Vspackage 的方面。