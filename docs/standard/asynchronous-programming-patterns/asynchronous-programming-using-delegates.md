---
title: Temsilcileri Kullanarak Zaman Uyumsuz Programlama
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET Framework], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 596d2be26318b782423653b4eb3f43c1f9fc4b92
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="asynchronous-programming-using-delegates"></a>Temsilcileri Kullanarak Zaman Uyumsuz Programlama
Temsilciler bir zaman uyumsuz olarak zaman uyumlu bir yöntemi çağırmak etkinleştirin. Zaman uyumlu olarak, bir temsilciyi çağırdığınızda `Invoke` yöntemi doğrudan geçerli iş parçacığı üzerinde hedef yöntemini çağırır. Varsa `BeginInvoke` yöntemi çağrıldığında, ortak dil çalışma zamanı (CLR) isteğini sıraya koyar ve hemen çağırana döndürür. Hedef yöntemin iş parçacığı havuzundaki iş parçacığı üzerinde zaman uyumsuz olarak çağrılır. İstek gönderildi, orijinal iş parçacığı, hedef yöntemin ile Paralel yürütme devam etmek ücretsizdir. Bir geri çağırma yöntemi çağrısında belirtildiğinde `BeginInvoke` yöntemi, geri çağırma yöntemi hedef yöntemin bittikten sonra çağrılır. Geri çağırma yöntemi `EndInvoke` yöntemi, dönüş değeri ve giriş/çıkış ya da yalnızca çıktı parametreleri alır. Geri çağırma yöntemi çağrılırken belirtilmişse `BeginInvoke`, `EndInvoke` çağıran iş parçacığının çağrılabilir `BeginInvoke`.  
  
> [!IMPORTANT]
>  Derleyicileri temsilci sınıflarıyla yayma `Invoke`, `BeginInvoke`, ve `EndInvoke` yöntemlerini kullanarak kullanıcı tarafından belirtilen temsilci imzası. `BeginInvoke` Ve `EndInvoke` yöntemleri donatılmış olarak yerel. Bu yöntemler yerel olarak işaretlenmiş olduğundan, CLR uygulamasını sınıf yükleme zamanında otomatik olarak sağlar. Bunlar değil geçersiz yükleyici sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Zaman uyumlu yöntemleri zaman uyumsuz olarak çağırma](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Sıradan yöntemleri zaman uyumsuz çağrı yapmak için temsilciler kullanmayı açıklar ve bir zaman uyumsuz çağrı döndürmek beklenecek dört yolu Göster basit kod örnekleri sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Olay tabanlı zaman uyumsuz desen (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 .NET Framework ile zaman uyumsuz programlama açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Delegate>
