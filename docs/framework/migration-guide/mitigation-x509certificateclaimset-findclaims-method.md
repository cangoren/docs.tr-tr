---
title: "Azaltma: X509CertificateClaimSet.FindClaims yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7872f1904cfcab860bb25459aabd47e6dcf38ac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a>Azaltma: X509CertificateClaimSet.FindClaims yöntemi
Hedefleyen uygulamalar ile başlayan [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> yöntemi eşleşen deneyecek `claimType` bağımsız değişkeni, SAN alanındaki tüm DNS girişlerini ile.  
  
## <a name="impact"></a>Etki  
 Bu değişiklik, yalnızca .NET Framework başlayarak sürümlerini hedefleyen uygulamaları etkiler [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 .NET Framework'ün önceki sürümlerini hedefleyen uygulamalar için <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> yöntemi çalışır eşleşecek şekilde `claimType` bağımsız değişkeni yalnızca son DNS girişi ile.  
  
## <a name="mitigation"></a>Azaltma  
 Bu değişiklik istenmeyen ise, uygulamalar, hedef başlayarak .NET Framework sürümleri [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] onu dışında şu yapılandırma ayarı ekleyerek seçebilirsiniz [ \<çalışma zamanı >](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) uygulamanın bölümü yapılandırma dosyası:  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
```  
  
 Buna ek olarak, .NET Framework'ün önceki sürümlerini hedefleyen ancak altında çalışan uygulamalar [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ve sonraki sürümler kabul etme Bu davranışı şu yapılandırma ayarı ekleyerek [ \<çalışma zamanı >](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)uygulamanın yapılandırma dosyasının:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yeniden hedefleme değişiklikleri](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
