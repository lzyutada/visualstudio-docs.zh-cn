---
title: 实现抽象类
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: dfa2c6692ddcef9e41454bf902580f354c32f861
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53047598"
---
# <a name="implement-an-abstract-class-in-visual-studio"></a>在 Visual Studio 中实现抽象类

此代码生成适用于：

- C#

- Visual Basic

**功能：** 快速生成实现抽象类所需的代码。

**使用时机：** 想要继承抽象类时。

操作原因：可以手动逐一实现各个抽象类，但此功能可自动生成所有方法签名。

## <a name="how-to"></a>操作说明

1. 将光标置于红色波浪线，该线条表示已从抽象类继承但部分必需成员尚未实现。

   - C#：

       ![突出显示的代码 C#](media/abstract-highlight-cs.png)

   - Visual Basic：

       ![突出显示的代码 VB](media/abstract-highlight-vb.png)

2. 接下来，执行以下操作之一：

   - **键盘**
      - 按“Ctrl”+**。** 触发“快速操作和重构”菜单。
   - **鼠标**
      - 右键单击并选择“快速操作和重构”菜单。
      - 将鼠标悬停在红色波形曲线上，然后单击出现的 ![灯泡](media/bulb-cs.png) 图标。
      - 单击 ![灯泡](media/bulb-cs.png) 图标（如果文本光标已在具有红色波形曲线的行上，它会出现在左边缘）。

   ![实现类预览](media/abstract-preview-cs.png)

3. 从下拉菜单中选择“实现抽象类”。

   > [!TIP]
   > - 进行选择前，使用预览窗口底部的“预览更改”链接[查看将发生的所有更改](../../ide/preview-changes.md)。
   > - 通过预览窗口底部的“文档”、“项目”和“解决方案”链接，跨继承自此抽象类的多个类创建适当的方法签名。

   将创建抽象方法签名以供实现。

   - C#：

       ![“实现类”的结果 C#](media/abstract-result-cs.png)

   - Visual Basic：

       ![“实现类”的结果 VB](media/abstract-result-vb.png)

## <a name="see-also"></a>请参阅

- [代码生成](../code-generation-in-visual-studio.md)
- [预览更改](../../ide/preview-changes.md)