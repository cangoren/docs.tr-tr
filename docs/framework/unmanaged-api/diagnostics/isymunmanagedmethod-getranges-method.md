---
title: ISymUnmanagedMethod::GetRanges Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetRanges
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 71d24bc83d6a26c800d0d97e885b322cc2b4ccbd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetranges-method"></a>ISymUnmanagedMethod::GetRanges Metodu
Bir konumda bir belge, bu yöntem içinde konumu kapsayan Microsoft Ara dili (MSIL) aralıklarına karşılık gelir başlangıç ve bitiş uzaklığında çiftleri dizisi döndürür. Dizi dizisi ve [Başlangıç, son, Başlat, son] biçimi vardır. 2 ile bölünmüş dizi uzunluğu, aralığı çiftleri sayısıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `document`  
 [in] Uzaklık istenen belge.  
  
 `line`  
 [in] Aralıklarına karşılık gelen belge satırı.  
  
 `column`  
 [in] Aralıklarına karşılık gelen belge sütun.  
  
 `cRanges`  
 [in] Boyutunu `ranges` dizi.  
  
 `pcRanges`  
 [out] Bir işaretçi bir `ULONG32` aralıkları içermesi gerekir arabellek boyutunu alır.  
  
 `ranges`  
 [out] Aralıkları alır arabellek için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL veya başka bir hata kodu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Isymunmanagedmethod arabirimi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
