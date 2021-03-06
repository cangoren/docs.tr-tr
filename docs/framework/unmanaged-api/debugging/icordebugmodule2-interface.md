---
title: Icordebugmodule2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2
helpviewer_keywords: ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 97259783d34babe3f0f229f5d62b3e945c0ac624
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2-interface1"></a>Icordebugmodule2 Interface1
Icordebugmodule arabirimi için mantıksal bir uzantısı olarak görev yapar.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[ApplyChanges yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|Meta veri değişiklikleri ve Microsoft Ara dili (MSIL) kod değişiklikleri çalışan işlemi için geçerlidir.|  
|[Getjıtcompilerflags yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|Tam zamanında (JIT) derleme için bu denetim bayrakları alır `ICorDebugModule2`.|  
|[ResolveAssembly yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|Belirtilen meta veri simgesi tarafından başvurulan derleme çözümler.|  
|[Setjıtcompilerflags yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|JIT derleme için bu denetim bayrakları ayarlar `ICorDebugModule2`.|  
|[SetJMCStatus yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|Tüm sınıfların tüm yöntemleri yalnızca My kod (JMC) durumunu bu ayarlar `ICorDebugModule2` hariç belirtilen değerle `pTokens` ters değerine ayarlar dizi.|  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu arabirim, makineler arası veya çapraz işlem uzaktan çağrılan desteklemez.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama arabirimleri](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
