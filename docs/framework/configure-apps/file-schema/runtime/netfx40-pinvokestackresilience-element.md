---
title: "&lt;Netfx40_pınvokestackresilience&gt; öğesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3e77e43ed9d7520cbbcf453d067a49de3a86de3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltnetfx40pinvokestackresiliencegt-element"></a><span data-ttu-id="a1bbc-102">&lt;Netfx40_pınvokestackresilience&gt; öğesi</span><span class="sxs-lookup"><span data-stu-id="a1bbc-102">&lt;NetFx40_PInvokeStackResilience&gt; Element</span></span>
<span data-ttu-id="a1bbc-103">Olup çalışma zamanı düzeltmeleri yanlış platform çağırma bildirimler arasında yavaş geçişler, çalışma zamanında otomatik olarak yönetilen ve yönetilmeyen kod belirtir.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="a1bbc-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="a1bbc-104">\<configuration></span></span>  
<span data-ttu-id="a1bbc-105">\<çalışma zamanı ></span><span class="sxs-lookup"><span data-stu-id="a1bbc-105">\<runtime></span></span>  
<span data-ttu-id="a1bbc-106">< Netfx40_pınvokestackresilience ></span><span class="sxs-lookup"><span data-stu-id="a1bbc-106"><NetFx40_PInvokeStackResilience></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1bbc-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a1bbc-107">Syntax</span></span>  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1bbc-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="a1bbc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a1bbc-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1bbc-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="a1bbc-110">Attributes</span></span>  
  
|<span data-ttu-id="a1bbc-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="a1bbc-111">Attribute</span></span>|<span data-ttu-id="a1bbc-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a1bbc-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a1bbc-113">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a1bbc-114">Çalışma zamanı yanlış platform algılayıp algılamadığını belirtir bildirimleri çağırma ve yığın çalışma zamanında 32-bit platformlarda otomatik olarak düzeltir.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a1bbc-115">etkin Öznitelik</span><span class="sxs-lookup"><span data-stu-id="a1bbc-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a1bbc-116">Değer</span><span class="sxs-lookup"><span data-stu-id="a1bbc-116">Value</span></span>|<span data-ttu-id="a1bbc-117">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a1bbc-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="a1bbc-118">Çalışma zamanı sürümünde sunulan mimarisi hazırlama daha hızlı birlikte çalışabilirliği kullanır [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], hangi algılamazsa ve düzeltme yanlış platform çağırma bildirimleri.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-118">The runtime uses the faster interop marshaling architecture introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="a1bbc-119">Bu varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="a1bbc-120">Algılayan ve yanlış platform düzeltme çalışma zamanı kullanır yavaş geçişleri bildirimleri çağırır.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1bbc-121">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="a1bbc-121">Child Elements</span></span>  
 <span data-ttu-id="a1bbc-122">Yok.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1bbc-123">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="a1bbc-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a1bbc-124">Öğe</span><span class="sxs-lookup"><span data-stu-id="a1bbc-124">Element</span></span>|<span data-ttu-id="a1bbc-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a1bbc-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a1bbc-126">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a1bbc-127">Çalışma zamanı başlatma seçenekleri hakkında bilgi içerir.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1bbc-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a1bbc-128">Remarks</span></span>  
 <span data-ttu-id="a1bbc-129">Bu öğe, çalışma zamanı esnekliği yanlış platform karşı çağırmak için bildirimleri daha hızlı birlikte çalışma hazırlama ticari olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>  
  
 <span data-ttu-id="a1bbc-130">İle başlayarak [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], yönetilen koddan yönetilmeyen koda geçişler için önemli performans iyileştirme mimarisi hazırlama kolaylaştırılmış bir birlikte çalışabilirlik sağlar.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="a1bbc-131">.NET Framework'ün önceki sürümlerinde, hazırlama algılanan katman yanlış platform 32-bit platformlarda bildirimleri çağırma ve otomatik olarak yığın sabit.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="a1bbc-132">Yeni hazırlama mimarisi, bu adım ortadan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="a1bbc-133">Sonuç olarak, geçişleri çok hızlı, ancak yanlış bir platform çağırma bildirimi program başarısız olmasına neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>  
  
 <span data-ttu-id="a1bbc-134">Geliştirme sırasında hatalı bildirimleri algılamak kolaylaştırmak için Visual Studio deneyimi hata ayıklama geliştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="a1bbc-135">[PInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) yönetilen hata ayıklama Yardımcısı (MDA) bildirir, yanlış platform çağırma bildirimleri hata ayıklayıcısı ekli, uygulamanızı çalıştırırken.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-135">The [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>  
  
 <span data-ttu-id="a1bbc-136">Burada, uygulamanızın kullandığı derlenir olamaz ve kullanabileceğiniz sahip yanlış platform çağırma, bildirimler, bileşenleri adresi senaryoları için `NetFx40_PInvokeStackResilience` öğesi.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="a1bbc-137">Bu öğe ile uygulama yapılandırma dosyasına ekleyerek `enabled="1"` daha yavaş geçişleri, .NET Framework'ün önceki sürümlerinde davranışını ile uyumluluk moduna çevrilir.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="a1bbc-138">Karşı .NET Framework'ün önceki sürümlerinde derlenmiş derlemeler bu uyumluluk moduna otomatik olarak tutulur ve bu öğe gerekmez.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="a1bbc-139">Yapılandırma Dosyası</span><span class="sxs-lookup"><span data-stu-id="a1bbc-139">Configuration File</span></span>  
 <span data-ttu-id="a1bbc-140">Bu öğe yalnızca uygulama yapılandırma dosyasında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-140">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1bbc-141">Örnek</span><span class="sxs-lookup"><span data-stu-id="a1bbc-141">Example</span></span>  
 <span data-ttu-id="a1bbc-142">Aşağıdaki örnekte gösterildiği yanlış karşı artan esneklik içine kabul etmek için platform çağırma nasıl bildirimler arasında yavaş geçişler, bir uygulama için yönetilen ve yönetilmeyen kod.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1bbc-143">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-143">See Also</span></span>  
 [<span data-ttu-id="a1bbc-144">Çalışma Zamanı Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="a1bbc-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="a1bbc-145">Yapılandırma dosyası şeması</span><span class="sxs-lookup"><span data-stu-id="a1bbc-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a1bbc-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="a1bbc-146">pInvokeStackImbalance</span></span>](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)