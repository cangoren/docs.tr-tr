---
title: "ICLRStrongName::StrongNameGetPublicKey Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameGetPublicKey
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4b7ace87a5eff5235d85507bda649e55ea18fd93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="44640-102">ICLRStrongName::StrongNameGetPublicKey Yöntemi</span><span class="sxs-lookup"><span data-stu-id="44640-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="44640-103">Ortak anahtarı bir genel/özel anahtar çifti alır.</span><span class="sxs-lookup"><span data-stu-id="44640-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="44640-104">Anahtar çifti, şifreleme hizmeti sağlayıcısı (CSP) içinde bir anahtar kapsayıcı adı veya ham bayt koleksiyonu olarak sağlanabilir.</span><span class="sxs-lookup"><span data-stu-id="44640-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44640-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="44640-105">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44640-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="44640-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="44640-107">[in] Ortak/özel anahtar çiftini içeren anahtar kapsayıcı adı.</span><span class="sxs-lookup"><span data-stu-id="44640-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="44640-108">Varsa `pbKeyBlob` null, `szKeyContainer` CSP Geçerli kapsayıcıda belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="44640-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="44640-109">Bu durumda, [Iclrstrongname::strongnamegetpublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) yöntemi kapsayıcısında depolanan anahtar çifti gelen ortak anahtarı ayıklar.</span><span class="sxs-lookup"><span data-stu-id="44640-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="44640-110">Varsa `pbKeyBlob` anahtar çifti varsayılır anahtar ikili büyük nesne (BLOB) dahil edilmek üzere null değil.</span><span class="sxs-lookup"><span data-stu-id="44640-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="44640-111">1024 bit Rivest-Shamir-Adleman (RSA) anahtarları İmzalama anahtarları olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="44640-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="44640-112">Başka tür anahtarları şu anda desteklenir.</span><span class="sxs-lookup"><span data-stu-id="44640-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="44640-113">[in] Ortak/özel anahtar çifti için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="44640-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="44640-114">Bu çiftidir Win32 tarafından oluşturulan biçiminde `CryptExportKey` işlevi.</span><span class="sxs-lookup"><span data-stu-id="44640-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="44640-115">Varsa `pbKeyBlob` null, belirtilen anahtar kapsayıcısı olan `szKeyContainer` anahtar çiftini içeren varsayılır.</span><span class="sxs-lookup"><span data-stu-id="44640-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="44640-116">[in] Bayt olarak boyutu, `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="44640-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="44640-117">[out] Döndürülen ortak anahtarı BLOB.</span><span class="sxs-lookup"><span data-stu-id="44640-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="44640-118">`ppbPublicKeyBlob` Parametresi ortak dil çalışma zamanı tarafından ayrılmış ve yapana.</span><span class="sxs-lookup"><span data-stu-id="44640-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="44640-119">Kullanarak, çağıran belleği serbest gerekir [Iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="44640-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="44640-120">[out] Döndürülen ortak anahtarı BLOB boyutu.</span><span class="sxs-lookup"><span data-stu-id="44640-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44640-121">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="44640-121">Return Value</span></span>  
 <span data-ttu-id="44640-122">`S_OK`Yöntem başarıyla tamamlandı Aksi takdirde hata belirten bir HRESULT değeri (bkz [ortak HRESULT değerleri](http://go.microsoft.com/fwlink/?LinkId=213878) bir listesi için).</span><span class="sxs-lookup"><span data-stu-id="44640-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44640-123">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="44640-123">Remarks</span></span>  
 <span data-ttu-id="44640-124">Ortak anahtar içeren bir [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) yapısı.</span><span class="sxs-lookup"><span data-stu-id="44640-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44640-125">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="44640-125">Requirements</span></span>  
 <span data-ttu-id="44640-126">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44640-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44640-127">**Başlık:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="44640-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="44640-128">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="44640-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44640-129">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44640-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44640-130">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="44640-130">See Also</span></span>  
 [<span data-ttu-id="44640-131">StrongNameTokenFromPublicKey yöntemi</span><span class="sxs-lookup"><span data-stu-id="44640-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="44640-132">PublicKeyBlob yapısı</span><span class="sxs-lookup"><span data-stu-id="44640-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="44640-133">Iclrstrongname arabirimi</span><span class="sxs-lookup"><span data-stu-id="44640-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)