---
title: IDebugClassField::EnumNestedClasses |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugClassField::EnumNestedClasses
helpviewer_keywords:
- IDebugClassField::EnumNestedClasses method
ms.assetid: 2ba5ef0c-395e-4006-9e3c-9b06e1d711d0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a313e27c3dcbca0136b00bfb789e444174474369
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49937520"
---
# <a name="idebugclassfieldenumnestedclasses"></a>IDebugClassField::EnumNestedClasses
创建此类中嵌套的类的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumNestedClasses(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumNestedClasses(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
 [out]返回[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)对象，表示的嵌套类的列表。 如果不有任何嵌套的类，则返回 null 值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK 或如果没有嵌套的类，则返回 S_FALSE。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 枚举每个元素均[IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)描述嵌套的类的对象。  
  
 嵌套的类是在另一个类中定义的类。 例如：  
  
```  
class RootClass {  
   class NestedClass { }  
};  
```  
  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)枚举将包含一个对象，表示`NestedClass`类。  
  
## <a name="see-also"></a>请参阅  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)