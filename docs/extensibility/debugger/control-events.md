---
title: 控件事件 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 0fc63484-5fb6-4887-9ea4-1905b459ca9d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7a2da9f3e91eb803d292f1ab789f8133558db049
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49913301"
---
# <a name="control-events"></a>控件事件
必须将事件发送程序的受控的执行过程。 使用的所有事件发送[IDebugEvent2](../../extensibility/debugger/reference/idebugevent2.md)界面，并且具有需要实现的属性[IDebugEvent2::GetAttributes](../../extensibility/debugger/reference/idebugevent2-getattributes.md)方法。  
  
## <a name="additional-methods"></a>其他方法  
 某些事件需要的其他方法的实现，如下所示：  
  
- 发送[IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md)接口时初始化调试引擎 (DE) 要求您实现[IDebugEngineCreateEvent2::GetEngine](../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md)方法。  
  
- 执行控件需要为此类控件事件的实现[IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md)并[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md)接口。 **IDebugBreakEvent2**仅需要异步分页符。  
  
- 单步执行函数需要实现[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md)接口和其方法。  
  
  派生自断点事件需要实施[IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)， [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md)，并[IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)接口，并将[IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md)并[EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md)方法。  
  
  异步表达式计算要求您实现[IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)接口并将其[IDebugExpressionEvaluationCompleteEvent2::GetExpression](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md)[和 GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md)方法。  
  
  同步事件需要实现[IDebugEngine2::ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)方法。  
  
  对于写入字符串样式输出在引擎，必须实现[IDebugOutputStringEvent2::GetString](../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [执行控件和状态评估](../../extensibility/debugger/execution-control-and-state-evaluation.md)