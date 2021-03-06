---
title: ICorProfilerInfo7::GetInMemorySymbolsLength 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e662270fc8db3fb85e058e8d4f3346f58f79bb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>ICorProfilerInfo7::GetInMemorySymbolsLength 方法
[仅在 .NET Framework 4.6.1 及更高版本中受支持]  
  
 返回的内存中的符号流的长度。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
#### <a name="parameters"></a>参数  
 `moduleId`  
 [in]包含内存中流的模块的标识符。  
  
 pCountSymbolBytes  
 [out]指向的指针`DWORD`，方法返回时，包含值的以字节为单位的流长度。  
  
## <a name="return-value"></a>返回值  
 该方法返回`S_OK`如果内存流的长度就可以确定，即使它是零 (0)。  
  
 该方法返回`CORPROF_E_MODULE_IS_DYNAMIC`如果方法使用创建<xref:System.Reflection.Emit?displayProperty=nameWithType>。  
  
## <a name="remarks"></a>备注  
 如果该模块具有内存中的符号，将流的长度放置在`pCountSymbolBytes`。 如果该模块不具有内存中符号`*pCountSymbolBytes = 0`。  
  
> [!NOTE]
>  当前实现不支持 Reflection.Emit。 如果通过使用 Reflection.Emit 创建模块，该方法返回`CORPROF_E_MODULE_IS_DYNAMIC`。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo7 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
