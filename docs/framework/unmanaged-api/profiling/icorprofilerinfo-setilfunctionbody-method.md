---
title: "ICorProfilerInfo::SetILFunctionBody Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6d97827555ecefb775323fdf9dbd6577f941f1e9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a>ICorProfilerInfo::SetILFunctionBody Yöntemi
Belirtilen modül belirtilen işlev gövdesi yerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `moduleId`  
 [in] İşlev bulunduğu modül kimliği.  
  
 `methodid`  
 [in] İşlev gövdesi değiştirmek üzere belirteci.  
  
 `pbNewILMethodHeader`  
 [in] İşlev için yeni üstbilgi.  
  
## <a name="remarks"></a>Açıklamalar  
 `SetILFunctionBody` Yöntemi, böylece işaret yeni işlev gövdesi ve iç veri yapılarını gerektiği gibi ayarlar meta verilerde işlevinin göreli sanal adres değiştirir.  
  
 `SetILFunctionBody` Yöntemi, hiçbir zaman tam zamanında (JIT) derleyicisi tarafından derlenen işlevler üzerinde çağrılabilir.  
  
 Kullanım [Icorprofilerınfo::getılfunctionbodyallocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) arabellek uyumlu olduğundan emin olmak yeni yöntemi için alan ayırmak için yöntem.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Icorprofilerınfo arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
