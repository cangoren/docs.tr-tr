---
title: "IHostTaskManager::SetCLRTaskManager Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SetCLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ec0d515ad4c0bc21e1036f20f17bf168d7af79d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="c085a-102">IHostTaskManager::SetCLRTaskManager Yöntemi</span><span class="sxs-lookup"><span data-stu-id="c085a-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="c085a-103">Ana bilgisayar için bir arabirim işaretçisi sağlayan bir [Iclrtaskmanager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) ortak dil çalışma zamanı tarafından (CLR) uygulanan örneği.</span><span class="sxs-lookup"><span data-stu-id="c085a-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c085a-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c085a-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c085a-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="c085a-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="c085a-106">[in] Bir işaretçi bir `ICLRTaskManager` ortak dil çalışma zamanı tarafından uygulanan örneği.</span><span class="sxs-lookup"><span data-stu-id="c085a-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c085a-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="c085a-107">Return Value</span></span>  
  
|<span data-ttu-id="c085a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c085a-108">HRESULT</span></span>|<span data-ttu-id="c085a-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c085a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c085a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c085a-110">S_OK</span></span>|<span data-ttu-id="c085a-111">`SetCLRTaskManager`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="c085a-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="c085a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c085a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c085a-113">CLR süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="c085a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c085a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c085a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c085a-115">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="c085a-115">The call timed out.</span></span>|  
|<span data-ttu-id="c085a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c085a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c085a-117">Arayan kilidi kendisine ait değil.</span><span class="sxs-lookup"><span data-stu-id="c085a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c085a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c085a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c085a-119">Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.</span><span class="sxs-lookup"><span data-stu-id="c085a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c085a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c085a-120">E_FAIL</span></span>|<span data-ttu-id="c085a-121">Bilinmeyen yıkıcı bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="c085a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c085a-122">Bir yöntem E_FAIL döndüğünde, CLR artık işlemi içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="c085a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c085a-123">Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="c085a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c085a-124">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c085a-124">Remarks</span></span>  
 <span data-ttu-id="c085a-125">Çalışma zamanı çağrıları `SetCLRTaskManager` ana bilgisayar için bir arabirim işaretçisi sağlamak için bir `ICLRTaskManager` örneği.</span><span class="sxs-lookup"><span data-stu-id="c085a-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c085a-126">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="c085a-126">Requirements</span></span>  
 <span data-ttu-id="c085a-127">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c085a-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c085a-128">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c085a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c085a-129">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="c085a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c085a-130">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c085a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c085a-131">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c085a-131">See Also</span></span>  
 [<span data-ttu-id="c085a-132">Iclrtask arabirimi</span><span class="sxs-lookup"><span data-stu-id="c085a-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="c085a-133">Iclrtaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="c085a-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="c085a-134">Ihosttask arabirimi</span><span class="sxs-lookup"><span data-stu-id="c085a-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="c085a-135">Ihosttaskmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="c085a-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)