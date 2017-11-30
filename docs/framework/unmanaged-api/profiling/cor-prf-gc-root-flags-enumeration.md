---
title: "COR_PRF_GC_ROOT_FLAGS Numaralandırması"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_ROOT_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords: COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f340f9ad83d28b00054a0997bf4b60c750192bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="c96ef-102">COR_PRF_GC_ROOT_FLAGS Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="c96ef-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="c96ef-103">Çöp toplama kök özelliğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="c96ef-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c96ef-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c96ef-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c96ef-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="c96ef-105">Members</span></span>  
  
|<span data-ttu-id="c96ef-106">Üye</span><span class="sxs-lookup"><span data-stu-id="c96ef-106">Member</span></span>|<span data-ttu-id="c96ef-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c96ef-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="c96ef-108">Kök nesne taşınmasını çöp toplama engeller.</span><span class="sxs-lookup"><span data-stu-id="c96ef-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="c96ef-109">Kök çöp toplama engellemez.</span><span class="sxs-lookup"><span data-stu-id="c96ef-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="c96ef-110">Kök nesne yerine Nesne bir alana başvuruyor.</span><span class="sxs-lookup"><span data-stu-id="c96ef-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="c96ef-111">Nesne başvuru sayısı belirli bir değere ise kök çöp toplama engeller.</span><span class="sxs-lookup"><span data-stu-id="c96ef-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c96ef-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c96ef-112">Remarks</span></span>  
 <span data-ttu-id="c96ef-113">`COR_PRF_GC_ROOT_FLAGS`Özel kökleri hakkında ek bilgi sağlayan bir bit maskesi olan.</span><span class="sxs-lookup"><span data-stu-id="c96ef-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="c96ef-114">Ancak, tüm kökleri özel değildir.</span><span class="sxs-lookup"><span data-stu-id="c96ef-114">However, not all roots are special.</span></span> <span data-ttu-id="c96ef-115">Örneğin, bazı kökleri zayıf başvurular, sabitlenmiş veya başvuruları sayılan iç işaretçiler değildir.</span><span class="sxs-lookup"><span data-stu-id="c96ef-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="c96ef-116">Bu tür kökler için iletmek için hiçbir bayrakları vardır.</span><span class="sxs-lookup"><span data-stu-id="c96ef-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="c96ef-117">Bu nedenle, bu numaralandırma gibi kullandığınız yöntemleri [Icorprofilercallback2::rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) yöntemi, tüm bayraklar belirten bayrakları bit maskesi için Gönder 0 kapalıdır.</span><span class="sxs-lookup"><span data-stu-id="c96ef-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c96ef-118">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="c96ef-118">Requirements</span></span>  
 <span data-ttu-id="c96ef-119">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c96ef-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c96ef-120">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c96ef-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c96ef-121">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c96ef-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c96ef-122">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c96ef-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c96ef-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c96ef-123">See Also</span></span>  
 [<span data-ttu-id="c96ef-124">Profil oluşturma numaralandırmaları</span><span class="sxs-lookup"><span data-stu-id="c96ef-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)