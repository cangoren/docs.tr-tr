---
title: "FunctionIDMapper İşlevi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionIDMapper
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionIDMapper
helpviewer_keywords: FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 629bcd5085169fcb136884c53434c29d385642cd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="functionidmapper-function"></a>FunctionIDMapper İşlevi
Profil oluşturucu işlevi verilen tanıtıcısı kullanılmak üzere bir alternatif kimlik eşlenmesine bildirir [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), ve [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) bu işlev için geri çağırmaları. `FunctionIDMapper`Ayrıca, bu işlevin geri aramalar almak istediği olup olmadığını belirtmek profil oluşturucu sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `funcId`  
 [in] Eşleştirilmesi için işlevi tanımlayıcısı.  
  
 `pbHookFunction`  
 [out] Profil Oluşturucu ayarlar için bir değer için bir işaretçi `true` almak istiyorsa, `FunctionEnter2`, `FunctionLeave2`, ve `FunctionTailcall2` geri aramalar; Aksi takdirde, bu değeri ayarlar `false`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Profil Oluşturucu yürütme altyapısı bir alternatif işlevi tanımlayıcı olarak kullanan bir değer döndürür. Dönüş değeri null olamaz sürece `false` döndürülür `pbHookFunction`. Aksi takdirde null dönüş değeri büyük olasılıkla işlemi durdurma dahil, öngörülemeyen sonuçlara oluşturur.  
  
## <a name="remarks"></a>Açıklamalar  
 `FunctionIDMapper` Bir geri çağırma işlevidir. Profil Oluşturucu için daha yararlı olan başka bir tanımlayıcı işlevi Kimliğine yeniden eşlemek için Profil Oluşturucu tarafından uygulanır. `FunctionIDMapper` Belirli bir işlev için kullanılacak alternatif Kimliğini döndürür. Profil Oluşturucu'nın istek sonra geliştirir yanı sıra geleneksel işlevi kimliği bu alternatif kimlik geri Profil Oluşturucusu'nda geçirerek yürütme altyapısı `clientData` parametresinin `FunctionEnter2`, `FunctionLeave2`, ve `FunctionTailcall2` tanımlamak için kancaları kendisi için kanca çağrılan işlev.  
  
 Kullanabileceğiniz [Icorprofilerınfo::setfunctionıdmapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) uygulanması belirtmek için yöntemi `FunctionIDMapper` işlevi. Çağırabilirsiniz `ICorProfilerInfo::SetFunctionIDMapper` yöntemi yalnızca bir kez ve biz öneririz, böylece bunu [Icorprofilercallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) geri çağırma.  
  
 Varsayılan olarak, bir profil oluşturucu COR_PRF_MONITOR_ENTERLEAVE bayrağını kullanarak ayarlayan olduğunu görünür duruma varsayılır [Icorprofilerınfo::seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), ve aracılığıyla kancaları ayarlar [Icorprofilerınfo::setenterleavefunctionhooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) veya [Icorprofilerınfo2::setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), alması gereken `FunctionEnter2`, `FunctionLeave2`, ve `FunctionTailcall2` her işlev için geri çağırmaları. Ancak, profil oluşturucular uygulayabilir `FunctionIDMapper` ayarlayarak seçerek bu geri aramalar belirli almayı önlemek için işlevleri `pbHookFunction` için `false`.  
  
 Profil oluşturucular burada profili uygulamasının birden çok iş parçacığı aynı yöntemi ya da işlevin aynı anda bulunduğunuz örneklerini dayanıklı olması gerekir. Böyle durumlarda, birden çok profil oluşturucu alabilirsiniz `FunctionIDMapper` geri aramalar için aynı `FunctionID`. Profil Oluşturucu ile aynı birden çok kez çağrıldığında, bu geri aramasından aynı değerlere döndürmek emin olmalısınız `FunctionID`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorProf.idl  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Setfunctionıdmapper yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [Functionıdmapper2 işlevi](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 [FunctionEnter2 işlevi](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionLeave2 işlevi](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [FunctionTailcall2 işlevi](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [Profil oluşturma genel statik işlevleri](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
