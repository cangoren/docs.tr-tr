---
title: 1009 - ActivityScheduled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdaa8ca4efeffb3895e0056303721b13cdc1ae27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="1009---activityscheduled"></a>1009 - ActivityScheduled
## <a name="properties"></a>Özellikler  
  
|||  
|-|-|  
|Kimlik|1009|  
|Anahtar Sözcükler|WFRuntime|  
|Düzey|Bilgiler|  
|Kanal|Microsoft Windows uygulaması sunucu-uygulamalar/hata ayıklama|  
  
## <a name="description"></a>Açıklama  
 Bir etkinlik çalıştırılmak üzere zamanlanmış gösterir.  
  
## <a name="message"></a>İleti  
 Üst etkinlik '%1', DisplayName: '%2', örnek kimliği: '%3' zamanlanmış alt etkinliği '%4', DisplayName: '%5', örnek kimliği: '%6'.  
  
## <a name="details"></a>Ayrıntılar  
  
|Veri öğesi adı|Veri öğesi türü|Açıklama|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs: String|Üst etkinlik türü adı.|  
|Ana görüntü adı|xs: String|Üst etkinliğin görünen adı.|  
|ParentInstanceId|xs: String|Üst etkinlik örnek kimliği.|  
|ChildActivity|xs: String|Zamanlanmış alt etkinlik türü adı.|  
|ChildDisplayName|xs: String|Zamanlanmış alt etkinliğin görünen adı.|  
|ChildInstanceId|xs: String|Zamanlanmış alt etkinlik örnek kimliği.|  
|AppDomain|xs: String|AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.|
