---
title: "ICorDebugModule3::CreateReaderForInMemorySymbols Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule3.CreateReaderForInMemorySymbols
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fbab155e783d3b5e40da466fef56633317c67042
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="a9f50-102">ICorDebugModule3::CreateReaderForInMemorySymbols Yöntemi</span><span class="sxs-lookup"><span data-stu-id="a9f50-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="a9f50-103">Dinamik bir modül için bir hata ayıklama simgesi okuyucu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="a9f50-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9f50-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a9f50-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9f50-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a9f50-105">Parameters</span></span>  
 <span data-ttu-id="a9f50-106">nRIID</span><span class="sxs-lookup"><span data-stu-id="a9f50-106">riid</span></span>  
 <span data-ttu-id="a9f50-107">[in] Döndürülecek COM arabirimi IID.</span><span class="sxs-lookup"><span data-stu-id="a9f50-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="a9f50-108">Genel olarak, bir [Isymunmanagedreader arabirimi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a9f50-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="a9f50-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="a9f50-109">ppObj</span></span>  
 <span data-ttu-id="a9f50-110">[out] Döndürülen arayüzü için bir işaretçi işaretçi.</span><span class="sxs-lookup"><span data-stu-id="a9f50-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9f50-111">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="a9f50-111">Return Value</span></span>  
 <span data-ttu-id="a9f50-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9f50-112">S_OK</span></span>  
 <span data-ttu-id="a9f50-113">Okuyucu başarıyla oluşturuldu.</span><span class="sxs-lookup"><span data-stu-id="a9f50-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="a9f50-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="a9f50-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="a9f50-115">Modül bir bellek içi ya da dinamik modül değil.</span><span class="sxs-lookup"><span data-stu-id="a9f50-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="a9f50-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a9f50-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="a9f50-117">Simge uygulama tarafından sağlanan yok veya henüz kullanılabilir değil.</span><span class="sxs-lookup"><span data-stu-id="a9f50-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="a9f50-118">E_FAIL (veya diğer E_ dönüş kodları)</span><span class="sxs-lookup"><span data-stu-id="a9f50-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="a9f50-119">Okuyucu oluşturulamadı.</span><span class="sxs-lookup"><span data-stu-id="a9f50-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9f50-120">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a9f50-120">Remarks</span></span>  
 <span data-ttu-id="a9f50-121">Simgeler ilk kullanılabilir olduktan sonra bu yöntem de bellek içi (dinamik olmayan) modülleri için bir simge Okuyucu nesnesi oluşturmak için kullanılan, ancak yalnızca olabilir (belirttiği [UpdateModuleSymbols yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) geri çağırma).</span><span class="sxs-lookup"><span data-stu-id="a9f50-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="a9f50-122">Bu yöntem her çağrıldığında yeni bir okuyucu örneği döndürür (gibi [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span><span class="sxs-lookup"><span data-stu-id="a9f50-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span></span> <span data-ttu-id="a9f50-123">Bu nedenle, hata ayıklayıcı sonucu önbelleğe alınması ve temel alınan veri yalnızca değişmiş olabilir zaman yeni bir örneğini iste (diğer bir deyişle, bir [LoadClass yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) geri alındığında).</span><span class="sxs-lookup"><span data-stu-id="a9f50-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="a9f50-124">İlk tür yüklenen kadar dinamik modüllerdeki semboller kullanılabilir gerekmez (belirtildiği gibi [LoadClass yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) geri çağırma).</span><span class="sxs-lookup"><span data-stu-id="a9f50-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9f50-125">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a9f50-125">Requirements</span></span>  
 <span data-ttu-id="a9f50-126">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9f50-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9f50-127">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9f50-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9f50-128">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9f50-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9f50-129">**.NET framework sürümleri:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="a9f50-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f50-130">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a9f50-130">See Also</span></span>  
 [<span data-ttu-id="a9f50-131">Icordebugremotetarget arabirimi</span><span class="sxs-lookup"><span data-stu-id="a9f50-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="a9f50-132">Icordebug arabirimi</span><span class="sxs-lookup"><span data-stu-id="a9f50-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="a9f50-133">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="a9f50-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)