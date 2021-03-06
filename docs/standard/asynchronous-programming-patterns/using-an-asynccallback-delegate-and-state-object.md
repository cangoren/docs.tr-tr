---
title: Bir AsyncCallback Temsilcisi ve Durum Nesnesi Kullanma
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e8793a78289e9b58407038f41cc9d403ff9f9940
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a>Bir AsyncCallback Temsilcisi ve Durum Nesnesi Kullanma
Kullandığınızda, bir <xref:System.AsyncCallback> zaman uyumsuz işlemi ayrı bir iş parçacığı sonuçlarını işlemek için temsilci seçme, bir durum nesnesi geri aramalar arasında bilgi aktarmak ve son sonucu almak için kullanabilirsiniz. Bu konuda, uygulama örnekte genişleterek gösterilir [zaman uyumsuz bir işlemi sonlandırmak için bir AsyncCallback temsilcisi kullanarak](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde zaman uyumsuz yöntemleri kullanma gösterilmektedir <xref:System.Net.Dns> kullanıcı tarafından belirtilen bilgisayarların etki alanı adı sistemi (DNS) bilgilerini almak için sınıf. Bu örnek tanımlar ve kullanır `HostRequest` durum bilgilerini depolamak için sınıf. A `HostRequest` nesne kullanıcı tarafından girilen her bir bilgisayar adı için oluşturulan. Bu nesne için geçirilen <xref:System.Net.Dns.BeginGetHostByName%2A> yöntemi. `ProcessDnsInformation` Yöntemi, bir isteği tamamlayan her zaman çağrılır. `HostRequest` Nesnesi kullanarak alınır <xref:System.IAsyncResult.AsyncState%2A> özelliği. `ProcessDnsInformation` Yöntemi kullanan `HostRequest` depolamak için nesne <xref:System.Net.IPHostEntry> istek tarafından döndürülen veya <xref:System.Net.Sockets.SocketException> istek tarafından oluşturulur. Tüm istekleri tamamlandığı zaman üzerinden uygulama tekrarlanan `HostRequest` nesneleri ve DNS bilgilerini görüntüler veya <xref:System.Net.Sockets.SocketException> hata iletisi.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay tabanlı zaman uyumsuz desen (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Olay tabanlı zaman uyumsuz desene genel bakış](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [Zaman uyumsuz bir işlemi sonlandırmak için bir AsyncCallback temsilcisi kullanma](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
