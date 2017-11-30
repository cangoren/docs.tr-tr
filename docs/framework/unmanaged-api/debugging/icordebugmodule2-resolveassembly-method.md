---
title: "ICorDebugModule2::ResolveAssembly Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.ResolveAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 37ddb0e8871d9ec5f8eed4f00d81098feafb01de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="86d2f-102">ICorDebugModule2::ResolveAssembly Yöntemi</span><span class="sxs-lookup"><span data-stu-id="86d2f-102">ICorDebugModule2::ResolveAssembly Method</span></span>
<span data-ttu-id="86d2f-103">Belirtilen meta veri simgesi tarafından başvurulan derleme çözümler.</span><span class="sxs-lookup"><span data-stu-id="86d2f-103">Resolves the assembly referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86d2f-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="86d2f-104">Syntax</span></span>  
  
```  
HRESULT ResolveAssembly (  
    [in]  mdToken             tkAssemblyRef,  
    [out] ICorDebugAssembly   **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86d2f-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="86d2f-105">Parameters</span></span>  
 `tkAsemblyRef`  
 <span data-ttu-id="86d2f-106">[in] Bir `mdToken` bütünleştirilmiş koduna başvuruyor değeri.</span><span class="sxs-lookup"><span data-stu-id="86d2f-106">[in] An `mdToken` value that references the assembly.</span></span>  
  
 `ppAssembly`  
 <span data-ttu-id="86d2f-107">[out] Bir işaretçi adresine Icordebugassembly nesnenin derleme temsil eder.</span><span class="sxs-lookup"><span data-stu-id="86d2f-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86d2f-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="86d2f-108">Remarks</span></span>  
 <span data-ttu-id="86d2f-109">Derleme zaten ne zaman yüklenmezse `ResolveAssembly` çağrılır, HRESULT CORDBG_E_CANNOT_RESOLVE_ASSEMBLY değeri döndürülür.</span><span class="sxs-lookup"><span data-stu-id="86d2f-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86d2f-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="86d2f-110">Requirements</span></span>  
 <span data-ttu-id="86d2f-111">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86d2f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86d2f-112">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86d2f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86d2f-113">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86d2f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86d2f-114">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86d2f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>