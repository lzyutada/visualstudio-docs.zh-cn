---
title: “列出线程”命令
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.listthreads
helpviewer_keywords:
- ListThreads command
- list threads command
- Debug.ListThreads command
ms.assetid: 34b665c0-d46f-4c1a-a066-b678eba5ac54
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aa44556be7c20c52d44ec83da1ba9d4972b4542d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31947425"
---
# <a name="list-threads-command"></a>“列出线程”命令
显示当前程序中线程的列表。

## <a name="syntax"></a>语法

```
Debug.ListThreads [index]
```

## <a name="arguments"></a>自变量
 `index`

 可选。 通过索引来选择要用作当前线程的线程。

## <a name="remarks"></a>备注
 如果已指定，`index` 实际参数将指示的线程标记为当前线程。 星号 (*) 显示在当前线程旁边的列表中。

## <a name="example"></a>示例

```
>Debug.ListThreads
```

## <a name="see-also"></a>请参阅

- [“列出调用堆栈”命令](../../ide/reference/list-call-stack-command.md)
- [“列出反汇编”命令](../../ide/reference/list-disassembly-command.md)
- [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)
- [“命令”窗口](../../ide/reference/command-window.md)
- [“查找/命令”框](../../ide/find-command-box.md)
- [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)