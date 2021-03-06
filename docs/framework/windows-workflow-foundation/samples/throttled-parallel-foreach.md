---
title: "Daraltılmış paralel ForEach"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d7a3ea5f4ec911a6965ce07c098d460ca0cbd929
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="throttled-parallel-foreach"></a>Daraltılmış paralel ForEach
`ThrottleParallelForEach` Etkinlik benzer <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` etkinliği bir özel durum ile onun bir eşzamanlılık faktörü ayarını yürütmek için eşzamanlı dalların sayısını kısıtlayın izin verir. `ThrottleParallelForEach` Etkinlik türer <xref:System.Activities.NativeActivity>, diğer etkinlikleri (alt) zamanlama gerekir ve bu yalnızca üzerinden erişilebilir olduğundan <xref:System.Activities.NativeActivityContext> sınıfı.  
  
## <a name="projects"></a>Projeler  
  
|**ProjectName**|**Açıklama**|**Ana dosyaları**|  
|-|-|-|  
|ThrottledParallelForEach|İçeren `ThrottledParallelForEach` etkinliği ve onun Tasarımcısı.|ThrottledParallelForEach.cs<br /><br /> `ThrottledParallelForEach` Etkinlik tanımı.|  
|CodeTestClient|Örnek yapılandırır ve bir iş akışı ile çalıştıran istemci uygulamanın bir `ThrottledParallelForEach` kesinlik temelli kod kullanarak.|Program.cs<br /><br /> Örnek iş akışı örneğini çalıştıran ve tanımlar.|  
  
#### <a name="to-use-this-sample"></a>Bu örneği kullanmak için  
  
1.  Kullanarak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], ThrottledParallelForEach.sln dosyasını açın.  
  
2.  Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.  
  
3.  Çözümü çalıştırmak için F5 tuşuna basın.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`