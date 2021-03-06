---
title: 如何：为负载测试运行设置指定采样率
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings
ms.assetid: 51cbe7d6-5dfd-4842-bca3-f7f8a665dc84
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: b022b4648931bf0e403df589d37cb086fb2a9c2c
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53053044"
---
# <a name="how-to-specify-the-sample-rate-for-a-load-test-run-setting"></a>如何：为负载测试运行设置指定采样率

在用“新建负载测试向导”创建负载测试之后，可以使用“负载测试编辑器”更改属性，以满足测试需求和目标。

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

使用“负载测试编辑器”，可以在“属性”窗口中编辑运行设置的“采样率”属性值。 有关运行设置属性及其说明的完整列表，请参见[负载测试运行设置属性](../test/load-test-run-settings-properties.md)。

根据负载测试的长度，为负载测试运行设置的“采样率”属性选择适当的值。 较小的采样速率（如 5 秒默认值）需要占用负载测试结果数据库中的更多空间。 对于更长的负载测试，增加采样速率会减少收集的数据量。 有关更多信息，请参见[如何：为负载测试运行设置指定采样率](../test/how-to-specify-the-sample-rate-for-a-load-test.md)。

下面是有关采样速率的一些准则：

|负载测试持续时间|建议的采样速率|
|-|-----------------------------|
|\< 1 小时|5 秒|
|1 - 8 小时|15 秒|
|8 - 24 小时|30 秒|
|> 24 小时|60 秒|

## <a name="to-specify-performance-counter-sampling-rate-in-a-run-setting"></a>在运行设置中指定性能计数器采样速率

1.  打开一个负载测试。

     “负载测试编辑器”随即显示。 其中显示负载测试树。

2.  在负载测试树的“运行设置”文件夹中，选择要为其指定采样率的运行设置。

3.  在“视图”菜单上选择“属性窗口”。

     负载运行设置的类别和属性将显示在“属性”窗口中。

4.  在“采样率”属性中，输入一个时间值以指示负载测试收集性能计数器数据的频率。

5.  更改完此属性后，请选择“文件”菜单上的“保存”。 然后，可以使用新的“采样率”值来运行负载测试。

## <a name="see-also"></a>请参阅

- [配置负载测试运行设置](../test/configure-load-test-run-settings.md)
- [负载测试方案属性](../test/load-test-scenario-properties.md)