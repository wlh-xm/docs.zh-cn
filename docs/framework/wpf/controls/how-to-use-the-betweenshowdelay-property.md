---
title: 如何：使用 BetweenShowDelay 属性
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: 7d48fb859ec6d37abd2490bc718d58cbdaa67f13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-betweenshowdelay-property"></a>如何：使用 BetweenShowDelay 属性
此示例演示如何使用<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>时间属性，以便快速显示工具提示-且很少或没有延迟-当用户将移动鼠标指针从一个工具提示直接到另一个。  
  
## <a name="example"></a>示例  
 在下面的示例中，<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>属性设置为 1 秒 （1000年毫秒为单位） 和<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>设置为 2 秒 （2000年毫秒） 的工具提示<xref:System.Windows.Shapes.Ellipse>控件。 如果显示一个省略号的工具提示，然后将鼠标指针移动到另一个椭圆在两个秒和暂停在其上时，第二个椭圆的工具提示将立即显示。  
  
 在以下情况下，任一<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>适用，这将导致产生要等待一秒才会出现的第二个椭圆的工具提示：  
  
-   如果的时间将移到第二个按钮将为多个两秒。  
  
-   如果工具提示的第一个椭圆的时间间隔开始时不可见。  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [帮助主题](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [ToolTip 概述](../../../../docs/framework/wpf/controls/tooltip-overview.md)
