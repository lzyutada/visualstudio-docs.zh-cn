---
title: 'Idiasession:: Findsymbolbyaddr |Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findSymbolByAddr method
ms.assetid: c130abc5-4d0a-4d2d-8286-94fde36ddd4a
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: edb69dd51e883e23f205d9fb48a2624206d14f41
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51746223"
---
# <a name="idiasessionfindsymbolbyaddr"></a>IDiaSession::findSymbolByAddr
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索包含，或与指定的地址最接近的指定的符号类型。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT findSymbolByAddr (   
   DWORD        isect,  
   DWORD        offset,  
   SymTagEnum   symtag,  
   IDiaSymbol** ppSymbol  
);  
```  
  
#### <a name="parameters"></a>参数  
 `isect`  
 [in]指定地址的部分组件。  
  
 `offset`  
 [in]指定地址的偏移量的部分。  
  
 `symtag`  
 [in]要查找的符号类型。 值取自[SymTagEnum 枚举](../../debugger/debug-interface-access/symtagenum.md)枚举。  
  
 `ppSymbol`  
 [out]返回[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)检索表示该符号的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="example"></a>示例  
  
```cpp#  
IDiaSymbol* pFunc;  
pSession->findSymbolByAddr( isect, offset, SymTagFunction, &pFunc );  
```  
  
## <a name="see-also"></a>请参阅  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 枚举](../../debugger/debug-interface-access/symtagenum.md)



