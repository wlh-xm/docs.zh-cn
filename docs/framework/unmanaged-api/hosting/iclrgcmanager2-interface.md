---
title: "ICLRGCManager2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2
helpviewer_keywords: ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b025ec31e3797fec3ac184929f1274cb5f68501b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="69a80-102">ICLRGCManager2 接口</span><span class="sxs-lookup"><span data-stu-id="69a80-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="69a80-103">提供允许的主机与公共语言运行时的垃圾回收系统进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="69a80-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69a80-104">方法</span><span class="sxs-lookup"><span data-stu-id="69a80-104">Methods</span></span>  
  
|<span data-ttu-id="69a80-105">方法</span><span class="sxs-lookup"><span data-stu-id="69a80-105">Method</span></span>|<span data-ttu-id="69a80-106">描述</span><span class="sxs-lookup"><span data-stu-id="69a80-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69a80-107">SetGCStartupLimitsEx 方法</span><span class="sxs-lookup"><span data-stu-id="69a80-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="69a80-108">设置的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小。</span><span class="sxs-lookup"><span data-stu-id="69a80-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="69a80-109">使第 0 代和段大小大于`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="69a80-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69a80-110">备注</span><span class="sxs-lookup"><span data-stu-id="69a80-110">Remarks</span></span>  
 <span data-ttu-id="69a80-111">此接口继承自[ICLRGCManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="69a80-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="69a80-112">公共语言运行时 (CLR) 实现与托管其垃圾回收机制<xref:System.GC>类型。</span><span class="sxs-lookup"><span data-stu-id="69a80-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="69a80-113">有关垃圾回收系统的详细信息，请参阅[垃圾回收](../../../../docs/standard/garbage-collection/index.md)。</span><span class="sxs-lookup"><span data-stu-id="69a80-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69a80-114">要求</span><span class="sxs-lookup"><span data-stu-id="69a80-114">Requirements</span></span>  
 <span data-ttu-id="69a80-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="69a80-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69a80-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="69a80-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69a80-117">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="69a80-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69a80-118">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69a80-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a80-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69a80-119">See Also</span></span>  
 [<span data-ttu-id="69a80-120">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="69a80-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="69a80-121">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="69a80-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="69a80-122">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="69a80-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="69a80-123">CLR 承载接口添加在.NET Framework 4 和 4.5</span><span class="sxs-lookup"><span data-stu-id="69a80-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="69a80-124">承载接口</span><span class="sxs-lookup"><span data-stu-id="69a80-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="69a80-125">承载</span><span class="sxs-lookup"><span data-stu-id="69a80-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)