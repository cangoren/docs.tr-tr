---
title: 222 - OperationFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d56766dd32acf1ef71f7c06a5c3c94cc7510070
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="222---operationfailed"></a>222 - OperationFailed
## <a name="properties"></a>Özellikler  
  
|||  
|-|-|  
|Kimlik|222|  
|Anahtar Sözcükler|Sorun giderme, ServiceModel EndToEndMonitoring, ögesi,|  
|Düzey|Uyarı|  
|Kanal|Microsoft Windows uygulama sunucusu-uygulamalar/analitik|  
  
## <a name="description"></a>Açıklama  
 Bu olay yayılan, hizmet modelinin varsayılan `OperationInvoker` kendi yönteminin çağrılması sırasında bir özel durumla karşılaştı. Not öğesinden türetilen bu özel durumlar `FaultException` değil yayınlaması için bu olay neden.  
  
## <a name="message"></a>İleti  
 '%1' yöntemi, OperationInvoker tarafından çağrıldığında işlenmeyen bir özel durum oluşturdu. Yöntem çağrısı süre, '%2' ms idi.  
  
## <a name="details"></a>Ayrıntılar  
  
|Veri öğesi adı|Veri öğesi türü|Açıklama|  
|--------------------|--------------------|-----------------|  
|Yöntem adı|`xs:string`|Tarafından çağrılan yöntemin CLR adını `OperationInvoker`.|  
|Süre|`xs:long`|Geçen milisaniye cinsinden süre `OperationInvoker` yöntemini çağırmak için.|  
|HostReference|`xs:string`|Bu alan, Web barındırılan hizmetler için Web hiyerarşi hizmetinde benzersiz olarak tanımlar. Biçimi olarak tanımlanan ' Web sitesi adı uygulamanın sanal yolu &#124; Hizmet sanal yolu &#124; ServiceName'. Örnek: ' varsayılan Web sitesi/CalculatorApplication, #124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.|
