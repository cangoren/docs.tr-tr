---
title: COR_PRF_CODEGEN_FLAGS Sabit Listesi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_CODEGEN_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_CODEGEN_FLAGS
helpviewer_keywords: COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c2c97510077fefd730827ac00326d267fd1c62ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="corprfcodegenflags-enumeration"></a>COR_PRF_CODEGEN_FLAGS Sabit Listesi
İle ayarlayabilirsiniz kod oluşturma bayrakları tanımlar [Icorprofilerfunctioncontrol::setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) yöntemi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|Hiçbir işlevler bu işlevin gövdesi içermesinden olacaktır. Ancak, işlevi kendi arayanlar içermesinden olabilir.|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|Tüm iyileştirmeler bu işlevin gövdesi için devre dışı bırakılacak. Ancak, işlevi hala kendi arayanlar içermesinden olabilir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COR_PRF_CODEGEN_FLAGS` Numaralandırması tarafından kullanılan [Icorprofilerfunctioncontrol::setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) JIT yeniden derlenmesi işlevi için kod oluşturmanın denetlemek profil oluşturucu etkinleştirmek için yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil oluşturma numaralandırmaları](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
