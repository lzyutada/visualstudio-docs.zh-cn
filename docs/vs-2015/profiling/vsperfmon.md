---
title: VSPerfMon | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSPerfMon tool
- command line, tools
- command-line tools, VSPerfMon tool
- data [Visual Studio ALM], VSPerfMon tool
- performance data, VSPerfMon tool
- performance tools, VSPerfMon tool
- profilng tools,VSPerfCmd
ms.assetid: 37052afb-7a58-441f-bb17-f1587cc57068
caps.latest.revision: 35
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b06a91268560f3762ad78b2be238e8e30192ca53
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470385"
---
# <a name="vsperfmon"></a>VSPerfMon
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[VSPerfMon](https://docs.microsoft.com/visualstudio/profiling/vsperfmon)。  
  
可以使用 VSPerfMon 工具收集应用程序的性能数据；通常，由 VSPerfCmd.exe 启动该工具。 VSPerfMon 显示有关进程附加或分离的其他详细信息，而使用 VSPerfCmd 工具则无法获取这些信息。 若要查看此信息，请在单独的窗口中启动 VSPerfMon。 若要调用 VSPerfMon，请使用以下语法：  
  
```  
VSPerfMon [/U] </TRACE [/COUNTER:cfg] | /SAMPLE | /COVERAGE> /CROSSSESSION /OUTPUT <file name> [/WINCOUNTER:cfg] [/USER [DOMAIN\]username]  
```  
  
 下表描述了 VSPerfMon 工具选项：  
  
|选项|描述|  
|-------------|-----------------|  
|**U**|以 Unicode 形式写入重定向的控制台输出。  这必须是指定的第一个选项。|  
|**OUTPUT:** `<` *文件名* `>`|将输出重定向到指定的文件名。|  
|**TRACE**|为被检测的分析启动性能监视器。|  
|**SAMPLE**|为采样分析启动性能监视器。|  
|**COVERAGE**|为代码覆盖率收集启动性能监视器。|  
|**CONCURRENCY**|启动资源争用分析的性能监视器。|  
|**USER:** `[` *域* `\]` *用户名*|使客户端可以用指定的帐户访问性能监视器。|  
|**CROSSSESSION**|启用跨会话分析。|  
|**COUNTER** `:cfg`|使用检测 (TRACE) 分析方法时，指定要在每个检测点收集的 CPU 计数器。 可以通过指定多个计数器选项收集多个计数器数据。<br /><br /> 使用以下语法指定计数器 (*cfg*) 数据：<br /><br /> **CounterName** [**,Reload**[,**FriendlyName**]]<br /><br /> -   **CounterName** 是 VSPerfCmd /QueryCounters 命令返回的计数器的名称。<br />-   **Reload** 是计数器事件采样间隔。 不要将 *Reload* 与检测方法一起使用。<br />-   指定后，**FriendlyName** 将替换分析工具报告列名称中的 **CounterName**。|  
|**WINCOUNTER** `:path`|指定要与标记数据一起包括的 Windows 性能计数器。 `path` 是 PDH 计数器路径格式的 Windows 性能计数器字符串。 例如：<br /><br /> \Processor(0)\\% Processor Time<br /><br /> \System\Context Switches/sec|  
|**AUTOMARK** `:n`|指定使用 /WINCOUNTER 时自动标记之间的时间间隔（以毫秒为单位）。 向上舍入到最接近 500 毫秒。<br /><br /> 使用 0 以禁用自动标记。 （如果未指定，则默认为 500 毫秒）|  
  
## <a name="see-also"></a>请参阅  
 [VSInstr](../profiling/vsinstr.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [VSPerfReport](../profiling/vsperfreport.md)   
 [性能报告视图](../profiling/performance-report-views.md)


