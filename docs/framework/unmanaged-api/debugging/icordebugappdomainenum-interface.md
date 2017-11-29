---
title: Icordebugappdomainenum Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomainEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomainEnum
helpviewer_keywords: ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a77ce6e00ed4bbf866b8761d6339f4191151a6f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugappdomainenum-interface1"></a><span data-ttu-id="6fd4a-102">Icordebugappdomainenum Interface1</span><span class="sxs-lookup"><span data-stu-id="6fd4a-102">ICorDebugAppDomainEnum Interface1</span></span>
<span data-ttu-id="6fd4a-103">Sağlar `Next` belirtilen sayıda döndürür yöntemi `ICorDebugAppDomainEnum` listedeki sonraki konumunda başlayan değer.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="6fd4a-104">Bu arabirim "ICorDebugEnum" sınıfıdır.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6fd4a-105">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="6fd4a-105">Methods</span></span>  
  
|<span data-ttu-id="6fd4a-106">Yöntem</span><span class="sxs-lookup"><span data-stu-id="6fd4a-106">Method</span></span>|<span data-ttu-id="6fd4a-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6fd4a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6fd4a-108">Next yöntemi</span><span class="sxs-lookup"><span data-stu-id="6fd4a-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="6fd4a-109">Uygulama etki alanları belirtilen sayıda geçerli İmleç konumuna başlangıç koleksiyondan alır.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fd4a-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6fd4a-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fd4a-111">Bu arabirim, makineler arası veya çapraz işlem uzaktan çağrılan desteklemez.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fd4a-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="6fd4a-112">Requirements</span></span>  
 <span data-ttu-id="6fd4a-113">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fd4a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fd4a-114">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fd4a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fd4a-115">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fd4a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fd4a-116">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fd4a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd4a-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-117">See Also</span></span>  
 [<span data-ttu-id="6fd4a-118">Icordebug arabirimi</span><span class="sxs-lookup"><span data-stu-id="6fd4a-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="6fd4a-119">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="6fd4a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)