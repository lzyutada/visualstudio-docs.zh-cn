---
title: 'Idiaimagedata:: Get_imagebase |Microsoft Docs'
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
- IDiaImageData::get_imageBase method
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e09fb71294631f95b0d1d39ac6137c2e49b5bdea
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51801298"
---
# <a name="idiaimagedatagetimagebase"></a>IDiaImageData::get_imageBase
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索其中应基于映像的内存位置。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_imageBase (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回建议的图像的基值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 由于映像基冲突而进行映像可能会重新设定基址自动到未使用的内存位置在加载时。 此方法返回已在编译时存储在模块中的基本提示 （建议的内存位置）。  
  
## <a name="see-also"></a>请参阅  
 [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)



