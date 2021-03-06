---
title: "ICorProfilerInfo7::GetInMemorySymbolsLength yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type: COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 34da00bdc33a836e5f459e6e4314f252e1e39e9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>ICorProfilerInfo7::GetInMemorySymbolsLength yöntemi
[.NET Framework 4.6.1 ve sonraki sürümlerinde desteklenen]  
  
 Bellek içi simgesi akış uzunluğunu döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `moduleId`  
 [in] Bellek içi akış içeren modül tanıtıcısı.  
  
 pCountSymbolBytes  
 [out] Bir işaretçi bir `DWORD` yöntem döndürüldüğünde, akış bayt cinsinden uzunluğu değeri içerir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntem `S_OK` sıfır (0) olsa bile bellek akış uzunluğu, belirlenebilir durumunda.  
  
 Yöntem `CORPROF_E_MODULE_IS_DYNAMIC` yöntemi kullanılarak oluşturulduysa <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="remarks"></a>Açıklamalar  
 Modül bellek içi simgeleri varsa, akış uzunluğu yerleştirilir `pCountSymbolBytes`. Bellek içi simgeleri modülü yoksa `*pCountSymbolBytes = 0`.  
  
> [!NOTE]
>  Geçerli uygulama Reflection.Emit desteklemez. Modül Reflection.Emit kullanılarak oluşturulup oluşturulmadığını, yöntem `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICorProfilerInfo7 arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
