---
title: "IHostMemoryManager::VirtualFree Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.VirtualFree
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 468228101403c7ce3c123401e906e3ccbe301e28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanagervirtualfree-method"></a>IHostMemoryManager::VirtualFree Yöntemi
Karşılık gelen Win32 işlevi için mantıksal bir kapsayıcı görevi görür. Win32 uygulaması `VirtualFree` serbest, decommits, veya serbest bırakır ve çağırma işleminin sanal adres alanı içinde sayfalar bölgesi decommits.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lpAddress`  
 [in] Sanal bellek sayfalarının boşaltılması için taban adresi için bir işaretçi.  
  
 `dwSize`  
 [in] Boşaltılacak alanının bayt cinsinden boyutu.  
  
 `dwFreeType`  
 [in] İşlemi serbest bırakma türü.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|`VirtualFree`başarıyla döndürüldü.|  
|HOST_E_CLRNOTAVAILABLE|Ortak dil çalışma zamanı (CLR) süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.|  
|HOST_E_TIMEOUT|Arama zaman aşımına uğradı.|  
|HOST_E_NOT_OWNER|Arayan kilidi kendisine ait değil.|  
|HOST_E_ABANDONED|Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.|  
|E_FAIL|Bilinmeyen yıkıcı bir hata oluştu. Bir yöntem E_FAIL döndüğünde, CLR artık işlemi içinde kullanılamaz. Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.|  
|HOST_E_INVALIDOPERATION|Ana bilgisayar üzerinden ayrılmamış belleği boşaltmak için girişimde bulunuldu.|  
  
## <a name="remarks"></a>Açıklamalar  
 `VirtualFree`ilişkili sanal bellek sayfalarını boşaltır `lpAddress` önceki bir çağrı aracılığıyla parametresini [Ihostmemorymanager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) işlevi. Ana bilgisayar üzerinden ayrılmamış belleği serbest girişimlerini HOST_E_INVALIDOPERATION döndürmelidir.  
  
 Semantiğini olanlar Win32 uygulaması aynı `VirtualFree`. Daha fazla bilgi için Windows platformu belgelerine bakın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ihostmemorymanager arabirimi](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [Ihostmalloc arabirimi](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
