---
title: 如何：导出包含 Mipmap 的纹理 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d1ad14b-44fb-4cf0-a995-5e2f60026524
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 847655d04359fa795f878ea921e69b1b5cd16460
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49811732"
---
# <a name="how-to-export-a-texture-that-contains-mipmaps"></a>如何：导出包含 Mipmap 的纹理
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在项目生成阶段，图像内容管道可从源图像生成 mipmap。 当不需要手动指定每个 MIP 级别的图像内容时（可通过这样做来实现特定的效果），在生成时间生成 mipmap 可确保 mipmap 内容始终保持同步，并在运行时消除生成 mipmap 的性能成本。  
  
 本文档演示了这些活动：  
  
-   将源映像配置为由图像内容管道进行处理。  
  
-   配置图像内容管道，生成 mipmap。  
  
## <a name="exporting-mipmaps"></a>导出 Mipmap  
 Mipmapping 为 3D 游戏或应用中的带纹理图面提供自动屏幕空间细节层次。 它通过纹理的预计算向下采样版本来增强游戏或应用的呈现性能，使整个纹理每次采样时不必进行向下采样。  
  
#### <a name="to-export-a-texture-that-has-mipmaps"></a>导出包含 mipmap 的纹理  
  
1. 从基本纹理开始。 加载现有图像文件，或根据[如何：创建基本纹理](../designers/how-to-create-a-basic-texture.md)所述，创建一个纹理。 若要支持 mipmap，请指定一个宽度和高度尺寸都是 2 的同次幂的纹理，如 64x64、256x256 或 512x512。  
  
2. 配置，以便由图像内容管道处理刚创建的纹理文件。 在“解决方案资源管理器”中，打开刚刚创建的纹理文件的快捷菜单，然后选择“属性”。 在“配置属性”，常规”页上，将“项目类型”属性设置为“图像内容管道”。 请确保将“内容”属性设置为“是”，并且将“从生成中排除”设置为“否”，然后选择“应用”按钮。 将出现“图像内容管道”配置属性页。  
  
3. 配置图像内容管道，生成 mipmap。 在“配置属性”、“图像内容管道”、“常规”页上，将“生成 Mip”属性设置为“是(/generatemips)”。  
  
4. 选择“确定”  按钮。  
  
   生成项目时，图像内容管线将源图像从工作格式转换为指定，包括 MIP 级别，并且结果将被复制到项目的输出目录的输出格式。



