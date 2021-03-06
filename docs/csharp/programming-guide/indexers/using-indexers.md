---
title: "Dizin Oluşturucular Kullanma (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d5c727edbbea116d858c6acf6b600f8fd9f43ee2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="using-indexers-c-programming-guide"></a>Dizin Oluşturucular Kullanma (C# Programlama Kılavuzu)
Dizin oluşturucular oluşturmanıza olanak sağlayan bir söz dizimi kullanışlı olan bir [sınıfı](../../../csharp/language-reference/keywords/class.md), [yapısı](../../../csharp/language-reference/keywords/struct.md), veya [arabirimi](../../../csharp/language-reference/keywords/interface.md) istemci uygulamaları, bir dizi olarak erişebilir. Dizin oluşturucular en sık birincil amacı olan bir iç toplama veya dizi kapsülleyen türlerinde uygulanır. Örneğin, 24 saatlik bir dönemde 10 farklı saatlerinde kayıtlı olan Farenheit sıcaklık temsil eden TempRecord adlı bir sınıf olduğunu varsayalım. "Etme temsil etmek için temps" float türünde adlı bir dizi sınıf içerir ve bir <xref:System.DateTime> etme kaydedilen tarih temsil eder. Bu sınıf bir dizin oluşturucu uygulayarak istemcileri TempRecord örneğinde etme erişebilir `float temp = tr[4]` yerine olarak `float temp = tr.temps[4]`. Dizin Oluşturucu gösterimi yalnızca istemci uygulamaları için söz dizimi basitleştirir; Ayrıca sınıf ve amacı anlamak diğer geliştiriciler için daha sezgisel kılar.  
  
 Bir dizin oluşturucu bir sınıf veya yapı bildirmek için kullanın [bu](../../../csharp/language-reference/keywords/this.md) Bu örnekte olduğu gibi anahtar sözcüğü:  
  
```  
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir dizin oluşturucu türünü ve parametreleri türünü en az dizinleyici olarak erişilebilir olmalıdır. Erişilebilirlik düzeyleri hakkında daha fazla bilgi için bkz: [erişim değiştiricileri](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Dizin oluşturucular bir arabirim ile kullanma hakkında daha fazla bilgi için bkz: [arabirim Dizinleyicileri](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md).  
  
 Bir dizin oluşturucu imza sayısı ve türleri resmi parametrelerinden oluşur. Dizin Oluşturucu türü veya biçimsel parametresi adları içermez. Aynı sınıf içinde birden çok dizin oluşturucu bildirirseniz farklı imzalar olması gerekir.  
  
 Bir dizin oluşturucu değeri bir değişken olarak sınıflandırılmış değil; Bu nedenle, bir dizin oluşturucu değeri olarak geçiremezsiniz bir [ref](../../../csharp/language-reference/keywords/ref.md) veya [çıkışı](../../../csharp/language-reference/keywords/out.md) parametresi.  
  
 Dizin Oluşturucu, diğer diller kullanabileceği bir ad ile sağlamak için kullanın bir `name` öznitelik bildirimi. Örneğin:  
  
```  
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this [int index]   // Indexer declaration  
{  
}  
```  
  
 Bu dizin oluşturucu ada sahip olacaktır `TheItem`. Ad özniteliği sağlama değil olun `Item` varsayılan adı.  
  
## <a name="example-1"></a>Örnek 1  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, bir özel dizi alan bildirmek gösterilmiştir `temps`ve bir dizin oluşturucu. Dizin oluşturucu örneği doğrudan erişim sağlayan `tempRecord[i]`. Dizin Oluşturucu kullanarak alternatif bir dizi olarak bildirmektir bir [ortak](../../../csharp/language-reference/keywords/public.md) üye ve bu grubun üyeleri erişim `tempRecord.temps[i]`, doğrudan.  
  
 Bir oluşturucunun erişim, örneğin, içinde değerlendirmesinde dikkat bir `Console.Write` deyimi, [almak](../../../csharp/language-reference/keywords/get.md) erişimci çağrılır. Bu nedenle, yoksa `get` erişimci yoksa, bir derleme zamanı hatası oluşur.  
  
### <a name="code"></a>Kod  
 [!code-csharp[csProgGuideIndexers#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_1.cs)]  
  
## <a name="indexing-using-other-values"></a>Diğer değerleri kullanarak dizin oluşturma  
 C# dizin türü tamsayı sınırlamaz. Örneğin, bir dizeyi bir dizin oluşturucu ile kullanmak yararlı olabilir. Böyle bir dizin oluşturucu, koleksiyondaki dizesi için arama ve uygun değer döndürme uygulanabilir. Dize ve tamsayı sürümleri erişimciler aşırı olarak birlikte bulunabilir.  
  
## <a name="example-2"></a>Örnek 2  
  
### <a name="description"></a>Açıklama  
 Bu örnekte, bir sınıf haftanın günlerini depolar bildirildi. A `get` erişimci bildirilen bir gün adı bir dize alır ve karşılık gelen tamsayıyı döndürür. Örneğin, Pazar 0 döndürür, Pazartesi 1 dönmek ve benzeri.  
  
### <a name="code"></a>Kod  
 [!code-csharp[csProgGuideIndexers#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_2.cs)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 İçinde güvenlik ve dizin oluşturucular güvenilirliğini geliştirilebilir başlıca iki yolu vardır:  
  
-   Hata işleme stratejisi ' geçersiz dizin değeri geçirme istemci kodu olasılığını işlemek için bir tür eklemenizi emin olun. Bu konunun önceki kısımlarında ilk örnekte TempRecord sınıfı için dizin oluşturucu geçirmeden önce giriş doğrulamak istemci kodu sağlayan bir Length özelliği sağlar. Hata işleme kodunu dizinleyici içinde de yerleştirebilirsiniz. İçinde bir dizin oluşturucu erişimci throw tüm özel durumlar için kullanıcıların belgelediğinizden emin olun.  
  
-   Erişilebilirliğini ayarlamak `get` ve [ayarlamak](../../../csharp/language-reference/keywords/set.md) erişimciler şüphelenilebilir olabildiğince kısıtlayıcı olun. Bu önemlidir `set` belirli erişimci. Daha fazla bilgi için bkz: [erişimci erişilebilirliğini kısıtlama](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# programlama kılavuzu](../../../csharp/programming-guide/index.md)  
 [Dizin oluşturucular](../../../csharp/programming-guide/indexers/index.md)  
 [Özellikleri](../../../csharp/programming-guide/classes-and-structs/properties.md)
