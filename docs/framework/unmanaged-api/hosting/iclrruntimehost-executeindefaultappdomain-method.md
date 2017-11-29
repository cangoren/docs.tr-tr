---
title: "ICLRRuntimeHost::ExecuteInDefaultAppDomain Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ae0e006cdaa983fd7a3c9f650b61d4579aeaf0ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="0f74f-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Yöntemi</span><span class="sxs-lookup"><span data-stu-id="0f74f-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="0f74f-103">Belirtilen türe ait belirtilen yöntem belirtilen yönetilen derlemedeki çağırır.</span><span class="sxs-lookup"><span data-stu-id="0f74f-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f74f-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0f74f-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f74f-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="0f74f-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="0f74f-106">[in] Yolu <xref:System.Reflection.Assembly> tanımlayan <xref:System.Type> olan yöntemdir çağrılacak.</span><span class="sxs-lookup"><span data-stu-id="0f74f-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="0f74f-107">[in] Adını <xref:System.Type> çağrılacak yöntemi tanımlar.</span><span class="sxs-lookup"><span data-stu-id="0f74f-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="0f74f-108">[in] Çağrılacak yöntemin adı.</span><span class="sxs-lookup"><span data-stu-id="0f74f-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="0f74f-109">[in] Yönteme dizesi parametresi.</span><span class="sxs-lookup"><span data-stu-id="0f74f-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="0f74f-110">[out] Çağrılan yöntem tarafından döndürülen tamsayı değeri.</span><span class="sxs-lookup"><span data-stu-id="0f74f-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f74f-111">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="0f74f-111">Return Value</span></span>  
  
|<span data-ttu-id="0f74f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f74f-112">HRESULT</span></span>|<span data-ttu-id="0f74f-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0f74f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f74f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f74f-114">S_OK</span></span>|<span data-ttu-id="0f74f-115">`ExecuteInDefaultAppDomain`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="0f74f-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="0f74f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f74f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f74f-117">Ortak dil çalışma zamanı (CLR) süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="0f74f-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f74f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f74f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f74f-119">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="0f74f-119">The call timed out.</span></span>|  
|<span data-ttu-id="0f74f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f74f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f74f-121">Arayan kilidi kendisine ait değil.</span><span class="sxs-lookup"><span data-stu-id="0f74f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f74f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f74f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f74f-123">Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.</span><span class="sxs-lookup"><span data-stu-id="0f74f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f74f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f74f-124">E_FAIL</span></span>|<span data-ttu-id="0f74f-125">Bilinmeyen yıkıcı bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="0f74f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f74f-126">Bir yöntem E_FAIL döndürürse, CRL artık işlemi içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="0f74f-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="0f74f-127">Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="0f74f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f74f-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0f74f-128">Remarks</span></span>  
 <span data-ttu-id="0f74f-129">Çağrılan yöntem aşağıdaki imzaya sahip olmalıdır:</span><span class="sxs-lookup"><span data-stu-id="0f74f-129">The invoked method must have the following signature:</span></span>  
  
```  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="0f74f-130">Burada `pwzMethodName` çağrılan yöntem adını temsil eder ve `pwzArgument` bu yönteme geçirilen parametre olarak dize değeri temsil eder.</span><span class="sxs-lookup"><span data-stu-id="0f74f-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="0f74f-131">HRESULT değer S_OK için ayarlanırsa `pReturnValue` çağrılan yöntemi tarafından döndürülen tamsayı değerine ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="0f74f-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="0f74f-132">Aksi takdirde, `pReturnValue` ayarlı değil.</span><span class="sxs-lookup"><span data-stu-id="0f74f-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f74f-133">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="0f74f-133">Requirements</span></span>  
 <span data-ttu-id="0f74f-134">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f74f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f74f-135">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0f74f-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f74f-136">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="0f74f-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f74f-137">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f74f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f74f-138">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0f74f-138">See Also</span></span>  
 [<span data-ttu-id="0f74f-139">Iclrruntimehost arabirimi</span><span class="sxs-lookup"><span data-stu-id="0f74f-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)