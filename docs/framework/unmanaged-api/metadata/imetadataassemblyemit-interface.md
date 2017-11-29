---
title: "IMetaDataAssemblyEmit 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit
helpviewer_keywords: IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af7a5fd5a564aa7366924f47b0c526aff7153521
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="e09c4-102">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="e09c4-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="e09c4-103">提供支持公共语言运行时用于解析和使用资源的自描述模型的方法。</span><span class="sxs-lookup"><span data-stu-id="e09c4-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e09c4-104">方法</span><span class="sxs-lookup"><span data-stu-id="e09c4-104">Methods</span></span>  
  
|<span data-ttu-id="e09c4-105">方法</span><span class="sxs-lookup"><span data-stu-id="e09c4-105">Method</span></span>|<span data-ttu-id="e09c4-106">描述</span><span class="sxs-lookup"><span data-stu-id="e09c4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e09c4-107">DefineAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="e09c4-107">DefineAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="e09c4-108">创建包含指定程序集的元数据的程序集数据结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="e09c4-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="e09c4-109">DefineAssemblyRef 方法</span><span class="sxs-lookup"><span data-stu-id="e09c4-109">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="e09c4-110">创建包含此程序集引用的程序集的元数据的 `AssemblyRef` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="e09c4-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="e09c4-111">DefineExportedType 方法</span><span class="sxs-lookup"><span data-stu-id="e09c4-111">DefineExportedType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="e09c4-112">创建包含指定导出类型的元数据的 `ExportedType` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="e09c4-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="e09c4-113">DefineFile 方法</span><span class="sxs-lookup"><span data-stu-id="e09c4-113">DefineFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="e09c4-114">创建包含此程序集引用的程序集的元数据的 `File` 元数据结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="e09c4-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="e09c4-115">DefineManifestResource 方法</span><span class="sxs-lookup"><span data-stu-id="e09c4-115">DefineManifestResource Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="e09c4-116">创建包含指定清单资源的元数据的 `ManifestResource` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="e09c4-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="e09c4-117">SetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="e09c4-117">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="e09c4-118">修改指定的 `Assembly` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="e09c4-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="e09c4-119">SetAssemblyRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="e09c4-119">SetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="e09c4-120">修改指定的 `AssemblyRef` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="e09c4-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="e09c4-121">SetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="e09c4-121">SetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="e09c4-122">修改指定的 `ExportedType` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="e09c4-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="e09c4-123">SetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="e09c4-123">SetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="e09c4-124">修改指定的 `File` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="e09c4-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="e09c4-125">SetManifestResourceProps 方法</span><span class="sxs-lookup"><span data-stu-id="e09c4-125">SetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="e09c4-126">修改指定的 `ManifestResource` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="e09c4-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e09c4-127">备注</span><span class="sxs-lookup"><span data-stu-id="e09c4-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e09c4-128">要求</span><span class="sxs-lookup"><span data-stu-id="e09c4-128">Requirements</span></span>  
 <span data-ttu-id="e09c4-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e09c4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e09c4-130">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e09c4-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e09c4-131">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e09c4-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e09c4-132">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e09c4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e09c4-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e09c4-133">See Also</span></span>  
 [<span data-ttu-id="e09c4-134">元数据接口</span><span class="sxs-lookup"><span data-stu-id="e09c4-134">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="e09c4-135">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="e09c4-135">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)