---
title: InvokeMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c275943d37a3602335ecd898aed3feb6c9059edf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="invokemethod"></a>InvokeMethod
Bu örnek kullanarak farklı yollarını gösterir <xref:System.Activities.Statements.InvokeMethod> bir sınıfın yöntemleri çağırmak için etkinlik.  
  
 Bir yöntem bir sınıfa ait ve içerdiği bir işlemler kümesini temsil eder. <xref:System.Activities.Statements.InvokeMethod> Etkinlik, nesneler veya türleri karşı yöntemlerini çağırın, parametreleri geçirin ve dönüş değerini alma olanağı verir. Yöntemleri zaman uyumlu veya zaman uyumsuz olarak çağrılabilir.  
  
## <a name="sample-details"></a>Örnek Ayrıntıları  
 Bu örnekte <xref:System.Activities.Statements.InvokeMethod> aşağıdaki senaryolarda gerçekleştirme etkinliği:  
  
1.  Parametresiz bir örnek yöntemi çağırır.  
  
2.  Örnek yöntemi iki parametre ile çağırma (<xref:System.String> ve <xref:System.Int32>).  
  
3.  Örnek yöntemi iki parametre ile çağırma (<xref:System.String> ve <xref:System.Int32>) ve bir parametre dizisi türü <xref:System.String>[].  
  
4.  Örnek yöntemi iki parametre türü ile çağırma <xref:System.Int32> ve bir sonuç türü <xref:System.Int32>. Bu senaryoda, sonuç değeri bir değişkene bağlı ve başka bir etkinliğin kullanılır. Konsolunu kullanarak görüntülenir <xref:System.Activities.Statements.WriteLine> etkinlik.  
  
5.  Türünde iki parametre ile bir statik yöntem çağırma <xref:System.String> ve <xref:System.Int32>.  
  
6.  Türünde bir genel parametresi ile örnek yöntemi çağırma <xref:System.String>.  
  
7.  Türünde iki genel parametreleri olan bir statik yöntem çağırma <xref:System.String> ve <xref:System.Int32>.  
  
8.  Başvuru türü tarafından geçirilen bir parametre olan örnek yöntemi çağırma <xref:System.String>. Bu senaryoda, bir değişkene başvuru parametresine bağlıdır (`outParam`) ve başka bir etkinliğin kullanılır. Konsolunu kullanarak görüntülenir <xref:System.Activities.Statements.WriteLine> etkinlik.  
  
9. Zaman uyumsuz örnek yöntemi çağırır.  
  
10. Aynı örneği iki kullanan bir nesne üzerinde iki farklı yöntem çağırma <xref:System.Activities.Statements.InvokeMethod> etkinlikler.  
  
11. Bir değer bir nesne örneğini depolar.  
  
12. Bir nesnenin bir örnekten bir değer alır.  
  
## <a name="to-use-this-sample"></a>Bu örneği kullanmak için  
 Bu örnek iki sürümlerinde sağlanır. Bu örnek ilk sürümü kullanımını gösteren <xref:System.Activities.Statements.InvokeMethod> C# ile kullanarak kod [!INCLUDE[wf](../../../../includes/wf-md.md)] programlama modeli ve CodedWorkflow\CS klasörü altında bulunabilir. İkinci Sürüm kullanımını gösteren <xref:System.Activities.Statements.InvokeMethod> XAML kullanılarak ve DesignerWorkflow\CS klasörü altında bulunabilir.  
  
#### <a name="to-run-the-coded-workflow-sample"></a>Kodlanmış iş akışı örneği çalıştırmak için  
  
1.  Kullanarak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], CodedWorkflow\CS klasöründeki InvokeMethodUsage.sln çözüm dosyasını açın.  
  
2.  Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.  
  
3.  Çözümü çalıştırmak için CTRL + F5 tuşuna basın.  
  
#### <a name="to-run-the-designer-workflow-sample"></a>Tasarımcı iş akışı örneği çalıştırmak için  
  
1.  Kullanarak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], DesignerWorkflow\CS klasöründeki InvokeMethodUsage.sln çözüm dosyasını açın.  
  
2.  Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.  
  
3.  Çözümü çalıştırmak için CTRL + F5 tuşuna basın.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`