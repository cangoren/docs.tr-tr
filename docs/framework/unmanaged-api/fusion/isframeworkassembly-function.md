---
title: "IsFrameworkAssembly İşlevi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IsFrameworkAssembly
api_location: fusion.dll
api_type: COM
f1_keywords: IsFrameworkAssembly
helpviewer_keywords: IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 216a7221550cb6345b29b5ed9e45b13ce40eadf4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="isframeworkassembly-function"></a>IsFrameworkAssembly İşlevi
Belirtilen derleme yönetilen olup olmadığını belirten bir değer alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pwzAssemblyReference`  
 [in] Denetlenecek derlemenin adı.  
  
 `pbIsFrameworkAssembly`  
 [out] Derleme yönetilen olup olmadığını gösteren bir Boole değeri.  
  
 `pwzFrameworkAssemblyIdentity`  
 [in] Derleme benzersiz kimliğini içeren bir uncanonicalized dize.  
  
 `pccSize`  
 [in] Boyutunu `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Açıklamalar  
 `pwzAssemblyReference` Bir işaretçi bir derleme adını içeren bir karakter dizesi parametresidir.  
  
 Bu derleme parçasıysa .NET Framework'ün `pbIsFrameworkAssembly` parametre bir Boole değeri içerecek `true`.  
  
 Adlandırılmış derlemesi .NET Framework'ün bir parçası değilse veya `pwzAssemblyReference` parametre bir derleme adı değil `pbIsFrameworkAssembly` bir Boole değeri içerecektir `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Fusion genel statik işlevleri](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
