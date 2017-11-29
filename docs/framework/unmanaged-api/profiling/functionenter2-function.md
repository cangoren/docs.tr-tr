---
title: "FunctionEnter2 İşlevi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionEnter2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionEnter2
helpviewer_keywords: FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0aa1d98021dcbfc38721d7f30ad305065dced605
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="functionenter2-function"></a><span data-ttu-id="9ffcb-102">FunctionEnter2 İşlevi</span><span class="sxs-lookup"><span data-stu-id="9ffcb-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="9ffcb-103">Profil Oluşturucu denetim bir işlevine geçirilen ve çerçeve ve işlev bağımsız değişkenleri yığını hakkında bilgi sağlayan bildirir.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="9ffcb-104">Bu işlevin yerini [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-104">This function supersedes the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ffcb-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="9ffcb-105">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ffcb-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="9ffcb-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="9ffcb-107">[in] Denetim geçirilen işlevi tanımlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-107">[in] The identifier of the function to which control is passed.</span></span>  
  
 `clientData`  
 <span data-ttu-id="9ffcb-108">[in] Profil oluşturucu kullanılarak daha önce belirtilen açmayla işlevi tanımlayıcı [Functionıdmapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-108">[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="9ffcb-109">[in] A `COR_PRF_FRAME_INFO` noktalarını yığın çerçevesi hakkında bilgi için değer.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-109">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="9ffcb-110">Profil Oluşturucu uygulamasında bu yürütme altyapısında dön geçirilen bir donuk tanıtıcısı düşünmelisiniz [Icorprofilerınfo2::getfunctionınfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `argumentInfo`  
 <span data-ttu-id="9ffcb-111">[in] Bir işaretçi bir [cor_prf_functıon_argument_ınfo](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) işlev bağımsız değişkenleri bellekte konumları belirtir yapısı.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-111">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>  
  
 <span data-ttu-id="9ffcb-112">Bağımsız değişken bilgilere erişmek için `COR_PRF_ENABLE_FUNCTION_ARGS` bayrağı ayarlanmış olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="9ffcb-113">Profil Oluşturucu kullanabilirsiniz [Icorprofilerınfo::seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) yöntemi olay bayraklarını ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-113">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ffcb-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9ffcb-114">Remarks</span></span>  
 <span data-ttu-id="9ffcb-115">Değerlerini `func` ve `argumentInfo` parametreler sonra geçerli değildir `FunctionEnter2` değerleri değiştirebilir veya yok edilmesi için işlevi döndürür.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="9ffcb-116">`FunctionEnter2` İşlevi bir geri çağırma; uygulamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="9ffcb-117">Uygulama kullanmalısınız `__declspec`(`naked`) depolama sınıfı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="9ffcb-118">Yürütme altyapısı, bu işlevi çağrılmadan önce tüm kayıtları kaydetmez.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-118">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="9ffcb-119">Girişte kayan nokta birim (FPU) de dahil olmak üzere, kullandığınız tüm kayıtları kaydetmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="9ffcb-120">Çıkış yapıldığında, çağıran tarafından gönderilen tüm parametreleri kapalı pencerelerinin tarafından yığın geri yüklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="9ffcb-121">Uygulaması `FunctionEnter2` çöp toplama geciktirir çünkü engelleyebilir miyim değil.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="9ffcb-122">Yığın bir atık toplama kolay durumda olmayabileceğinden uygulama çöp toplama çalışmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="9ffcb-123">Çöp toplama bulamazsa, çalışma zamanı kadar engeller `FunctionEnter2` döndürür.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="9ffcb-124">Ayrıca, `FunctionEnter2` işlevi değil çağırmalıdır yönetilen koda veya herhangi bir şekilde neden yönetilen bellek ayırma.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ffcb-125">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="9ffcb-125">Requirements</span></span>  
 <span data-ttu-id="9ffcb-126">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ffcb-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ffcb-127">**Başlık:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="9ffcb-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="9ffcb-128">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ffcb-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ffcb-129">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ffcb-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ffcb-130">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9ffcb-130">See Also</span></span>  
 [<span data-ttu-id="9ffcb-131">FunctionLeave2 işlevi</span><span class="sxs-lookup"><span data-stu-id="9ffcb-131">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="9ffcb-132">FunctionTailcall2 işlevi</span><span class="sxs-lookup"><span data-stu-id="9ffcb-132">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="9ffcb-133">SetEnterLeaveFunctionHooks2 yöntemi</span><span class="sxs-lookup"><span data-stu-id="9ffcb-133">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="9ffcb-134">Profil oluşturma genel statik işlevleri</span><span class="sxs-lookup"><span data-stu-id="9ffcb-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)