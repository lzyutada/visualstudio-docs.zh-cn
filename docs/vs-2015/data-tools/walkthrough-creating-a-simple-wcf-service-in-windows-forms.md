---
title: 演练： 在 Windows 窗体中创建一个简单的 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF, walkthrough [Visual Studio]
- WCF, Visual Studio tools for
- WCF services
- WCF services, walkthrough
ms.assetid: 5fef1a64-27a4-4f10-aa57-29023e28a2d6
caps.latest.revision: 29
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6e73659c2d28cf97a8a7136ed8232cfbc5f0b77c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49247203"
---
# <a name="walkthrough-creating-a-simple-wcf-service-in-windows-forms"></a>演练： 在 Windows 窗体中创建一个简单的 WCF 服务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
本演练演示如何创建一个简单[!INCLUDE[vsindigo](../includes/vsindigo-md.md)]服务并进行测试，然后从 Windows 窗体应用程序访问它。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="creating-the-service"></a>创建服务  
  
#### <a name="to-create-a-wcf-service"></a>要创建 WCF 服务  
  
1.  在 **“文件”** 菜单上指向 **“新建”** ，然后单击 **“项目”**。  
  
2.  在中**新的项目**对话框框中，展开**Visual Basic**或**Visual C#** 节点，然后单击**WCF**后, 跟**WCF服务库**。 单击**确定**以打开该项目。  
  
     ![WCF 服务库项目](../data-tools/media/wcf1.PNG "wcf1")  
  
    > [!NOTE]
    >  这将创建可以测试和访问的工作服务。 以下两个步骤演示您可以如何修改使用不同数据类型的默认方法。 在实际应用中，您还会向服务中添加您自己的函数。  
  
3.  ![IService1 文件](../data-tools/media/wcf2.png "wcf2")  
  
     在中**解决方案资源管理器**、 双击 IService1.vb 或 IService1.cs 并找到以下行：  
  
     [！ 代码-c# [WCFWalkthrough #4] (../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/iservice1 (2).cs #4)] [！ 代码 vb [WCFWalkthrough #4] (../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/iservice1 (2).vb #4)]  
  
     把`value`参数的类型更改为`String`：  
  
     [!code-csharp[WCFWalkthrough#1](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/iservice1.cs#1)]
     [!code-vb[WCFWalkthrough#1](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/iservice1.vb#1)]  
  
     在上面的代码中，请注意`<OperationContract()>`或`[OperationContract]`属性。 这些属性是由服务公开的任何方法所必需的。  
  
4.  ![Service1 文件](../data-tools/media/wcf3.png "wcf3")  
  
     在中**解决方案资源管理器**、 双击 Service1.vb 或 Service1.cs 并找到以下行：  
  
     [！ 代码-c# [WCFWalkthrough #5] (../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/service1 (2).cs #5)] [！ 代码 vb [WCFWalkthrough #5] (../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/service1 (2).vb #5)]  
  
     更改值参数类型为`String`：  
  
     [!code-csharp[WCFWalkthrough#2](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/service1.cs#2)]
     [!code-vb[WCFWalkthrough#2](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/service1.vb#2)]  
  
## <a name="testing-the-service"></a>正在测试服务  
  
#### <a name="to-test-a-wcf-service"></a>若要测试 WCF 服务  
  
1.  按**F5**来运行服务。 一个**WCF 测试客户端**将显示窗体，它将加载此服务。  
  
2.  在中**WCF 测试客户端**窗体中，双击**getdata （)** 待方法**IService1**。 **GetData**将显示选项卡。  
  
     ![GetData&#40; &#41;方法](../data-tools/media/wcf4.png "wcf4")  
  
3.  在中**请求**框中，选择**值**字段，并键入`Hello`。  
  
     ![值字段](../data-tools/media/wcf5.png "wcf5")  
  
4.  单击**Invoke**按钮。 如果**安全警告**对话框中，单击**确定**。 结果将显示在**响应**框。  
  
     ![响应框中的结果](../data-tools/media/wcf6.png "wcf6")  
  
5.  上**文件**菜单上，单击**退出**关闭测试窗体。  
  
## <a name="accessing-the-service"></a>访问服务  
  
#### <a name="to-reference-a-wcf-service"></a>若要引用 WCF 服务  
  
1.  上**文件**菜单，依次指向**添加**，然后单击**新项目**。  
  
2.  在中**新的项目**对话框框中，展开**Visual Basic**或**Visual C#** 节点，然后选择**Windows**，然后选择**Windows 窗体应用程序**。 单击**确定**以打开该项目。  
  
     ![Windows 窗体应用程序项目](../data-tools/media/wcf7.png "wcf7")  
  
3.  右键单击**WindowsApplication1**然后单击**添加服务引用**。 **添加服务引用**对话框将出现。  
  
4.  在中**添加服务引用**对话框中，单击**Discover**。  
  
     ![添加服务引用对话框](../data-tools/media/wcf8.png "wcf8")  
  
     **Service1**将显示在**Services**窗格。  
  
5.  单击**确定**添加服务引用。  
  
#### <a name="to-build-a-client-application"></a>要创建客户端应用程序。  
  
1.  在中**解决方案资源管理器**，双击**Form1.vb**或**Form1.cs**若要打开 Windows 窗体设计器，如果已打开。  
  
2.  从**工具箱**，拖动`TextBox`控件，`Label`控件，和一个`Button`拖到窗体控件。  
  
     ![将控件添加到窗体](../data-tools/media/wcf9.png "wcf9")  
  
3.  双击 `Button` 并将下面的代码添加到 `Click` 事件处理程序：  
  
     [!code-csharp[WCFWalkthrough#3](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/form1.cs#3)]
     [!code-vb[WCFWalkthrough#3](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/form1.vb#3)]  
  
4.  在中**解决方案资源管理器**，右键单击**WindowsApplication1**然后单击**设为启动项目**。  
  
5.  按**F5**以运行该项目。 输入一些文本，然后单击按钮。 该标签将显示“输入：”和您输入的文本。  
  
     ![显示结果窗体](../data-tools/media/wcf10.png "wcf10")  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 中的 Windows Communication Foundation 服务和 WCF 数据服务](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)

