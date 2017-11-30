---
title: ICorDebugNativeFrame2::GetStackParameterSize Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2.GetStackParameterSize Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c265cb564718b362b1354189e59dc217b2866b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="7b064-102">ICorDebugNativeFrame2::GetStackParameterSize Metodu</span><span class="sxs-lookup"><span data-stu-id="7b064-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="7b064-103">İşletim sistemleri x86 yığında parametreleri toplam boyutu döndürür.</span><span class="sxs-lookup"><span data-stu-id="7b064-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b064-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7b064-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b064-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="7b064-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="7b064-106">[out] Yığın parametreleri toplam boyutu için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="7b064-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b064-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="7b064-107">Return Value</span></span>  
 <span data-ttu-id="7b064-108">Bu yöntem aşağıdaki belirli HRESULTs yanı sıra HRESULT yöntem hatası olduğunu gösteren hatalar.</span><span class="sxs-lookup"><span data-stu-id="7b064-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7b064-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7b064-109">HRESULT</span></span>|<span data-ttu-id="7b064-110">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7b064-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b064-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b064-111">S_OK</span></span>|<span data-ttu-id="7b064-112">Yığın boyutunu başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="7b064-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="7b064-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7b064-113">S_FALSE</span></span>|<span data-ttu-id="7b064-114">`GetStackParameterSize`x86 olmayan platformda çağrıldı.</span><span class="sxs-lookup"><span data-stu-id="7b064-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="7b064-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7b064-115">E_FAIL</span></span>|<span data-ttu-id="7b064-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="7b064-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="7b064-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7b064-117">E_INVALIDARG</span></span>|<span data-ttu-id="7b064-118">`pSize`Olan `null`.</span><span class="sxs-lookup"><span data-stu-id="7b064-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="7b064-119">Özel Durumlar</span><span class="sxs-lookup"><span data-stu-id="7b064-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b064-120">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7b064-120">Remarks</span></span>  
 <span data-ttu-id="7b064-121">[Icordebugstackwalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) yöntemleri yığına parametreler için yığın işaretçisi Ayarla değil.</span><span class="sxs-lookup"><span data-stu-id="7b064-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="7b064-122">Bunun yerine, tarafından döndürülen değer kullanabilirsiniz `GetStackParameterSize` parametrelerini ayarlamak bir yerel unwinder oluşturmak için yığın işaretçisi ayarlamak için.</span><span class="sxs-lookup"><span data-stu-id="7b064-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b064-123">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="7b064-123">Requirements</span></span>  
 <span data-ttu-id="7b064-124">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b064-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b064-125">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b064-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b064-126">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b064-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b064-127">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b064-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b064-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7b064-128">See Also</span></span>  
 [<span data-ttu-id="7b064-129">Icordebugnativeframe2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="7b064-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="7b064-130">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="7b064-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="7b064-131">Hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="7b064-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)