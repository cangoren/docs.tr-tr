---
title: "Temel İletişimler: Web Barındırma Desteği"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 707b97c49d6a6f5262719e91f8cb38fe7da53601
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="core-communications-webhost-support"></a>Temel İletişimler: Web Barındırma Desteği
Bu konuda, Web barındırma desteği tarafından oluşturulan tüm özel durumlar listelenir.  
  
## <a name="exception-list"></a>Özel durum listesi  
  
|Kaynak kodu|Kaynak dizesi|  
|-------------------|---------------------|  
|Hosting_CompatibilityServiceNotHosted|Bu hizmet, ASP.NET uyumluluğu gerektirir. IIS de barındırılan gerekir. Her iki ana bilgisayar hizmeti IIS ASP.NET uyumluluğu ile Web.config dosyasında açık veya başka bir değer AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode özelliğini ayarlayın.|  
|Hosting_ListenerNotFoundForActivationInRecycling|Kanal belirtilen adresinde etkin şekilde dinler. Uygulama geri dönüştürme, hizmeti kapalı.|  
|Hosting_NonHTTPInCompatibilityMode|ASP.NET uyumluluğu altında desteklenen yalnızca HTTP ve HTTPS protokollerdir. Belirtilen uç nokta kaldırın veya ASP.NET uyumluluğu uygulama için devre dışı bırakın.|  
|Hosting_ProcessNotExecutingUnderHostedContext|Belirtilen barındırma processcannot geçerli barındırma ortamında çağrılan. Bu API, çağıran uygulama Internet Information Services veya Windows İşlem Etkinleştirme hizmeti barındırılması gerekir.|  
|Hosting_ServiceCompatibilityRequire|ASP.NET uyumluluğu gerektirdiğinden hizmeti devre dışı bırakılamaz. ASP.NET uyumluluğu bu uygulama için etkin değil. ASP.NET uyumluluğu Web.config dosyasında etkinleştirmek ya da AspNetCompatibilityRequirementsAttribute.AspNetCompatibility ayarlayın.|
