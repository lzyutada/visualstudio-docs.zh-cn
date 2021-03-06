---
title: EVALFLAGS |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EVALFLAGS
helpviewer_keywords:
- EVALFLAGS enumeration
ms.assetid: 7b2cb14a-511a-4fef-9e4f-308139719fba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ef229fb06f8b265b76dc40019b18ae3c796740f7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49829958"
---
# <a name="evalflags"></a>EVALFLAGS
指定用于控制表达式求值的标志。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
};  
typedef DWORD EVALFLAGS;  
```  
  
```csharp  
public enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
}  
```  
  
## <a name="members"></a>成员  
 EVAL_RETURNVALUE  
 指定的计算返回值，如果有的话。  
  
 EVAL_NOSIDEEFFECTS  
 指定不允许副作用。  
  
 EVAL_ALLOWBPS  
 指定断点停止。  
  
 EVAL_ALLOWERRORREPORT  
 指定错误报告到的主机功能，允许。 主要用于在 Internet Explorer 中的脚本中的表达式计算。  
  
 EVAL_FUNCTION_AS_ADDRESS  
 强制函数计算结果为地址，而不是调用该函数。  
  
 EVAL_NOFUNCEVAL  
 防止函数进行计算。 例如，考虑`int`令牌在表达式中`myExpression(int) + 10`。 为地址，但不能作为一个值，此函数可以正确评估。  
  
 EVAL_NOEVENTS  
 一个标志，用于指示会话调试管理器 (SDM) 或 IDE 未发送的表达式计算期间发生的事件。  
  
## <a name="remarks"></a>备注  
 这些标志作为参数传递[EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)并[EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)方法。  
  
 可能会使用按位 OR 组合这些标志。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)