---
title: 找出谁在传递错误的参数值 |Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.parameters
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], parameters
- parameters [debugger]
- passing parameters, troubleshooting wrong values
- functions [debugger], detecting wrong parameter values
- parameter values, troubleshooting
ms.assetid: 1f1ae455-0e25-4e9d-b33f-53908f5bd6ce
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 164ca15cfc508b952ccfe2f986892c0801fd1539
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53059361"
---
# <a name="how-can-i-find-out-who-is-passing-a-wrong-parameter-value"></a>如何查明谁在传递错误的参数值？
## <a name="problem-description"></a>问题描述  
 给我的某个函数传递的是错误的参数值。 很多地方都在调用该函数。 如何查明是谁在传递错误值？  
  
## <a name="solution"></a>解决方案  
  
#### <a name="to-resolve-this-problem"></a>解决此问题  
  
1.  在函数的开始处设置一个位置断点。  
  
2.  右键单击该断点并选择“条件”。  
  
3.  在“断点条件”对话框中，单击“条件”复选框。 请参阅[高级断点](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)。  
  
4.  在文本框中输入一个表达式（例如 `Var==3`），此处 `Var` 是包含错误值的参数的名称，`3` 是传给此参数的错误值。  
  
5.  选择“为真”单选按钮，单击“确定”按钮。  
  
6.  现在再次运行程序。 当 `Var` 参数的值为 `3` 时，断点导致程序在函数开始处暂停。  
  
7.  然后可以使用“调用堆栈”窗口查找调用函数并定位到其源代码。 有关更多信息，请参见[如何：使用“调用堆栈”窗口](../debugger/how-to-use-the-call-stack-window.md)。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)   
 [断点](https://msdn.microsoft.com/library/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [调试本机代码](../debugger/debugging-native-code.md)