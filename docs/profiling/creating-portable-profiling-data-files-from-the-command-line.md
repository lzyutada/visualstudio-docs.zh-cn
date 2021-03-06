---
title: 从命令行创建可移植的分析数据文件 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: be919183f18efc29ea562b0e4cc60c84febe60c8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49841931"
---
# <a name="create-portable-profiling-data-files-from-the-command-line"></a>从命令行创建可移植的分析数据文件
若要更轻松地共享分析数据，可以使用 [VSPerfReport](../profiling/vsperfreport.md) 命令行工具将用于分析运行的符号嵌入到 .vsp 文件中。  
  
 还可以创建经过预先分析的分析数据 (.vsps) 文件，此文件较小，可在 IDE 中快速加载。  
  
> [!NOTE]
>  请确保符号 (.pdb) 文件可供 VSPerfReport 使用。 有关详细信息，请参阅[如何：从命令行指定符号文件位置](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md)。  
>   
>  有关 VSReport 路径的信息，请参阅[指定命令行工具的路径](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)。  
>   
>  无法筛选 .vsps 文件中的分析数据。  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>将用于分析运行的符号嵌入到分析数据 (.vsp) 文件  
  
- 在命令提示符窗口中，键入以下命令：  
  
   \<Path>VSPerfReport \<VSP File> /PackSymbols  
  
   默认采用 .vsp 文件的基名称对 .vsps 文件进行命名。 可以通过使用“输出”选项指定替代名称。  
  
### <a name="to-create-a-summary-profiling-data-file"></a>创建摘要分析数据文件  
  
- 在命令提示符窗口中，键入以下命令：  
  
   \<Path><strong>VSPerfReport \<</strong>VSP File> **/SummaryFile** [**/Output:**\<File Name>]  
  
   默认采用 .vsp 文件的基名称对 .vsps 文件进行命名。 可以通过使用“输出”选项指定替代名称。