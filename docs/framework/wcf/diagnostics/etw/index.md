---
title: 使用 ETW 进行分析跟踪
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 210418b8a8765a1fc59658e9df57c92ce087c95f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="analytic-tracing-with-etw"></a>使用 ETW 进行分析跟踪
Windows Communication Foundation (WCF) 分析跟踪提供了一个方法来捕获的 WCF 服务执行期间的诊断信息。 WCF 堆栈，以便在生产环境中的 WCF 服务的故障排除中的关键点处发出的 WCF 分析跟踪事件。 WCF 服务的分析跟踪最小对性能有影响的产品服务器承载[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]WCF 服务，因为这些事件可以非常高效地发送到 Windows 事件跟踪 (ETW) 会话。  
  
## <a name="in-this-section"></a>本节内容  
 [分析跟踪概述](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 讨论 WCF 分析跟踪中的工作方式[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]。  
  
 [动态启用分析跟踪](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 讨论如何使用 ETW 动态启用或禁用跟踪。  
  
 [配置消息流跟踪](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 描述如何配置消息流跟踪。  
  
 [分析跟踪事件参考](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 显示一张表，其中包括事件 ID 及其事件级别、事件消息和关键字。  
  
## <a name="see-also"></a>请参阅  
 [WCF Services and Event Tracing for Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [在 Windows 中将事件跟踪到事件跟踪](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
