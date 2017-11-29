---
title: "ICorDebugManagedCallback::ExitThread Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ExitThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a00f5e13f2f353fbe33dbcf0a7431573b049c5d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="5d011-102">ICorDebugManagedCallback::ExitThread Yöntemi</span><span class="sxs-lookup"><span data-stu-id="5d011-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="5d011-103">Hata ayıklayıcı yönetilen kod yürütülmekte olan bir iş parçacığı yaptı bildirir.</span><span class="sxs-lookup"><span data-stu-id="5d011-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d011-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="5d011-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d011-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="5d011-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5d011-106">[in] Yönetilen iş parçacığı içeren uygulama etki alanını temsil eden bir Icordebugappdomain nesnesi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="5d011-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="5d011-107">[in] Yönetilen iş parçacığı temsil eden bir Icordebugthread nesnesi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="5d011-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d011-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5d011-108">Remarks</span></span>  
 <span data-ttu-id="5d011-109">Bir kez `ExitThread` geri çağırma harekete, iş parçacığı iş parçacığı numaralandırmalara görünmeyecek.</span><span class="sxs-lookup"><span data-stu-id="5d011-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d011-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="5d011-110">Requirements</span></span>  
 <span data-ttu-id="5d011-111">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d011-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d011-112">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d011-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d011-113">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d011-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d011-114">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d011-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d011-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5d011-115">See Also</span></span>  
 [<span data-ttu-id="5d011-116">Icordebugmanagedcallback arabirimi</span><span class="sxs-lookup"><span data-stu-id="5d011-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)