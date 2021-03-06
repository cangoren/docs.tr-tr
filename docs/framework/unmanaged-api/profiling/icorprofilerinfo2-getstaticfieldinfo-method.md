---
title: ICorProfilerInfo2::GetStaticFieldInfo Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStaticFieldInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7cf16a0fae7f3e2afd095534b2e7f7957d44e3e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>ICorProfilerInfo2::GetStaticFieldInfo Metodu
Belirtilen alan geçerlidir statik türünü belirten bir değer alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `classId`  
 [in] Statik alan tanımlandığı sınıfı kimliği.  
  
 `fieldToken`  
 [in] Statik alan için meta veri simgesi.  
  
 `pFieldInfo`  
 [out] Değerini gösteren bir işaretçi [cor_prf_statıc_type](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) numaralandırma belirten belirtilen alan statik olup ve bu nedenle, statik türü, alan için geçerli olup olmadığını.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bilgiler, statik alan adresini almak için çağırmak için hangi işlevi belirlemek için kullanılabilir.  
  
 Profil Oluşturucu kodu hala, aslında bir adresi olduğundan emin olmak için statik bir alan için meta verileri kontrol etmeniz gerekir. Statik değişmez değerleri (diğer bir deyişle, sabitler) yalnızca meta verilerde mevcut ve bir adresi yok.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Icorprofilerınfo arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Icorprofilerınfo2 arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
