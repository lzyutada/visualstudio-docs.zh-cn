---
title: 调试前台应用程序时使用调试器窗口 |Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.background
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- foreground program debugging
- remote debugging, debugging foreground programs
- debugging [Visual Studio], while observing foreground programs
- focus, debugging while observing foreground programs
- debugging [Visual Studio], foreground programs
ms.assetid: 9e67a308-1c81-42ab-966b-7fc3c1d2bf7a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6497a2a21c85e7889b3b6538dace0f8c22f24944
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53063763"
---
# <a name="how-can-i-use-debugger-windows-while-debugging-a-foreground-program"></a>调试前台程序时如何使用调试器窗口？
## <a name="problem-description"></a>问题描述  
 我在尝试调试屏幕绘制问题。 若要观察该问题，必须将程序保持在前台，这意味着不能访问调试窗口。 我该怎么办？  
  
## <a name="solution"></a>解决方案  
 如果有另一台计算机，则可以使用远程调试。 通过两台计算机的设置，当在主机上运行调试器时，可以监视远程计算机上的屏幕绘制。 有关远程调试的详细信息，请参阅[远程调试](../debugger/remote-debugging.md)。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)   
 [调试本机代码](../debugger/debugging-native-code.md)