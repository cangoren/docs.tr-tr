---
title: "Kuyruğa Alınan İletişim için En İyi Uygulamalar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queues [WCF], best practices
- best practices [WCF], queued communication
ms.assetid: 446a6383-cae3-4338-b193-a33c14a49948
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15de43cc83e92b781e44da703353bec98dbc2c6a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="best-practices-for-queued-communication"></a>Kuyruğa Alınan İletişim için En İyi Uygulamalar
Bu konu içinde kuyruğa alınan iletişim için önerilen yöntemler sağlar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Aşağıdaki bölümlerde bir senaryo açısından önerilen yöntemler açıklanmaktadır.  
  
## <a name="fast-best-effort-queued-messaging"></a>Hızlı ve en yüksek çaba ileti kuyruğa  
 İleti kuyruğa ayrımı sağlar gerektiren senaryolar ve hızlı, yüksek performanslı en yüksek çaba çıkışların ile Mesajlaşma, işlemsel olmayan bir sıraya kullanın ve ayarlayın <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> özelliğine `false`.  
  
 Ayrıca, disk yazma işlemleri maliyetini ayarlayarak tabi değil seçebileceğiniz <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> özelliğine `false`.  
  
 Güvenlik, performans üzerinde etkilere sahiptir. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Başarım düşünceleri](../../../../docs/framework/wcf/feature-details/performance-considerations.md).  
  
## <a name="reliable-end-to-end-queued-messaging"></a>Güvenilir uçtan uca ileti kuyruğa alındı  
 Aşağıdaki bölümler, uçtan uca güvenilir Mesajlaşma gerektiren senaryolar için önerilen uygulamaları açıklamaktadır.  
  
### <a name="basic-reliable-transfer"></a>Temel güvenilir aktarımı  
 Uçtan uca güvenilirlik için ayarlanmış <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> özelliğine `true` aktarım sağlamak için. <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> Özelliği ayarlanabilir `true` veya `false` gereksinimlerinize bağlı olarak (varsayılan `true`). Genellikle, <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> özelliği ayarlanmış `true` uçtan uca güvenilirlik bir parçası olarak. Güvenlik aşılması performans maliyeti, ancak sıra yöneticisi çökme gerçekleşirse ileti kayıp olmaması ileti dayanıklı hale getirir.  
  
### <a name="use-of-transactions"></a>İşlemleri kullanma  
 İşlemler, uçtan uca güvenilirlik sağlamak için kullanmalısınız. `ExactlyOnce`çıkışların yalnızca iletileri hedef sıraya teslim edilir emin olun. İleti alındığında emin olmak için işlemleri kullanın. Hizmetin çökmesi durumunda işlemler olmadan teslim edilmekte olduğu, ancak gerçekte uygulamaya teslim ileti kaybedersiniz.  
  
### <a name="use-of-dead-letter-queues"></a>Teslim edilemeyen iletiler sırası kullanma  
 Teslim edilemeyen iletiler sırası hedef sıraya teslim edilmesi bir ileti başarısız olursa bildirim aldığından emin olun. Sistem tarafından sağlanan sahipsiz sırayı veya özel bir sahipsiz sırayı kullanabilirsiniz. Tek bir sahipsiz sıraya içine bir uygulamadan teslim edilemeyen iletiler göndermenize olanak sağladığından genel olarak, özel bir sahipsiz sırayı kullanarak en iyisidir. Aksi takdirde, sistem üzerinde çalışan tüm uygulamaları için ortaya çıkan tüm teslim edilemeyen iletiler tek bir sıraya teslim edilir. Ardından, her uygulama yine de bu uygulamayla ilgili teslim edilemeyen iletiler bulmak için sahipsiz sırayı aramanız gerekir. Bazı durumlarda, özel bir sahipsiz sırayı kullanarak MSMQ 3.0 kullanırken gibi uygun değildir.  
  
 Sıralarındaki uçtan uca güvenilir iletişim için kapatma önerilmez.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][İletiyi işlemek için kullanarak sıralarındaki aktarım hataları](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).  
  
### <a name="use-of-poison-message-handling"></a>Poison ileti işleme kullanımı  
 Poison ileti işleme işlem iletileri hatasından kurtarma olanağı sağlar.  
  
 Poison ileti işleme özelliğini kullanırken emin <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> özelliğini uygun değere ayarlayın. Ayar <xref:System.ServiceModel.ReceiveErrorHandling.Drop> veriler kaybolur anlamına gelir. Diğer taraftan, ayarı <xref:System.ServiceModel.ReceiveErrorHandling.Fault> zararlı bir ileti algıladığında hizmet konağı hataları. MSMQ 3.0 kullanılarak <xref:System.ServiceModel.ReceiveErrorHandling.Fault> veri kaybını önlemek ve zararlı ileti dışına taşımak için en iyi seçenektir. MSMQ 4. 0'da da kullanarak <xref:System.ServiceModel.ReceiveErrorHandling.Move> önerilen yaklaşımdır. <xref:System.ServiceModel.ReceiveErrorHandling.Move>Hizmet yeni iletileri işlemeye devam edebilmek için sıradaki zarar görmüş bir ileti taşır. Poison ileti hizmeti zehir iletisi sonra ayrı olarak işleyebilir.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Zehirli ileti işleme](../../../../docs/framework/wcf/feature-details/poison-message-handling.md).  
  
## <a name="achieving-high-throughput"></a>Yüksek verimlilik elde  
 Tek bir uç noktada yüksek verimlilik elde etmek için aşağıdakileri kullanın:  
  
-   İşlem yapılan toplu işlem. İşlenen toplu iş çok sayıda ileti tek bir işlemde okuyabilmelerini sağlar. Bu işlem yürütme, genel performansı artırma en iyi duruma getirir. Toplu işleme maliyetini bir yığın içindeki tek bir ileti hata oluşuyor sonra toplu işlemin tamamını geri alınır ve iletileri işlenen teker teker yeniden toplu güvenlidir kadar olması gerekiyorsa olmasıdır. Çoğu durumda, toplu işleme özellikle işlemde diğer kaynak yöneticileri olduğunda sistem performansını artırmak için tercih edilen yöntem olmasını zarar iletileri seyrek, kullanılır. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Bir işlemde toplu ileti işleme](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md).  
  
-   Eşzamanlılık. Eşzamanlılık verimliliğini artırır, ancak eşzamanlılık paylaşılan kaynakları için Çekişme de etkiler. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Eşzamanlılık](../../../../docs/framework/wcf/samples/concurrency.md).  
  
-   Azaltma. En iyi performans için ileti dağıtıcısı ardışık düzeninde sayısını azaltma. Bunun nasıl yapılacağı örneği için bkz: [azaltma](../../../../docs/framework/wcf/samples/throttling.md).  
  
 Toplu işleme kullanırken, eşzamanlılık ve azaltma için eş zamanlı toplu Çevir unutmayın.  
  
 Daha yüksek performans ve kullanılabilirlik elde etmek için bir grubu kullanmak [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kuyruktan okunmak Hizmetleri. Bu, tüm bu hizmetleri aynı sözleşme aynı uç noktada kullanıma gerektirir. Grup yaklaşım iletileri yüksek üretim oranları tüm hizmetlerin sayısı sağladığından olan uygulamalar için en iyi çalışır aynı kuyruktan okuyun.  
  
 Grupları kullanırken, MSMQ 3.0 uzak işlem temelli okuma desteklemediğini unutmayın. MSMQ 4.0 uzaktan hizmetteki okuma desteklemiyor.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Bir işlemde toplu ileti işleme](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md) ve [Windows Vista, Windows Server 2003 ve Windows XP'de kuyruğa alma özelliği farklar](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).  
  
## <a name="queuing-with-unit-of-work-semantics"></a>İş semantiği birimle queuing  
 Bazı senaryolarda iletiler bir kuyrukta grubunu ilgili olabilir ve bu nedenle, bu iletilerin sıralama önemlidir. Bu senaryolarda, ilgili iletiler birlikte tek bir birim olarak bir grup işlem: tüm iletileri başarıyla işlendi ya da yok. Bu tür davranış uygulamak için kuyruklarla oturumları kullanın.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Bir oturumda kuyruğa alınmış iletileri gruplandırma](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md).  
  
## <a name="correlating-request-reply-messages"></a>İstek-yanıt iletilerini ilişkilendirme  
 Kuyruklar genellikle tek yönlü olmakla birlikte, bazı senaryolarda daha önce gönderilen bir istek aldı bir Yanıtla ilişkilendirmek isteyebilirsiniz. Bu tür bağıntı gerektiriyorsa, iletinin bağıntı bilgilerle içeren kendi SOAP iletisi üstbilgisi uygulamanız önerilir. Genellikle, bu iletiyi başlığıyla gönderen ekler ve iletiyi işlemeyi ve yanıt sırası üzerinde yeni bir ileti ile geri yanıtlama alıcı, böylece gönderenin bağıntı bilgilerini içeren gönderenin ileti üstbilgisi ekler İstek iletisi yanıt iletisiyle tanımlayın.  
  
## <a name="integrating-with-non-wcf-applications"></a>WCF olmayan uygulamaları ile tümleştirme  
 Kullanım `MsmqIntegrationBinding` tümleştirdiğinizde [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmetleri veya istemcileriyle olmayan[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmetleri veya istemciler. Olmayan[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uygulama System.Messaging, COM + kullanılarak yazılmış bir MSMQ uygulaması olabilir [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], ya da C++.  
  
 Kullanırken `MsmqIntegrationBinding`, aşağıdakilere dikkat edin:  
  
-   A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ileti gövdesi MSMQ İleti gövdesi ile aynı değil. Gönderirken bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sıraya alınmış bir bağlamayı kullanarak ileti [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ileti gövdesi içinde MSMQ iletisi yerleştirilir. Bu ek bilgiler oblivious MSMQ altyapısıdır; yalnızca MSMQ iletisi görür.  
  
-   `MsmqIntegrationBinding`popüler serileştirme türlerini destekler. Genel ileti gövdesi türü seri hale getirme türüne göre <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, farklı tür parametreleri alır. Örneğin, <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat.ByteArray> gerektirir `MsmqMessage\<byte[]>` ve <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat.Stream> gerektirir `MsmqMessage<Stream>`.  
  
-   XML serileştirilmesi ile bilinen türü kullanılarak belirtebilirsiniz `KnownTypes` özniteliği [ \<davranışı >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) sonra XML iletisini seri durumdan nasıl belirlemek için kullanılan öğesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WCF'de kuyruğa alma](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [Nasıl yapılır: WCF uç noktaları iletileri kuyruğa alınan](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [Nasıl yapılır: WCF uç noktaları iletileri Exchange ve Message Queuing uygulamaları](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [Kuyruğa alınmış iletileri bir oturumda gruplandırma](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md)  
 [Bir işlemde toplu ileti işleme](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md)  
 [İleti aktarımı hatalarını işlemek için teslim edilemeyen iletiler sırası kullanma](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 [Zehirli ileti işleme](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)  
 [Windows Vista, Windows Server 2003 ve Windows XP'de kuyruğa alma özelliği farklar](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)  
 [Taşıma Güveliği kullanarak iletileri güvenli hale getirme](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)  
 [İleti Güveliği kullanarak iletileri güvenli hale getirme](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md)  
 [Kuyruğa Alınan iletilerde sorun giderme](../../../../docs/framework/wcf/feature-details/troubleshooting-queued-messaging.md)
