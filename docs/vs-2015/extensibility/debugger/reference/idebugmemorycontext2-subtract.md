---
title: IDebugMemoryContext2::Subtract |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugMemoryContext2::Subtract
helpviewer_keywords:
- Subtract method
- IDebugMemoryContext2::Subtract method
ms.assetid: 63df14c7-8d7e-47c1-afa7-5a1ab5d8eaba
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3265e8845340b2a02dbd5bf30c05b9e4c4d2400b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470215"
---
# <a name="idebugmemorycontext2subtract"></a>IDebugMemoryContext2::Subtract
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugMemoryContext2::Subtract](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmemorycontext2-subtract)。  
  
从当前上下文中的指定的值减去，并返回新的上下文。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Subtract(   
   UINT64                 dwCount,  
   IDebugMemoryContext2** ppMemCxt  
);  
```  
  
```csharp  
int Subtract(  
   ulong                    dwCount,   
   out IDebugMemoryContext2 ppMemCxt  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwCount`  
 [in]要递减的内存字节数。  
  
 `ppMemCxt`  
 [out]返回一个新[IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 内存上下文是一个地址，因此从发件人地址值中减去生成需要新的上下文接口的新地址。  
  
 即使生成的地址是与此上下文关联的内存空间外，此方法必须始终会生成一个新的上下文。 唯一的例外是，如果可以为新的上下文不分配任何内存或`ppMemCxt`为空值 （这是错误）。  
  
## <a name="see-also"></a>请参阅  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
