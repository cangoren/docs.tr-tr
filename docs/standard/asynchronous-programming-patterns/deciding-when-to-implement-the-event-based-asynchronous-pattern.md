---
title: "Olay Tabanlı Zaman Uyumsuz Desenin Ne Zaman Uygulanacağını Belirleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48de1b736c251a61a2ad34975c77bc2bca139626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a>Olay Tabanlı Zaman Uyumsuz Desenin Ne Zaman Uygulanacağını Belirleme
Olay tabanlı zaman uyumsuz desen bir sınıfı zaman uyumsuz davranışı sunmaya yönelik bir desen sağlar. Bu desen girişiyle [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] zaman uyumsuz davranışı gösterme için iki modeli tanımlar: zaman uyumsuz desen dayalı <xref:System.IAsyncResult?displayProperty=nameWithType> arabirimi ve olay tabanlı düzeni. Bu konu, her iki desenlerini uygulama için uygun olduğunda açıklar.  
  
 İle zaman uyumsuz programlama hakkında daha fazla bilgi için <xref:System.IAsyncResult> arabirim için bkz: [olay tabanlı zaman uyumsuz desen (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
## <a name="general-principles"></a>Genel ilkeler  
 Genel olarak, olay tabanlı zaman uyumsuz desen mümkün olduğunca kullanarak zaman uyumsuz özellikler maruz bırakmamalısınız. Ancak, olay tabanlı deseni karşılayamayan bazı gereksinimler vardır. Bu durumda, uygulamanız gerekebilir <xref:System.IAsyncResult> olay tabanlı deseni yanı sıra düzeni.  
  
> [!NOTE]
>  Nadir <xref:System.IAsyncResult> da uygulanan olay tabanlı deseni uygulanması için desen.  
  
## <a name="guidelines"></a>Kuralları  
 Aşağıdaki liste, olay tabanlı zaman uyumsuz desenin ne zaman uygulamak için yönergeleri açıklar:  
  
-   Olay tabanlı deseni varsayılan API sınıfınız için zaman uyumsuz davranışı kullanıma sunmak için kullanın.  
  
-   Değil kullanıma <xref:System.IAsyncResult> desen sınıfınız öncelikle bir istemci uygulaması, örneğin Windows Forms kullanıldığında.  
  
-   Yalnızca kullanıma <xref:System.IAsyncResult> desen gereksinimlerinizi karşılamak için gerekli olduğunda. Örneğin, var olan bir API ile uyumluluk kullanıma sunmak gerektirebilecek <xref:System.IAsyncResult> düzeni.  
  
-   Değil kullanıma <xref:System.IAsyncResult> ayrıca olay tabanlı deseni gösterme olmadan düzeni.  
  
-   Kullanıma gerekir, <xref:System.IAsyncResult> desen, Gelişmiş bir seçenek olarak bunu. Proxy nesnesi oluşturursanız, örneğin, olay tabanlı deseni oluşturmak için bir seçenek ile varsayılan üretmek <xref:System.IAsyncResult> düzeni.  
  
-   Olay tabanlı deseni uygulamanızı oluşturmak, <xref:System.IAsyncResult> desen uygulaması.  
  
-   Her iki olay tabanlı deseni kullanılmasını önlemek ve <xref:System.IAsyncResult> düzeni aynı sınıfta. Olay tabanlı deseni "daha yüksek düzey" sınıflarda kullanıma ve <xref:System.IAsyncResult> üzerinde "düzeyini düşürmek" sınıfların desen. Örneğin, olay tabanlı deseni üzerinde karşılaştırmak <xref:System.Net.WebClient> ile bileşen <xref:System.IAsyncResult> üzerinde desen <xref:System.Web.HttpRequest> sınıfı.  
  
    -   Olay tabanlı deseni kullanıma ve <xref:System.IAsyncResult> düzeni uyumluluk gerektirdiğinde aynı sınıfta. Örneğin, kullanan bir API zaten yayımlandı <xref:System.IAsyncResult> desen korumak gerekir <xref:System.IAsyncResult> geriye dönük uyumluluk için desen.  
  
    -   Olay tabanlı deseni kullanıma ve <xref:System.IAsyncResult> elde edilen nesne modeli karmaşıklık uygulamaları ayırma avantajı ağır varsa aynı sınıf içinde desen. Olay tabanlı deseni kullanılmasını önlemek üzere daha tek bir sınıftaki her iki desenleri kullanıma sunmak iyidir.  
  
    -   Her iki olay tabanlı deseni kullanıma varsa ve <xref:System.IAsyncResult> kullanım tek bir sınıf desenine <xref:System.ComponentModel.EditorBrowsableAttribute> kümesine <xref:System.ComponentModel.EditorBrowsableState.Advanced> işaretlemek için <xref:System.IAsyncResult> Gelişmiş bir özellik olarak düzeni uygulaması. Bu tasarım ortamları için gibi gösterir [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] görüntüleme için IntelliSense, <xref:System.IAsyncResult> özellikleri ve yöntemleri. Bu özellikleri ve yöntemleri hala tam olarak kullanılabilir, ancak IntelliSense çalışan Geliştirici API daha anlaşılır bir görünüme sahiptir.  
  
## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a>Olay tabanlı deseni yanı sıra IAsyncResult düzeni gösterme ölçütleri  
 Olay tabanlı zaman uyumsuz desen yukarıda açıklanan senaryoları altında birçok avantaj sahipken, performans, en önemli gereksinimi varsa bilmeniz gereken bazı dezavantajları sahip.  
  
 Olay tabanlı deseni olmayan adres üç senaryo vardır yanı sıra <xref:System.IAsyncResult> Desen:  
  
-   Bir bekleme engelleme<xref:System.IAsyncResult>  
  
-   Birçok bekleme engelleme <xref:System.IAsyncResult> nesneleri  
  
-   Üzerinde tamamlanması için yoklama<xref:System.IAsyncResult>  
  
 Olay tabanlı deseni kullanarak bu senaryoyu ele, ancak bunun yapılması kullanmaktan daha kullanışsız <xref:System.IAsyncResult> düzeni.  
  
 Geliştiriciler sık kullandığınız <xref:System.IAsyncResult> genellikle çok yüksek performans gereksinimlerin Hizmetleri için desen. Örneğin, yoklama tamamlama senaryosu için yüksek performanslı sunucu tekniğidir.  
  
 Ayrıca, olay tabanlı deseni daha az verimli <xref:System.IAsyncResult> daha fazla nesneleri, özellikle oluşturduğundan desen <xref:System.EventArgs>, ve iş parçacıkları arasında eşitler.  
  
 Aşağıdaki liste kullanmaya karar verirseniz izlemek için bazı öneriler gösterir <xref:System.IAsyncResult> Desen:  
  
-   Yalnızca kullanıma <xref:System.IAsyncResult> desen desteği özellikle gerektirdiğinde <xref:System.Threading.WaitHandle> veya <xref:System.IAsyncResult> nesneleri.  
  
-   Yalnızca kullanıma <xref:System.IAsyncResult> desen kullanan mevcut bir API olduğunda <xref:System.IAsyncResult> düzeni.  
  
-   Temel bir varolan API varsa <xref:System.IAsyncResult> desen, ayrıca, bir sonraki sürümde olay tabanlı deseni gösterme göz önünde bulundurun.  
  
-   Yalnızca kullanıma <xref:System.IAsyncResult> doğrulandı yüksek performans gereksinimlerini varsa düzeni olay tabanlı bir desen karşılanamıyor ancak tarafından karşılanması <xref:System.IAsyncResult> düzeni.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Olay tabanlı zaman uyumsuz deseni destekleyen bir bileşeni uygulama](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [Olay tabanlı zaman uyumsuz desen (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Olay tabanlı zaman uyumsuz desen ile birden çok iş parçacıklı programlama](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [Olay tabanlı zaman uyumsuz deseni uygulama](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 [Olay tabanlı zaman uyumsuz desen uygulamak için en iyi uygulamalar](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 [Olay tabanlı zaman uyumsuz desene genel bakış](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
