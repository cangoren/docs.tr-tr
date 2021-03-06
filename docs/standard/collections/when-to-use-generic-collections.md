---
title: "Genel Koleksiyonları Ne Zaman Kullanılacağı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- collections [.NET Framework], generic
- generic collections [.NET Framework]
ms.assetid: e7b868b1-11fe-4ac5-bed3-de68aca47739
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6e6f23c413bbefe6a29746e2f6a1887a23dd3bfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-use-generic-collections"></a>Genel Koleksiyonları Ne Zaman Kullanılacağı
Temel koleksiyonu türden türetilmiş ve türüne özgü üyeleri uygulamak gerek kalmadan tür güvenliği hemen avantajı elde çünkü genel koleksiyonlar kullanarak genellikle önerilir. Genel koleksiyon türleri de genellikle gerçekleştirmek nongeneric koleksiyon türleri ve karşılık gelen daha iyi (ve türlerini daha iyi, türetilen nongeneric temel koleksiyonu türlerinden) koleksiyon öğeleri olduğunda değer türleri, genel türler ile olduğundan öğeler kutu gerek yoktur.  
  
 Programları hedefleyen [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] veya daha sonra genel koleksiyon sınıfları kullanması gereken <xref:System.Collections.Concurrent> birden çok iş parçacığı ekleme veya öğeleri koleksiyondan eşzamanlı olarak kaldırma, ad alanı.  
  
 Aşağıdaki genel türler varolan koleksiyon türlerine karşılık gelir:  
  
-   <xref:System.Collections.Generic.List%601>karşılık gelen genel bir sınıftır <xref:System.Collections.ArrayList>.  
  
-   <xref:System.Collections.Generic.Dictionary%602>ve <xref:System.Collections.Concurrent.ConcurrentDictionary%602> karşılık genel sınıfları <xref:System.Collections.Hashtable>.  
  
-   <xref:System.Collections.ObjectModel.Collection%601>karşılık gelen genel bir sınıftır <xref:System.Collections.CollectionBase>. <xref:System.Collections.ObjectModel.Collection%601>Ancak bir temel sınıf olarak kullanılan <xref:System.Collections.CollectionBase>, Özet değil. Bu, çok kullanmak kolaylaştırır.  
  
-   <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>karşılık gelen genel bir sınıftır <xref:System.Collections.ReadOnlyCollectionBase>. <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>Özet olmayan ve var olan kullanıma sunmak kolaylaştıran bir kurucusu olan <xref:System.Collections.Generic.List%601> salt okunur bir koleksiyon olarak.  
  
-   <xref:System.Collections.Generic.Queue%601>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Generic.Stack%601>, <xref:System.Collections.Concurrent.ConcurrentStack%601>, Ve <xref:System.Collections.Generic.SortedList%602> Genel sınıflar aynı adlarıyla ilgili nongeneric sınıfları karşılık gelir.  
  
## <a name="additional-types"></a>Ek türleri  
 Birkaç genel koleksiyon türleri nongeneric ortaklarınıza gerekmez. Bunlar aşağıdakileri içerir:  
  
-   <xref:System.Collections.Generic.LinkedList%601>O(1) ekleme ve kaldırma işlemlerini sağlayan genel amaçlı bağlantılı listesidir.  
  
-   <xref:System.Collections.Generic.SortedDictionary%602>O ile sıralanmış bir sözlük (günlük `n`) için yararlı bir alternatif kolaylaştırır, ekleme ve alma işlemleri <xref:System.Collections.Generic.SortedList%602>.  
  
-   <xref:System.Collections.ObjectModel.KeyedCollection%602>bir karma listesini ve kendi anahtarlarını içeren nesneleri depolamak için bir yol sağlayan bir sözlüğü arasında değil.  
  
-   <xref:System.Collections.Concurrent.BlockingCollection%601>sınırlama ve engelleme işlevi ile koleksiyon sınıfına uygular.  
  
-   <xref:System.Collections.Concurrent.ConcurrentBag%601>Hızlı ekleme ve kaldırma sırasız öğelerinin sağlar.  
  
## <a name="linq-to-objects"></a>Nesnelere LINQ  
 LINQ to nesneleri özelliği, nesne türü uygulayan sürece bellek içi nesnelere erişmek için LINQ sorgularını kullanmanıza olanak tanır <xref:System.Collections.IEnumerable?displayProperty=nameWithType> veya <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> arabirimi. LINQ sorguları verilerine erişmek için genel bir desen sağlar; genellikle daha kısa ve standart okunabilir olan `foreach` döngü; ve filtreleme, sıralama ve yetenekleri gruplandırma sağlar. LINQ sorguları da performansı artırabilir. Daha fazla bilgi için bkz: [nesnelere LINQ](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9) ve [paralel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="additional-functionality"></a>Ek işlevler  
 Bazı genel türleri nongeneric koleksiyon türlerinde bulunamadı işlevselliğe sahiptir. Örneğin, <xref:System.Collections.Generic.List%601> nongeneric karşılık gelen sınıf <xref:System.Collections.ArrayList> sınıfı, bir dizi genel temsilciler gibi kabul yöntemi sahip <xref:System.Predicate%601> listeninaramayöntemleribelirtmenizeolanaktanırtemsilci<xref:System.Action%601>her liste öğesi üzerinde hareket yöntemlerini temsil eder temsilci ve <xref:System.Converter%602> temsilci türleri arasında dönüştürmeler tanımlamanıza izin verir.  
  
 <xref:System.Collections.Generic.List%601> Sınıfı belirtmenize olanak verir, kendi <xref:System.Collections.Generic.IComparer%601> sıralama ve arama listesi için genel arabirim uygulamaları. <xref:System.Collections.Generic.SortedDictionary%602> Ve <xref:System.Collections.Generic.SortedList%602> sınıfları Ayrıca bu özelliği vardır. Ayrıca, bu sınıfları koleksiyonu oluşturulduğunda comparers belirtmenizi sağlar. Benzer şekilde, <xref:System.Collections.Generic.Dictionary%602> ve <xref:System.Collections.ObjectModel.KeyedCollection%602> sınıfları kendi eşitlik comparers belirtmenize olanak tanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonlar ve veri yapıları](../../../docs/standard/collections/index.md)  
 [Çok kullanılan koleksiyon türleri](../../../docs/standard/collections/commonly-used-collection-types.md)  
 [Genel türler](../../../docs/standard/generics/index.md)
