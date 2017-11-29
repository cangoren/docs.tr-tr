---
title: ICorDebugFunction Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction
helpviewer_keywords: ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327ef9f74e94e3b1b20e78eb6a833038b5bfe16d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction-interface1"></a><span data-ttu-id="427bc-102">ICorDebugFunction Interface1</span><span class="sxs-lookup"><span data-stu-id="427bc-102">ICorDebugFunction Interface1</span></span>
<span data-ttu-id="427bc-103">Yönetilen bir işlevi veya yöntemi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="427bc-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="427bc-104">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="427bc-104">Methods</span></span>  
  
|<span data-ttu-id="427bc-105">Yöntem</span><span class="sxs-lookup"><span data-stu-id="427bc-105">Method</span></span>|<span data-ttu-id="427bc-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="427bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="427bc-107">CreateBreakpoint yöntemi</span><span class="sxs-lookup"><span data-stu-id="427bc-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="427bc-108">Bu işlev, başında bir kesme noktası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="427bc-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="427bc-109">GetClass yöntemi</span><span class="sxs-lookup"><span data-stu-id="427bc-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="427bc-110">Bu işlev bir üyesidir sınıfı temsil eden bir Icordebugclass nesnesi alır.</span><span class="sxs-lookup"><span data-stu-id="427bc-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="427bc-111">GetCurrentVersionNumber yöntemi</span><span class="sxs-lookup"><span data-stu-id="427bc-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="427bc-112">Bu işleve yapılan en son düzenleme sürüm numarasını alır.</span><span class="sxs-lookup"><span data-stu-id="427bc-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="427bc-113">Getılcode yöntemi</span><span class="sxs-lookup"><span data-stu-id="427bc-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="427bc-114">Bu işlev için Microsoft Ara dili (MSIL) kodu alır.</span><span class="sxs-lookup"><span data-stu-id="427bc-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="427bc-115">GetLocalVarSigToken yöntemi</span><span class="sxs-lookup"><span data-stu-id="427bc-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="427bc-116">Meta verileri, bu tarafından temsil edilen işlevinin yerel değişken imzası için belirteç alır `ICorDebugFunction` örneği.</span><span class="sxs-lookup"><span data-stu-id="427bc-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="427bc-117">GetModule yöntemi</span><span class="sxs-lookup"><span data-stu-id="427bc-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="427bc-118">Bu işlevin tanımlı olduğu modülü alır.</span><span class="sxs-lookup"><span data-stu-id="427bc-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="427bc-119">GetNativeCode yöntemi</span><span class="sxs-lookup"><span data-stu-id="427bc-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="427bc-120">Bu işlev için yerel kodu alır.</span><span class="sxs-lookup"><span data-stu-id="427bc-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="427bc-121">GetToken yöntemi</span><span class="sxs-lookup"><span data-stu-id="427bc-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="427bc-122">Meta verileri bu işlev için belirteç alır.</span><span class="sxs-lookup"><span data-stu-id="427bc-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="427bc-123">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="427bc-123">Remarks</span></span>  
 <span data-ttu-id="427bc-124">`ICorDebugFunction` Arabirimi genel tür parametreleri olan bir işlevi temsil etmiyor.</span><span class="sxs-lookup"><span data-stu-id="427bc-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="427bc-125">Örneğin, bir `ICorDebugFunction` örneği temsil eden `Func<T>` ama `Func<string>`.</span><span class="sxs-lookup"><span data-stu-id="427bc-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="427bc-126">Çağrı [Icordebugılframe2::enumeratetypeparameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) genel tür parametreleri alınamıyor.</span><span class="sxs-lookup"><span data-stu-id="427bc-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="427bc-127">Bir yöntemin meta veri simgesi arasındaki ilişkiyi `mdMethodDef`ve bir yöntemin `ICorDebugFunction` Düzenle ve devam et izin verilip işlev bağlı nesne bağlıdır:</span><span class="sxs-lookup"><span data-stu-id="427bc-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
-   <span data-ttu-id="427bc-128">Düzenle ve devam et izin verilmez, işlev arasında bire bir ilişki var. `ICorDebugFunction` nesne ve `mdMethodDef` belirteci.</span><span class="sxs-lookup"><span data-stu-id="427bc-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="427bc-129">Diğer bir deyişle, işlev varsa `ICorDebugFunction` nesne ve bir `mdMethodDef` belirteci.</span><span class="sxs-lookup"><span data-stu-id="427bc-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
-   <span data-ttu-id="427bc-130">Düzenle ve devam et izin veriliyorsa işlev arasında çoktan bire bir ilişki var. `ICorDebugFunction` nesne ve `mdMethodDef` belirteci.</span><span class="sxs-lookup"><span data-stu-id="427bc-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="427bc-131">Diğer bir deyişle, birçok örneklerini işlevi olabilir `ICorDebugFunction`, bir işlev her sürümü, ancak yalnızca bir `mdMethodDef` belirteci.</span><span class="sxs-lookup"><span data-stu-id="427bc-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="427bc-132">Bu arabirim, makineler arası veya çapraz işlem uzaktan çağrılan desteklemez.</span><span class="sxs-lookup"><span data-stu-id="427bc-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="427bc-133">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="427bc-133">Requirements</span></span>  
 <span data-ttu-id="427bc-134">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="427bc-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="427bc-135">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="427bc-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="427bc-136">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="427bc-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="427bc-137">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="427bc-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="427bc-138">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="427bc-138">See Also</span></span>  
 [<span data-ttu-id="427bc-139">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="427bc-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)