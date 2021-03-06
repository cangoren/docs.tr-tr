---
title: "ICorDebugManagedCallback::DebuggerError Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.DebuggerError
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c4eb16762d2a0db01c3cc921712a89995e0c87c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>ICorDebugManagedCallback::DebuggerError Yöntemi
Ortak dil çalışma zamanı (CLR) bir olay işlemeye çalışırken bir hata oluştu hata ayıklayıcı bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pProcess`  
 [in] Olayın meydana geldiği işlemi temsil eden bir "ICorDebugProcess" nesnesi için bir işaretçi.  
  
 `errorHR`  
 [in] Olay işleyiciden döndürülen HRESULT değeri.  
  
 `errorCode`  
 [in] CLR hata belirten bir tamsayı.  
  
## <a name="remarks"></a>Açıklamalar  
 İşlem hatası doğasına bağlı olarak geçiş moduna yerleştirilebilir.  
  
 `DebugError` Geri çağırma hata ayıklayıcıları hata iletisinin kullanıcıya kullanılabilmesini böylece hata ayıklama Hizmetleri bir hata nedeniyle devre dışı bırakılmış olduğunu gösterir. [Icordebugprocess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) çağrısı ancak dahil olmak üzere tüm diğer yöntemleri, güvenli olacak [Icordebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), çağrılmamalı. Hata ayıklayıcı işlemleri sona erdirmek için işletim sistemi özellikleri kullanmanız gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Icordebugmanagedcallback arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
