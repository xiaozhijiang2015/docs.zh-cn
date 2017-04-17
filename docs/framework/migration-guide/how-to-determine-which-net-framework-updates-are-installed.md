---
title: "如何：确定安装了哪些 .NET Framework 更新 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, 确定更新"
  - "更新, 确定 .NET Framework"
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
caps.latest.revision: 6
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# 如何：确定安装了哪些 .NET Framework 更新
安装在计算机上的各个版本 .NET Framework 已安装的更新都列在 Windows 注册表中。  可以使用注册表编辑器 \(regedit.exe\) 查看此信息。  
  
 在注册表编辑器中，.NET Framework 版本和每个版本已安装的更新都保存在不同的子项中。  有关检测已安装的版本号的信息，请参阅[如何：确定安装了哪些 .NET Framework 版本](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)。  有关安装 .NET Framework 的信息，请参阅[安装指南](../../../docs/framework/install/guide-for-developers.md)。  
  
### 若要查找已安装的更新  
  
1.  打开程序 **regedit.exe**。  在 Windows 8 和更高版本上打开“开始”屏幕，并键入的名称。  在早期版本的 Windows 中，在**“开始”**菜单上，选择**“运行”**，然后在**“打开”**框中，输入**“regedit.exe”**。  
  
     你必须具有管理凭据才能运行 regedit.exe。  
  
2.  在注册表编辑器中，打开以下子项：  
  
     HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Updates  
  
     已安装的更新在标识适用的 .NET Framework 版本的子项下方列出。  每个更新均由知识库 \(KB\) 编号进行标识。  
  
## 示例  
 以下代码以编程方式确定已安装在计算机上的 .NET Framework 更新。  你必须具有管理凭据才能运行此示例。  
  
 [!code-csharp[ListUpdates#1](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs#1)]
 [!code-vb[ListUpdates#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb#1)]  
  
 该示例生成类似下面内容的输出：  
  
```  
  
Microsoft .NET Framework 3.5 SP1  
  KB953595  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB953595)  
  SP1  
    KB2657424  Security Update for Microsoft .NET Framework 3.5 SP1 (KB2657424)  
    KB958484  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB958484)  
    KB963707  Update for Microsoft .NET Framework 3.5 SP1 (KB963707)  
Microsoft .NET Framework 4 Client Profile  
  KB2160841  Security Update for Microsoft .NET Framework 4 Client Profile (KB2160841)  
  KB2446708  Security Update for Microsoft .NET Framework 4 Client Profile (KB2446708)  
  KB2468871  Update for Microsoft .NET Framework 4 Client Profile (KB2468871)  
  KB2478663  Security Update for Microsoft .NET Framework 4 Client Profile (KB2478663)  
  KB2518870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2518870)  
  KB2533523  Update for Microsoft .NET Framework 4 Client Profile (KB2533523)  
  KB2539636  Security Update for Microsoft .NET Framework 4 Client Profile (KB2539636)  
  KB2572078  Security Update for Microsoft .NET Framework 4 Client Profile (KB2572078)  
  KB2633870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2633870)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Client Profile (KB2656351)  
Microsoft .NET Framework 4 Extended  
  KB2416472  Security Update for Microsoft .NET Framework 4 Extended (KB2416472)  
  KB2468871  Update for Microsoft .NET Framework 4 Extended (KB2468871)  
  KB2487367  Security Update for Microsoft .NET Framework 4 Extended (KB2487367)  
  KB2533523  Update for Microsoft .NET Framework 4 Extended (KB2533523)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Extended (KB2656351)  
  
```  
  
## 请参阅  
 [如何：确定安装了哪些 .NET Framework 版本](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)   
 [安装指南](../../../docs/framework/install/guide-for-developers.md)   
 [版本和依赖关系](../../../docs/framework/migration-guide/versions-and-dependencies.md)