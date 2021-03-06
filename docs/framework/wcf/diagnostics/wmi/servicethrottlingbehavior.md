---
title: ServiceThrottlingBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 59f85a148d6707876a4df512d5cfbd07ca0e54b7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="servicethrottlingbehavior"></a>ServiceThrottlingBehavior
ServiceThrottlingBehavior  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a>Yöntemler  
 ServiceThrottlingBehavior'dan sınıfı herhangi bir yöntem tanımlamıyor.  
  
## <a name="properties"></a>Özellikler  
 ServiceThrottlingBehavior'dan sınıfı aşağıdaki özelliklere sahiptir:  
  
### <a name="maxconcurrentcalls"></a>maxConcurrentCalls  
 Veri türü: SINT32  
  
 Erişim türüne: salt okunur  
  
 ServiceHost içindeki tüm dağıtıcı nesnelerinde etkin olarak işlenen ileti sayısı.  
  
### <a name="maxconcurrentinstances"></a>MaxConcurrentInstances  
 Veri türü: SINT32  
  
 Erişim türüne: salt okunur  
  
 Bir kerede yürütebilir hizmet nesneleri maksimum sayısı.  
  
### <a name="maxconcurrentsessions"></a>MaxConcurrentSessions  
 Veri türü: SINT32  
  
 Erişim türüne: salt okunur  
  
 Bir ana bilgisayar aynı anda kabul edebilir oturumları maksimum sayısı.  
  
## <a name="requirements"></a>Gereksinimler  
  
|MOF|Bildirilen Servicemodel.mof.|  
|---------|-----------------------------------|  
|Ad Alanı|İçinde tanımlanan root\ServiceModel|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
