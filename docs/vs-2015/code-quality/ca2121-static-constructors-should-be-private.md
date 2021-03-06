---
title: CA2121： 静态构造函数应为私有 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
helpviewer_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
ms.assetid: ee93c620-8fc1-4e47-866c-d389c3ca9f2e
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 24fcd6970d368bfee739e47f9b7e0407f5cd6307
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49918540"
---
# <a name="ca2121-static-constructors-should-be-private"></a>CA2121：静态构造函数应为私有
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|StaticConstructorsShouldBePrivate|
|CheckId|CA2121|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 类型具有不是私有的静态构造函数。

## <a name="rule-description"></a>规则说明
 静态构造函数，也称为类构造函数，用于初始化的类型。 系统在创建第一个类型实例或引用任何静态成员之前调用静态构造函数。 用户可以调用静态构造函数时没有控制。 如果静态构造函数不是私有，则系统以外的代码可以调用它。 根据构造函数中执行的操作，这可能导致意外行为。

 此规则由 C# 和 Visual Basic.NET 编译器强制执行。

## <a name="how-to-fix-violations"></a>如何解决冲突
 冲突通常由以下操作之一引起：

- 为你的类型定义静态构造函数和未将它设置为私有。

- 编程语言编译器添加到你的类型的默认静态构造函数和未将它设置为私有。

  若要解决冲突的第一个类型，请将静态构造函数专用。 若要解决的第二个类型，请与您的类型添加私有静态构造函数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不要禁止显示这些冲突。 如果您的软件设计要求显式静态构造函数调用，则很可能设计存在严重缺陷，应进行检查。



