---
title: IMetaDataImport::GetMemberProps Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMemberProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b52d3130400310379c69eb0202217d1cd37ff18d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps Metodu
Adını, ikili imza ve göreli sanal adres, meta veri bilgilerini alır <xref:System.Type> belirtilen meta veri simgesi tarafından başvurulan üye.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] ULONG             *pulCodeRVA,   
   [out] DWORD             *pdwImplFlags,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `mb`  
 [in] İlişkili meta verileri almak için üye başvuran belirteci.  
  
 `pClass`  
 [out] Üye sınıfı temsil eder meta veri simgesi için bir işaretçi.  
  
 `szMember`  
 [out] Üyenin adı.  
  
 `cchMember`  
 [in] Geniş karakter cinsinden boyutu `szMember` arabellek.  
  
 `pchMember`  
 [out] Döndürülen adını geniş karakter cinsinden boyutu.  
  
 `pdwAttr`  
 [out] Üyeye uygulanan tüm bayrak değeri.  
  
 `ppvSigBlob`  
 [out] Üyenin ikili meta verileri imza için bir işaretçi.  
  
 `pcbSigBlob`  
 [out] Bayt cinsinden boyutu `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Göreli sanal adres üyesi için bir işaretçi.  
  
 `pdwImplFlags`  
 [out] Üye ile ilişkili tüm yöntemi uygulama bayrakları.  
  
 `pdwCPlusTypeFlag`  
 [out] İşaretler bir bayrak bir <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Bu üye tarafından döndürülen bir sabit dize değeri.  
  
 `pcchValue`  
 [out] Karakter cinsinden boyutu `ppValue`, ya da sıfır `ppValue` bir dize tutmaz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** Cor.h  
  
 **Kitaplığı:** bir kaynak olarak MsCorEE.dll dahil  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Imetadataımport arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Imetadataımport2 arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
