---
title: IDebugPortEvents2::Event |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPortEvents2::Event
helpviewer_keywords:
- IDebugPortEvents2::Event
ms.assetid: 5cc813f7-04a1-4462-9ea7-fbddcf0e0143
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c4f27e05c331c500b6b490bde382a42c09103708
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51760304"
---
# <a name="idebugportevents2event"></a>IDebugPortEvents2::Event
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此方法将发送表示创建和销毁的过程和程序的端口上的事件。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Event(  
   IDebugCoreServer2* pServer,  
   IDebugPort2*       pPort,  
   IDebugProcess2*    pProcess,  
   IDebugProgram2*    pProgram,  
   IDebugEvent2*      pEvent,  
   REFIID             riidEvent  
);  
```  
  
```csharp  
int Event(  
   IDebugCoreServer2 pServer,   
   IDebugPort2       pPort,   
   IDebugProcess2    pProcess,   
   IDebugProgram2    pProgram,   
   IDebugEvent2      pEvent,   
   ref Guid          riidEvent  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pMachine`  
 [in][IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)对象，表示调试服务器 (还有一个的每个实例[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]) 中发生该事件。  
  
 `pPort`  
 [in][IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)对象，表示在其中发生事件的端口。  
  
 `pProcess`  
 [in][IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)对象，表示在其中发生事件的过程。  
  
 `pProgram`  
 [in][IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)表示的程序发生事件的对象。  
  
 `pEvent`  
 [in][IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)标识的事件的对象。 可能的事件，如下所示为：  
  
- [IDebugProcessCreateEvent2](../../../extensibility/debugger/reference/idebugprocesscreateevent2.md)  
  
- [IDebugProcessDestroyEvent2](../../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)  
  
- [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
  
- [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)  
  
  `riidEvent`  
  [in]事件的 GUID。 因为该事件转换为[IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)调用此方法之前，此标识符可以更轻松地确定正在发送的事件。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)

