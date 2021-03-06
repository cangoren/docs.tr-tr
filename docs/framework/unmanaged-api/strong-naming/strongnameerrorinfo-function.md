---
title: "StrongNameErrorInfo İşlevi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: StrongNameErrorInfo
helpviewer_keywords: StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0fbe77f16ed022458a036b6627b82f80d194276c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="strongnameerrorinfo-function"></a>StrongNameErrorInfo İşlevi
Güçlü ad işlevleri biri tarafından gerçekleştirilen son hata kodunu alır.  
  
 Bu işlev kullanım dışı bırakıldı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Güçlü ad işlevleri biri tarafından ayarlanmış son COM hata kodudur.  
  
## <a name="remarks"></a>Açıklamalar  
 Güçlü ad yöntemlerinin en basit bir dönüş `true` veya `false` başarılı bir şekilde tamamlandığında bir göstergesi. Kullanım `StrongNameErrorInfo` güçlü ad işlevleri tarafından üretilen son hata belirten bir HRESULT alınacak işlev.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** StrongName.h  
  
 **Kitaplığı:** bir kaynak olarak MsCorEE.dll dahil  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güçlü adlandırma genel statik işlevleri](http://msdn.microsoft.com/en-us/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)
