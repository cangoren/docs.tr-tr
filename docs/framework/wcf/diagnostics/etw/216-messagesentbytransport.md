---
title: 216 - MessageSentByTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1b2bf2841c04dcdc74bf64a0169b95caa6c8a36a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="216---messagesentbytransport"></a>216 - MessageSentByTransport
## <a name="properties"></a>Özellikler  
  
|||  
|-|-|  
|Kimlik|216|  
|Anahtar Sözcükler|Sorun giderme, ServiceModel|  
|Düzey|Bilgiler|  
|Kanal|Microsoft Windows uygulama sunucusu-uygulamalar/analitik|  
  
## <a name="description"></a>Açıklama  
 Bu olay, bir TCP tabanlı taşıma ileti gönderdiğinde oluşur. Aktarım düzeyinde birden çok ileti istemciler ve hizmetler için tek bir işlem arasında değiştirilebilir unutmayın. Bu iyi bir örneği olan güvenlik altyapı davranışı nedeniyle olabilir. Bu nedenle, sayısı **MessageSentByTransport** gösterilen olayları hizmetinizin bağlama ve yapılandırmasına göre değişir.  
  
## <a name="message"></a>İleti  
 Taşıma '%1' için bir ileti gönderdi.  
  
## <a name="details"></a>Ayrıntılar  
  
|Veri öğesi adı|Veri öğesi türü|Açıklama|  
|--------------------|--------------------|-----------------|  
|DestinationAddress|`xs:string`|İstek iletisi gönderildiği adresi.|  
|HostReference|xs: String|Bu alan, Web barındırılan hizmetler için Web hiyerarşi hizmetinde benzersiz olarak tanımlar. Biçimi olarak tanımlanan ' Web sitesi adı uygulamanın sanal yolu &#124; Hizmet sanal yolu &#124; ServiceName'. Örnek: ' varsayılan Web sitesi/CalculatorApplication, #124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.|
