---
title: 在调试器外部运行程序时如何调试访问冲突？ | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.access
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5e0ed8025986c92cd4c809ea8b04f0109fb010c5
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51816265"
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>在调试器外部运行程序时如何调试访问冲突？
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

问题描述  
 我的程序在 Visual Studio 环境中运行良好，但在 Windows 操作系统中独立运行时产生访问冲突。 如何调试该问题？  
  
## <a name="solution"></a>解决方案  
 设置[中实时调试](../debugger/just-in-time-debugging-in-visual-studio.md)选项并运行独立应用程序，直到发生访问冲突。 然后，在**访问冲突**对话框中，你可以单击**取消**启动调试器。  
  
 请参见知识库文章 Q133174“How to Locate Where a General Protection (GP) Fault Occurs”（如何定位通用性保护 (GP) 错误的发生位置）。 MSDN 库 CD 上或通过搜索可以查找知识库文章[ http://support.microsoft.com/ ](http://support.microsoft.com/)。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)   
 [调试本机代码](../debugger/debugging-native-code.md)



