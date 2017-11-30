---
title: "ICorRuntimeHost::Start Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.Start
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f259a28009ed12583bc8f7baa63e2ca17e4a21e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="6f0dd-102">ICorRuntimeHost::Start Yöntemi</span><span class="sxs-lookup"><span data-stu-id="6f0dd-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="6f0dd-103">Ortak dil çalışma zamanı (CLR) başlatır.</span><span class="sxs-lookup"><span data-stu-id="6f0dd-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f0dd-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6f0dd-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6f0dd-105">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="6f0dd-105">Return Value</span></span>  
  
|<span data-ttu-id="6f0dd-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f0dd-106">HRESULT</span></span>|<span data-ttu-id="6f0dd-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6f0dd-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f0dd-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f0dd-108">S_OK</span></span>|<span data-ttu-id="6f0dd-109">İşlem başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="6f0dd-109">The operation was successful.</span></span>|  
|<span data-ttu-id="6f0dd-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6f0dd-110">S_FALSE</span></span>|<span data-ttu-id="6f0dd-111">İşlemi tamamlayamadı.</span><span class="sxs-lookup"><span data-stu-id="6f0dd-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="6f0dd-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6f0dd-112">E_FAIL</span></span>|<span data-ttu-id="6f0dd-113">Bilinmeyen, geri dönülemez bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="6f0dd-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="6f0dd-114">CLR, artık bir yöntem E_FAIL döndürürse, işlemde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="6f0dd-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="6f0dd-115">Barındırma hiçbir API'leri yapılan sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="6f0dd-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6f0dd-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6f0dd-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6f0dd-117">CLR süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="6f0dd-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f0dd-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6f0dd-118">Remarks</span></span>  
 <span data-ttu-id="6f0dd-119">Genellikle çağırmak gerekli değildir `Start` yöntemi, çünkü CLR yönetilen kodu çalıştırmak için ilk istek üzerine otomatik olarak başlar.</span><span class="sxs-lookup"><span data-stu-id="6f0dd-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f0dd-120">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="6f0dd-120">Requirements</span></span>  
 <span data-ttu-id="6f0dd-121">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f0dd-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f0dd-122">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6f0dd-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f0dd-123">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="6f0dd-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f0dd-124">**.NET framework sürümleri:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6f0dd-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f0dd-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6f0dd-125">See Also</span></span>  
 [<span data-ttu-id="6f0dd-126">Icorruntimehost arabirimi</span><span class="sxs-lookup"><span data-stu-id="6f0dd-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)