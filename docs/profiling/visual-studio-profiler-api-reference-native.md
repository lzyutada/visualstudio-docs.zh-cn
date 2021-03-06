---
title: Visual Studio 探查器 API 参考（本机）
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, API
- Profiler, API
ms.assetid: a0c3be92-c263-4678-9fb9-bafead3bd5f5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: acb85c9994436b2e35a6d4161a579180ad5e0ac5
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53062979"
---
# <a name="visual-studio-profiler-api-reference-native"></a>Visual Studio 探查器 API 参考（本机）
Visual Studio 探查器 API 允许你以编程方式控制收集的数据量，并在分析期间插入时间戳和分析标记。 若要使用本机 API，请包含 VSPerf.h 头文件，并在项目中添加 VSPerf.lib。  
  
> [!NOTE]
>  默认情况下，VSPerf.h 和 VSPerf.lib 位于“PerfSDK”文件夹中。 例如，\<drive>:\Program Files\Microsoft Visual Studio 14.0\Team Tools\Performance Tools\PerfSDK 目录。  
  
## <a name="in-this-section"></a>本节内容  
 [CommentMarkAtProfile](../profiling/commentmarkatprofile.md)  
  
 [CommentMarkProfile](../profiling/commentmarkprofile.md)  
  
 [MarkProfile](../profiling/markprofile.md)  
  
 [NameProfile](../profiling/nameprofile.md)  
  
 [ResumeProfile](../profiling/resumeprofile.md)  
  
 [StartProfile](../profiling/startprofile.md)  
  
 [StopProfile](../profiling/stopprofile.md)  
  
 [SuspendProfile](../profiling/suspendprofile.md)  
  
 [PROFILE_CURRENTID](../profiling/profile-currentid.md)  
  
## <a name="see-also"></a>请参阅  
 [分析工具 API](../profiling/profiling-tools-apis.md)   
 [演练：使用探查器 API](../profiling/walkthrough-using-profiler-apis.md)
