---
title: CA2118： 检查 SuppressUnmanagedCodeSecurityAttribute 用法 |Microsoft Docs
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
- CA2118
- ReviewSuppressUnmanagedCodeSecurityUsage
helpviewer_keywords:
- ReviewSuppressUnmanagedCodeSecurityUsage
- CA2118
ms.assetid: 4cb8d2fc-4e44-4dc3-9b74-7f5838827d41
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6d4cee2d7758f467a13875f89a9534ceb0d883b5
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49904474"
---
# <a name="ca2118-review-suppressunmanagedcodesecurityattribute-usage"></a>CA2118：检查 SuppressUnmanagedCodeSecurityAttribute 用法
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ReviewSuppressUnmanagedCodeSecurityUsage|
|CheckId|CA2118|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 公共或受保护的类型或成员具有<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName>属性。

## <a name="rule-description"></a>规则说明
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 执行使用 COM 互操作或平台调用的非托管的代码的成员更改默认的安全系统行为。 通常情况下，系统会进行[数据和建模](http://msdn.microsoft.com/library/8c37635d-e2c1-4b64-a258-61d9e87405e6)非托管的代码权限。 此要求发生在运行时为每个成员，并且检查权限的调用堆栈中每个调用方。 当存在该属性时，系统会进行[链接要求](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)的权限： 调用方进行 JIT 编译时检查直接调用方的权限。

 该特性主要用于提高性能；不过，提高性能的同时会显著增加安全风险。 如果该属性将在调用本机方法的公共成员上时中 （而不是直接调用方） 的调用堆栈, 的调用方不需要执行非托管的代码的非托管的代码权限。 具体取决于公共成员的操作和输入的处理，它可能允许不受信任调用方访问通常限制为可信的代码的功能。

 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]依赖于安全性检查，以防止调用方直接访问当前进程的地址空间。 此特性会绕过常规安全，因为你的代码将造成严重的威胁，如果可用于读取或写入到该进程的内存。 请注意风险并不局限于有意提供访问权限来处理内存; 方法该按钮还出现在任何情况下，其中恶意代码可以访问通过任何方式，例如，通过实现提供令人惊讶、 格式不正确，或无效输入。

 默认安全策略不会向程序集授予非托管的代码权限，除非它执行从本地计算机或者是以下组之一的成员：

-   我的计算机的区域代码组

-   Microsoft 强名称代码组

-   ECMA 强名称代码组

## <a name="how-to-fix-violations"></a>如何解决冲突
 请仔细查看代码，以确保此属性是绝对必要。 如果你不熟悉托管的代码安全或不了解使用此属性的安全隐患，请在代码中将其删除。 如果该属性是必需的您必须确保调用方不能出于恶意使用你的代码。 如果你的代码没有权限来执行非托管的代码，此属性不起作用，应删除。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 若要安全地禁止显示此规则的警告，必须确保你的代码不提供调用方对本机操作或可以以破坏方式使用的资源的访问权限。

## <a name="example"></a>示例
 下面的示例与规则冲突。

 [!code-csharp[FxCop.Security.TypesDoNotSuppress#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TypesDoNotSuppress/cs/FxCop.Security.TypesDoNotSuppress.cs#1)]

## <a name="example"></a>示例
 在以下示例中，`DoWork`方法提供的平台调用方法的可公开访问的代码路径`FormatHardDisk`。

 [!code-csharp[FxCop.Security.PInvokeAndSuppress#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.PInvokeAndSuppress/cs/FxCop.Security.PInvokeAndSuppress.cs#1)]

## <a name="example"></a>示例
 在下面的示例中，公共方法`DoDangerousThing`会导致冲突。 若要解决冲突，`DoDangerousThing`应设为专用，并对它的访问应通过公共方法受保护的安全要求，如所示`DoWork`方法。

 [!code-csharp[FxCop.Security.TypeInvokeAndSuppress#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TypeInvokeAndSuppress/cs/FxCop.Security.TypeInvokeAndSuppress.cs#1)]

## <a name="see-also"></a>请参阅
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> [安全编码准则](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)[安全优化](http://msdn.microsoft.com/en-us/cf255069-d85d-4de3-914a-e4625215a7c0)[数据和建模](http://msdn.microsoft.com/library/8c37635d-e2c1-4b64-a258-61d9e87405e6)[链接需求](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)



