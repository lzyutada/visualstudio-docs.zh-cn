---
title: 如何： 清除撤消堆栈 |Microsoft Docs
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
- editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c7f094723ec74bbcfe7723ea8141a6980a1465fa
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51734695"
---
# <a name="how-to-clear-the-undo-stack"></a>如何： 清除撤消堆栈
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

下面的以下过程说明如何清除撤消堆栈。  
  
### <a name="to-clear-the-undo-stack"></a>若要清除撤消堆栈  
  
1.  若要清除撤消堆栈使用[IOleUndoManager::DiscardFrom](http://msdn.microsoft.com/library/windows/desktop/ms693799)方法。 以下是此示例：  
  
    ```  
    HRESULT CCmdWindow::ClearUndoStack()  
    {  
      HRESULT hr = S_OK;  
  
      if (m_pUndoMgr == NULL)  
        {  
        IfFailGo(m_pTextLines->GetUndoManager(&m_pUndoMgr));  
        ASSERT(m_pUndoMgr != NULL, "",;);  
        }  
  
      IfFailGo(m_pUndoMgr->DiscardFrom(NULL));  
  
    Error:  
      return hr;  
    }  
    ```  
  
## <a name="see-also"></a>请参阅  
 [如何：实现撤消管理](../extensibility/how-to-implement-undo-management.md)

