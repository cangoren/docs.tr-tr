---
title: "ICorDebugStepper::SetInterceptMask Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetInterceptMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a99b504c0ce58ca6b89153667598cd4c2c682d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="cccf2-102">ICorDebugStepper::SetInterceptMask Yöntemi</span><span class="sxs-lookup"><span data-stu-id="cccf2-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="cccf2-103">İçine adım adım kod türlerini belirten bir değer ayarlar.</span><span class="sxs-lookup"><span data-stu-id="cccf2-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cccf2-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="cccf2-104">Syntax</span></span>  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cccf2-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="cccf2-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="cccf2-106">[in] Kod türlerini belirtir Cordebugıntercept numaralandırması değerlerinin birleşimi.</span><span class="sxs-lookup"><span data-stu-id="cccf2-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cccf2-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cccf2-107">Remarks</span></span>  
 <span data-ttu-id="cccf2-108">Bir dinleyiciden bitini ayarlanırsa, kod kesintiye uğratan verilen türünü karşılaşıldığında Adımlayıcı tamamlayın.</span><span class="sxs-lookup"><span data-stu-id="cccf2-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="cccf2-109">Bit işaretli değilse, intercepting kod atlanacak.</span><span class="sxs-lookup"><span data-stu-id="cccf2-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="cccf2-110">`SetInterceptMask` Yöntemi olabilir ile öngörülemeyen etkileşimleri [ICorDebugStepper::setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (açısından kullanıcının).</span><span class="sxs-lookup"><span data-stu-id="cccf2-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="cccf2-111">Örneğin, varsa yalnızca görünür (diğer bir deyişle, iç olmayan) sınıf başlatma kodunu kısmı eksik eşleme bilgilerini ve değil STOP_NO_MAPPING_INFO ayarlayın (bkz [ICorDebugStepper::setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) yöntemi ve CorDebugUnmappedStop numaralandırması için) sınıfı başlatma Adımlayıcı adım.</span><span class="sxs-lookup"><span data-stu-id="cccf2-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="cccf2-112">Varsayılan olarak, yalnızca INTERCEPT_NONE değeri `CorDebugIntercept` numaralandırma kullanılır.</span><span class="sxs-lookup"><span data-stu-id="cccf2-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cccf2-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="cccf2-113">Requirements</span></span>  
 <span data-ttu-id="cccf2-114">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cccf2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cccf2-115">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cccf2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cccf2-116">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cccf2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cccf2-117">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cccf2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>