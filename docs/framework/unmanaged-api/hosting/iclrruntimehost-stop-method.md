---
title: "ICLRRuntimeHost::Stop Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.Stop
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3798c4fc451b78257373c0ac47a5e7e7c27dd048
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrruntimehoststop-method"></a>ICLRRuntimeHost::Stop Yöntemi
Kod yürütmeyi ortak dil çalışma zamanı tarafından (CLR) durdurur.  
  
> [!IMPORTANT]
>  Bu yöntem değil ana bilgisayar kaynakları serbest bırakmak, uygulama etki alanları kaldırma veya iş parçacığı yok. Bu kaynakları serbest bırakmak için işlemi sonlandırmamız gerekiyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|`Stop`başarıyla döndürüldü.|  
|HOST_E_CLRNOTAVAILABLE|CLR süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.|  
|HOST_E_TIMEOUT|Arama zaman aşımına uğradı.|  
|HOST_E_NOT_OWNER|Arayan kilidi kendisine ait değil.|  
|HOST_E_ABANDONED|Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.|  
|E_FAIL|Bilinmeyen yıkıcı bir hata oluştu. Bir yöntem E_FAIL döndürürse, CLR artık işlemi içinde kullanılamaz. Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Iclrruntimehost arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
