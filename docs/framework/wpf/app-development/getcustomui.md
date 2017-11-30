---
title: GetCustomUI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f3c101ad13df9b99a2d872bac8783baed8b4b9a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="getcustomui"></a><span data-ttu-id="b86d6-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="b86d6-102">GetCustomUI</span></span>
<span data-ttu-id="b86d6-103">Ana bilgisayardan özel ilerleme durumu ve hata iletileri almak için PresentationHost.exe tarafından uygulanırsa çağrılır.</span><span class="sxs-lookup"><span data-stu-id="b86d6-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b86d6-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b86d6-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b86d6-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="b86d6-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="b86d6-106">[out] Ana bilgisayar tarafından sağlanan kullanıcı arabirimi içeren bütünleştirilmiş kodun bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="b86d6-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="b86d6-107">[out] Ana bilgisayar tarafından sağlanan kullanıcı arabirimi, tercihen olduğu sınıfın adını bir [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] ile dosya <xref:System.Windows.Controls.Page> kendi üst seviye öğesidir.</span><span class="sxs-lookup"><span data-stu-id="b86d6-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="b86d6-108">Bu sınıf tarafından belirtilen derleme bulunur `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="b86d6-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="b86d6-109">[out] Ana bilgisayar tarafından sağlanan hata kullanıcı arabirimi içeren bütünleştirilmiş kodun bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="b86d6-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="b86d6-110">[out] Ana bilgisayar tarafından sağlanan hata kullanıcı sınıfının arabirim adı, tercihen ile bir XAML dosyası <xref:System.Windows.Controls.Page> kendi üst seviye öğesidir.</span><span class="sxs-lookup"><span data-stu-id="b86d6-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="b86d6-111">Bu sınıf tarafından belirtilen derleme bulunur `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="b86d6-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b86d6-112">Özellik Değeri/Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="b86d6-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="b86d6-113">HRESULT: yoksayıldı.</span><span class="sxs-lookup"><span data-stu-id="b86d6-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b86d6-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b86d6-114">Remarks</span></span>  
 <span data-ttu-id="b86d6-115">Bir ana bilgisayar uygulaması PresentationHost.exe'nin varsayılan kullanıcı arabirimleri için uygun olmayabilir belirli bir temaya sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="b86d6-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="b86d6-116">Bu durumda, ana bilgisayar uygulamasını uygulayabilirsiniz [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) ilerleme durumu ve hata kullanıcı arabirimleri PresentationHost.exe'ye izin verilecek.</span><span class="sxs-lookup"><span data-stu-id="b86d6-116">If this is the case, the host application can implement [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="b86d6-117">PresentationHost.exe her zaman çağıracaktır [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) varsayılan kullanıcı arabirimlerinden kullanmadan önce.</span><span class="sxs-lookup"><span data-stu-id="b86d6-117">PresentationHost.exe will always call [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="b86d6-118">Bu işlev bir kez PresentationHost'un sırasında çağrılır.</span><span class="sxs-lookup"><span data-stu-id="b86d6-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b86d6-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b86d6-119">See Also</span></span>  
 [<span data-ttu-id="b86d6-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="b86d6-120">IWpfHostSupport</span></span>](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)