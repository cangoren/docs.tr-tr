---
title: WF etkinlikleri Durum makinesi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ed2b5ace499af3c050529e9f0f2cdd3634c247fd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="state-machine-activities-in-wf"></a>WF etkinlikleri Durum makinesi
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]birkaç sistem tarafından sağlanan etkinlikleri ve etkinlik tasarımcıları durumu makine iş akışları oluşturmak için sağlar.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Tanıdık durumu makine kip kullanarak içerilen etkinlikleri yürütür.|  
|<xref:System.Activities.Statements.State>|Durum makinesinin durumda temsil eder.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Durum makinesinin sonlandırma durumunda temsil eder. <xref:System.Activities.Core.Presentation.FinalState>bir etkinlik Tasarımcısı olduğunda kullanılan oluşturur bir <xref:System.Activities.Statements.State> sonlandırma durumu olarak yapılandırılmış. Daha fazla bilgi için bkz: [son durum etkinlik Tasarımcısı](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|İki durumlu arasında geçiş temsil eder. Yoktur hiçbir **araç** için madde <xref:System.Activities.Statements.Transition>; geçişleri arasında iki durumlu bir satır bırakarak iş akışı Tasarımcısı oluşturulur veya ne zaman görünür üçgenler bir durumda bırakarak durum başka bir üzerine getirildiği . Daha fazla bilgi için bkz: [geçiş etkinlik Tasarımcısı](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlangıç Öğreticisi](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
