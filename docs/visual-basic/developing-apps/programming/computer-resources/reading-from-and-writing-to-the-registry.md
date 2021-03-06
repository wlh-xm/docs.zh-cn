---
title: 读取和写入注册表 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
ms.openlocfilehash: 6ce05b956ebf9a544eb8c95165b0f709c694f334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a>读取和写入注册表 (Visual Basic)
本主题介绍与注册表相关的任务和概念性主题。  
  
 在 Visual Basic 中编程时，可以通过 Visual Basic 提供的函数或者通过 .NET Framework 的注册表类访问注册表。 注册表托管有关操作系统的信息，以及有关计算机上托管的应用程序的信息。 对注册表进行操作时，如果允许对系统资源或受保护的信息进行不适当的访问，则可能会降低安全性。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：创建注册表项并设置其值](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 介绍如何使用 `My.Computer.Registry` 对象的 `CreateSubKey` 和 `SetValue` 方法创建注册表项并设置其值。  
  
 [如何：从注册表项读取值](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 介绍如何使用 `My.Computer.Registry` 对象的 `GetValue` 方法读取注册表项的值。  
  
 [如何：删除注册表项](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 介绍如何使用 `My.Computer.Registry.CurrentUser` 属性的 `DeleteSubKey` 方法删除注册表项。  
  
 [使用 Microsoft.Win32 命名空间读取和写入注册表](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 介绍如何使用 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 的 `Registry` 和 `RegistryKey` 类访问注册表。  
  
 [安全性与注册表](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 讨论与注册表相关的安全问题。  
  
## <a name="related-sections"></a>相关章节  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 列出并说明 `My.Computer.Registry` 对象的成员。  
  
 <xref:Microsoft.Win32.Registry>  
 提供 `Registry` 类的概述和指向各个注册表项和成员的链接。
