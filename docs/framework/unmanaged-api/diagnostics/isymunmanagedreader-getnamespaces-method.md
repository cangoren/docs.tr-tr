---
title: ISymUnmanagedReader::GetNamespaces Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetNamespaces
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c4404977fab42fb46292440473cd30f6cb162d6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="9bb72-102">ISymUnmanagedReader::GetNamespaces Metodu</span><span class="sxs-lookup"><span data-stu-id="9bb72-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="9bb72-103">Bu simge deposundaki genel kapsamda tanımlanan ad alanları alır.</span><span class="sxs-lookup"><span data-stu-id="9bb72-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bb72-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="9bb72-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bb72-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="9bb72-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="9bb72-106">[in] Ad alanları dizi büyüklüğü.</span><span class="sxs-lookup"><span data-stu-id="9bb72-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="9bb72-107">[out] Bir işaretçi bir değişkene ad listesi uzunluğunu alır.</span><span class="sxs-lookup"><span data-stu-id="9bb72-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="9bb72-108">[out] Bir işaretçi bir değişkene ad listesini alır.</span><span class="sxs-lookup"><span data-stu-id="9bb72-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9bb72-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="9bb72-109">Return Value</span></span>  
 <span data-ttu-id="9bb72-110">Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="9bb72-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bb72-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="9bb72-111">Requirements</span></span>  
 <span data-ttu-id="9bb72-112">**Başlık:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9bb72-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bb72-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9bb72-113">See Also</span></span>  
 [<span data-ttu-id="9bb72-114">Isymunmanagedreader arabirimi</span><span class="sxs-lookup"><span data-stu-id="9bb72-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)