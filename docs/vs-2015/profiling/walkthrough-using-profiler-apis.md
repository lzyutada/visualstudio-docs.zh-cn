---
title: 演练：使用探查器 API | Microsoft Docs
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
- profiling tools, walkthroughs
- performance tools, walkthroughs
ms.assetid: c2ae0b3e-a0ca-4967-b4df-e319008f520e
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b7eb2d4c3acfc8f2a98de1364b1f98aa451abaed
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470102"
---
# <a name="walkthrough-using-profiler-apis"></a>演练：使用探查器 API
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[演练： 使用 Profiler Api](https://docs.microsoft.com/visualstudio/profiling/walkthrough-using-profiler-apis)。  
  
本演练使用 C# 应用程序演示如何使用 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 分析工具 API。 用户将使用探查器 API 限制在检测分析期间收集的数据量。  
  
 本演练中的步骤通常适用于 C/C++ 应用程序。 对于每种语言，都需要配置适当的生成环境。  
  
 应用程序性能分析通常是从使用采样分析开始的。 如果采样分析没有提供可查明瓶颈的信息，检测分析可以提供更为详细的信息。 检测分析对于调查线程交互非常有用。  
  
 但是，更为详细的信息也意味着会收集更多数据。 用户可能发现检测分析会创建大型数据文件。 此外，检测更有可能影响应用程序的性能。 有关详细信息，请参阅[了解检测数据值](../profiling/understanding-instrumentation-data-values.md)和[了解采样数据值](../profiling/understanding-sampling-data-values.md)  
  
 通过 Visual Studio 探查器，可以限制数据收集。 本演练提供一个示例，说明如何使用探查器 API 限制数据收集。 Visual Studio 探查器提供一个 API，用于从应用程序内部控制数据收集。  
  
 对于本机代码，Visual Studio 探查器 API 位于 VSPerf.dll 中。 头文件 VSPerf.h 和导入库 VSPerf.lib 位于 Microsoft Visual Studio 9\Team Tools\Performance Tools 目录中。  
  
 对于托管代码，探查器 API 位于 Microsoft.VisualStudio.Profiler.dll 中。 此 DLL 位于 Microsoft Visual Studio 9\Team Tools\Performance Tools 目录中。 有关详细信息，请参阅<xref:Microsoft.VisualStudio.Profiler>。  
  
## <a name="prerequisites"></a>系统必备  
 本演练假定用户选择的开发环境配置为支持调试和采样。 以下主题概述了这些系统必备：  
  
 [如何：选择收集方法](../profiling/how-to-choose-collection-methods.md)  
  
 [如何：引用 Windows 符号信息](../profiling/how-to-reference-windows-symbol-information.md)  
  
 默认情况下，当探查器启动时，探查器在全局级别收集数据。 下面的代码位于程序开头，其功能是关闭全局分析。  
  
```  
DataCollection.StopProfile(  
ProfileLevel.Global,  
DataCollection.CurrentId);  
```  
  
 即使不使用 API 调用，也可以在命令行关闭数据收集。 以下步骤假定命令行生成环境配置为开发工具，并运行分析工具。 这包括 VSInstr 和 VSPerfCmd 所需的设置。 请参阅命令行分析工具。  
  
## <a name="limiting-data-collection-using-profiler-apis"></a>使用探查器 API 限制数据收集  
  
#### <a name="to-create-the-code-to-profile"></a>创建要分析的代码  
  
1.  在 Visual Studio 中创建一个新的 C# 项目，或使用命令行生成，具体取决于用户的选择。  
  
    > [!NOTE]
    >  生成必须引用 Microsoft.VisualStudio.Profiler.dll 库，该库位于 Microsoft Visual Studio 9\Team Tools\Performance Tools 目录中。  
  
2.  将以下代码复制并粘贴到项目中：  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using Microsoft.VisualStudio.Profiler;  
  
    namespace ConsoleApplication2  
    {  
        class Program  
        {  
            public class A  
            {  
             private int _x;  
  
             public A(int x)  
             {  
              _x = x;  
             }  
  
             public int DoNotProfileThis()  
             {  
              return _x * _x;  
             }  
  
             public int OnlyProfileThis()  
             {  
              return _x + _x;  
             }  
  
             public static void Main()  
             {  
            DataCollection.StopProfile(  
            ProfileLevel.Global,  
            DataCollection.CurrentId);  
              A a;  
              a = new A(2);  
              int x;      
              Console.WriteLine("2 square is {0}", a.DoNotProfileThis());  
              DataCollection.StartProfile(  
                  ProfileLevel.Global,  
                  DataCollection.CurrentId);  
              x = a.OnlyProfileThis();  
              DataCollection.StopProfile(  
                  ProfileLevel.Global,   
                  DataCollection.CurrentId);  
              Console.WriteLine("2 doubled is {0}", x);  
             }  
            }  
  
        }  
    }  
    ```  
  
#### <a name="to-collect-and-view-data-in-the-visual-studio-ide"></a>在 Visual Studio IDE 中收集和查看数据  
  
1.  打开 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] IDE。 在“分析”菜单上指向“探查器”，然后选择“新建性能会话”。  
  
2.  将编译的二进制文件添加到“性能资源管理器”窗口的“目标”列表中。 右键单击“目标”，然后选择“添加目标二进制文件”。 在“添加目标二进制文件”对话框中找到二进制文件，然后单击“打开”。  
  
3.  从“性能资源管理器”工具栏上的“方法”列表中选择“检测”。  
  
4.  单击“启动并启用分析功能”。  
  
     探查器将检测和执行该二进制文件，并创建一个性能报告文件。 性能报告文件将显示在“性能资源管理器”的“报告”节点中。  
  
5.  打开生成的性能报告文件。  
  
 默认情况下，当探查器启动时，探查器将在全局级别收集数据。 下面的代码位于程序开头，其功能是关闭全局分析。  
  
```  
DataCollection.StopProfile(  
ProfileLevel.Global,  
DataCollection.CurrentId);  
```  
  
#### <a name="to-collect-and-view-data-at-the-command-line"></a>在命令行收集和查看数据  
  
1.  编译在“创建要分析的代码”过程（本演练前面部分）中创建的代码示例的调试版本。  
  
2.  若要分析托管应用程序，请键入以下命令设置适当的环境变量：  
  
     **VsPefCLREnv /traceon**  
  
3.  键入下面的命令：**VSInstr \<文件名>.exe**  
  
4.  键入下面的命令：**VSPerfCmd /start:trace /output:\<文件名>.vsp**  
  
5.  键入下面的命令：**VSPerfCmd /globaloff**  
  
6.  执行程序。  
  
7.  键入下面的命令：**VSPerfCmd /shutdown**  
  
8.  键入下面的命令：**VSPerfReport /calltrace:\<文件名>.vsp**  
  
     当前目录中即会创建一个 .csv 文件，该文件包含得到的性能数据。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.Profiler>   
 [Visual Studio 探查器 API 参考（本机）](../profiling/visual-studio-profiler-api-reference-native.md)   
 [入门](../profiling/getting-started-with-performance-tools.md)   
 [从命令行分析](../profiling/using-the-profiling-tools-from-the-command-line.md)


