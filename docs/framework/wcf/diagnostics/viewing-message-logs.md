---
title: "İleti Günlüklerini Görüntüleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: df1d796ec5009008e00391eea2987f5256df6c48
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="viewing-message-logs"></a>İleti Günlüklerini Görüntüleme
Bu konuda, ileti günlüklerini nasıl görüntüleyebileceğiniz açıklanır.  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a>İleti görüntüleme hizmet izleme Görüntüleyicisi'nde günlüğe kaydeder  
 Tarafından işlendiği bir ileti dönüştürülmüş [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Bu nedenle, yalnızca ileti içeriği noktada kaydedildiğini, içeriğini değil Tel üzerinde bir ileti günlüğe kaydedilmesini yansıtır.  
  
 İleti günlüğe kaydetme çıktısını iletisinin aktarımı biçimine hiçbir ilişki olduğundan, her zaman ileti günlüğe kaydetme kodu çözülmüş ileti çıkarır. İleti günlüğünü düzgün yapılandırdıysanız, günlüğe kaydedilen tüm iletiler düz metin olarak olmalıdır. Örneğin, günlüğe kaydedilen iletilere biçimi (düz metin) ikili ileti kodlayıcı kullanımını etkilenmez.  
  
 XmlWriterTraceListener çıktısını bir dizi parçalarını içeren bir dosyadır. Dosya geçerli bir XML dosyası değil bilmeniz gerekir. Kullanmanız önerilir [hizmet izleme Görüntüleyicisi aracı (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) ileti günlük dosyalarını görüntülemek için. Bu aracın nasıl kullanılacağı hakkında daha fazla bilgi için bkz: [bağıntılı izlemeleri görüntüleme ve sorun giderme için hizmet izleme görüntüleyicisini kullanma](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 Hizmet izleme Görüntüleyicisi'nde iletileri listelenen **ileti** sekmesi. Neden olan veya olmayan iletilerini ilgili işleme hatası, sarı (uyarı düzeyi) ya da kırmızı (hata düzeyi) hatanın önem düzeyine bağlı olarak vurgulanır. İstek işlenirken bağlamında ileti izleme yukarı iletide çift getirir.  
  
> [!NOTE]
>  Bir ileti, üst Hayır sahipse `<header/>` etiketi günlüğe kaydedilir.  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a>Bir istemci, bir geçiş ve bir hizmet tarafından günlüğe kaydedilen iletileri görüntüleme  
 Ortamınızı daha sonra hizmet iletiyi iletir geçiş, bir ileti gönderir bir istemci içerebilir. Ne zaman ileti günlüğe kaydetme, tüm üç konumlarının etkinleştirildiğinde ve üç ileti günlüğü içinde görüntülenen [hizmet izleme Görüntüleyicisi aracı (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) ileti günlüğü alışverişlerinde yanlış eşzamanlı olarak işlenir. Bunun nedeni, `CorrelationId` ve `ActivityId` ileti üstbilgisinde her send-receive çifti için benzersiz değildir.  
  
 Bu sorunu gidermek için aşağıdaki yöntemlerden birini kullanabilirsiniz.  
  
-   Yalnızca iki üç ileti günlüklerde görüntülemek [hizmet izleme Görüntüleyicisi aracı (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) dilediğiniz zaman.  
  
-   Tüm üç günlüklerinde görüntülerseniz gerekir [hizmet izleme Görüntüleyicisi aracı (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) aynı anda yeni bir oluşturarak geçiş hizmeti değiştirebilirsiniz <xref:System.ServiceModel.Channels.Message> örneği. Bu örnek dışındaki tüm üstbilgileri yanı sıra gelen ileti gövdesi bir kopyası olmalıdır `ActivityId` ve `Action` üstbilgileri. Aşağıdaki kod örneği, bunun nasıl yapılacağı gösterilmektedir.  
  
```  
Message outgoingMessage = Message.CreateMessage(incomingMessage.Version, incomingMessage.Headers.Action, incomingMessage.GetReaderAtBodyContents());  
  
for (int i = 0; i < incomingMessage.Headers.Count; i++)  
{  
   if (incomingMessage.Headers[i].Name.Equals("ActivityId", StringComparison.InvariantCultureIgnoreCase) ||  
incomingMessage.Headers[i].Name.Equals("Action", StringComparison.InvariantCultureIgnoreCase))  
   {  
      continue;  
    }  
    outgoingMessage.Headers.CopyHeaderFrom(incomingMessage, i);  
}  
```  
  
## <a name="exceptional-cases-for-inaccurate-message-logging-content"></a>Yanlış ileti günlüğe kaydetme içerik için olağanüstü durumlar  
 Aşağıdaki koşullarda iletileri günlüğe kaydedilmesini kablo mevcut sekizli akış tam temsilini olmayabilir.  
  
-   Hiçbiri gelen / adresleme/içinde iletileri için BasicHttpBinding için zarf üstbilgileri günlüğe kaydedilen ad alanı.  
  
-   Boşluk eşleşmeyen.  
  
-   Gelen iletiler için boş öğeleri farklı temsil edilebilir. Örneğin, \<etiketi >\</etiket > yerine \<etiketi / >  
  
-   Bilinen PII günlüğü devre dışı bırakıldığında varsayılan veya açık ayarı enableLoggingKnownPii = "true".  
  
-   Kodlama UTF-8'e dönüştürme için etkinleştirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmet izleme Görüntüleyicisi aracı (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [İzlemeleri görüntüleme bağıntılı için hizmet izleme görüntüleyicisini kullanma ve sorun giderme](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [İleti günlüğe kaydetme](../../../../docs/framework/wcf/diagnostics/message-logging.md)
