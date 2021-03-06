---
title: "İşlem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: effdc8e6-accf-41eb-98a5-431603ba218b
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4a6dcd11d34f0b81d6d3982ef1c6ab211d94818b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="transaction-processing"></a>İşlem
Bir çevrimiçi bir kitaplığı defterinden satın aldığınızda, bir kitap (kredi biçiminde) karşılığında exchange. Kredi iyi ise, bir dizi ilgili operations defteri alma ve kitaplığı, para alır sağlar. Ancak, tek bir işlemde serisinde exchange sırasında başarısız olursa, tüm exchange başarısız olur. Kitap alma ve kitaplığı, para almaz.  
  
 Exchange Dengeli ve öngörülebilir yapmaktan sorumlu teknolojisi, işlem adı verilir. İşlemler işlem birimindeki tüm işlemleri başarıyla tamamlamak sürece veri yönelimli kaynakları kalıcı olarak güncelleştirilmez emin olun. Tamamen başarılı ya da tamamen başarısız bir birim ilgili işlemlere kümesini birleştirerek hata kurtarma basitleştirmek ve uygulamanızı daha güvenilir hale getirebilirsiniz.  
  
 Hareket işleme sistemleri bilgisayar donanımı ve yazılımı iş yürütmek gerekli rutin işlemleri gerçekleştirir işleme dayalı bir uygulamayı barındıran oluşur. Örnekler yönetme sipariş girişi, uçak ayırmaları, bordro, üretim ve sevkiyat çalışan kayıtları, sistemleri içerir.  
  
 Bu bölüm hem işlem hakkında genel bilgiler ve işlemsel uygulamaları ve Microsoft .NET Framework kullanarak kaynak yöneticileri yazma konusunda belirli bilgiler sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [İşlem temelleri](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 Temel işlem terimleri ve kavramları işleme tanıtır.  
  
 [System.Transactions tarafından sağlanan özellikleri](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md)  
 Özellikleri System.Transactions işlem uygulamanızı yazmak için nasıl kullanabileceğinizi açıklar.  
  
## <a name="reference"></a>Başvuru  
 <xref:System.Transactions>  
 Kodunuzu işlemlere katılmasına izin sınıflar sağlar. Sınıfları birden fazla dağıtılmış katılımcıları, birden çok aşaması bildirimleri ve kalıcı kayıtlar ile işlemleri destekler.
