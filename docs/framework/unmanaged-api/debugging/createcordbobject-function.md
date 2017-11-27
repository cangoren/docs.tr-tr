---
title: "CreateCordbObject İşlevi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateCoredbObject
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 06e08148e5526d65d82eca52ffe8db66a4e7df6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="createcordbobject-function"></a><span data-ttu-id="c695a-102">CreateCordbObject İşlevi</span><span class="sxs-lookup"><span data-stu-id="c695a-102">CreateCordbObject Function</span></span>
<span data-ttu-id="c695a-103">Hata ayıklayıcı arabirimi oluşturur ([Icordebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) uzak bir işlem üzerinde yönetilen hata ayıklama oturumu oluşturmak için işlevsellik sağlar.</span><span class="sxs-lookup"><span data-stu-id="c695a-103">Creates a debugger interface ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c695a-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c695a-104">Syntax</span></span>  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c695a-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="c695a-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="c695a-106">[in] Hedef işlemin hata ayıklayıcı sürümü.</span><span class="sxs-lookup"><span data-stu-id="c695a-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="c695a-107">Bu parametre, uzaktan hata ayıklama için CorDebugVersion_2_0 olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="c695a-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="c695a-108">[out] İşaretçi için cast bir nesne için bir işaretçi bir [Icordebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) arabirim ve döndürülür.</span><span class="sxs-lookup"><span data-stu-id="c695a-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c695a-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="c695a-109">Return Value</span></span>  
 <span data-ttu-id="c695a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c695a-110">S_OK</span></span>  
 <span data-ttu-id="c695a-111">İşlem CLRs sayısında başarıyla belirlendi ve karşılık gelen tanıtıcısı ve yol dizileri düzgün doldurulmuş.</span><span class="sxs-lookup"><span data-stu-id="c695a-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="c695a-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c695a-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="c695a-113">`ppCordb`null, veya `iDebuggerVersion` CorDebugVersion_2_0 değil.</span><span class="sxs-lookup"><span data-stu-id="c695a-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="c695a-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c695a-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="c695a-115">İçin yeterli bellek ayrılamıyor.`ppCordb`</span><span class="sxs-lookup"><span data-stu-id="c695a-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="c695a-116">E_FAIL (veya diğer E_ dönüş kodları)</span><span class="sxs-lookup"><span data-stu-id="c695a-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="c695a-117">Diğer hataları.</span><span class="sxs-lookup"><span data-stu-id="c695a-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c695a-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c695a-118">Remarks</span></span>  
 <span data-ttu-id="c695a-119">[Icordebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) döndürülür arabirimi `ppCordb` tüm hata ayıklama Hizmetleri tarafından yönetilen en üst düzey hata ayıklama arabirimidir.</span><span class="sxs-lookup"><span data-stu-id="c695a-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c695a-120">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="c695a-120">Requirements</span></span>  
 <span data-ttu-id="c695a-121">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c695a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c695a-122">**Başlık:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="c695a-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="c695a-123">**Kitaplığı:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="c695a-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="c695a-124">**.NET framework sürümleri:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="c695a-124">**.NET Framework Versions:** 3.5 SP1</span></span>