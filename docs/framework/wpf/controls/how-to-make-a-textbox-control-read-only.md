---
title: 如何：将 TextBox 控件设为只读
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 3ba93cae5977f3c8c76f3bfa9f5732d3f0736af7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-a-textbox-control-read-only"></a>如何：将 TextBox 控件设为只读
此示例演示如何配置<xref:System.Windows.Controls.TextBox>控件不允许用户输入或修改。  
  
## <a name="example"></a>示例  
 若要防止用户修改的内容<xref:System.Windows.Controls.TextBox>控制、 设置<xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>属性设为**true**。  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>特性影响仅用户输入; 它不会影响在中设置的文本[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]说明<xref:System.Windows.Controls.TextBox>控件或设置以编程方式通过文本<xref:System.Windows.Controls.TextBox.Text%2A>属性。  
  
 默认值<xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>是**false**。  
  
## <a name="see-also"></a>请参阅  
 [TextBox 概述](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
