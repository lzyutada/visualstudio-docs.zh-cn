---
title: 端口供应商 |Microsoft Docs
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
- port suppliers
- debugging [Debugging SDK], port suppliers
ms.assetid: a8f3db96-1a13-4e93-9ef6-0861880369e0
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8ca5c7d9154b07cbc51b5fde6b9c85e97d880df
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51751581"
---
# <a name="port-suppliers"></a>端口提供程序
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

在调试器体系结构，方面**端口供应商**:  
  
- 包含由服务器并提供有关对该服务器的请求的端口。  
  
- 可以添加和删除包含服务器的端口。  
  
- 可以枚举具有提供给服务器的所有端口。  
  
- 为由[IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)接口，通过在注册表中注册与 Visual Studio。 此接口可以通过调用来获取[GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)。  
  
  [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 提供了默认端口提供程序和默认端口。 如果需要实现自定义端口，则自定义端口提供程序还需要实现以提供这些自定义端口。  
  
## <a name="see-also"></a>请参阅  
 [服务器](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [端口](../../extensibility/debugger/ports.md)   
 [调试器概念](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)

