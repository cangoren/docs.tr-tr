---
title: Yineleyici (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Iterator
helpviewer_keywords: Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 503d586c0515b4cb53f8ec5656e5fe765cc094a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iterator-visual-basic"></a>Yineleyici (Visual Basic)
Belirleyen bir işlevi veya `Get` erişimci yineleyici olduğu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir *yineleyici* özel bir yineleme içinde bir koleksiyon gerçekleştirir. Yineleyici kullanan [verim](../../../visual-basic/language-reference/statements/yield-statement.md) deyimi koleksiyondaki bir birer birer her öğesini döndürür. Zaman bir `Yield` deyimi ulaşıldığında, kod geçerli konumda korunur. Yürütme, yineleyici işlevinin bir sonraki çağrılmasında bu konumdan başlar.  
  
 Yineleyici bir işlevi veya olarak uygulanabileceği bir `Get` özelliği tanımı erişimcisi. `Iterator` Değiştiricisi görünür yineleyici işlevi bildiriminde veya `Get` erişimcisi.  
  
 Yineleyici kullanarak istemci kodundan çağıran bir [For Each... Sonraki deyim](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Bir yineleyici işlevinin dönüş türü veya `Get` erişimci olabilir <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, veya <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Yineleyici içeremez `ByRef` parametreleri.  
  
 Yineleyici bir olay, örnek oluşturucusu, statik Oluşturucusu veya statik yıkıcı gerçekleşemez.  
  
 Yineleyici adsız bir işlev olabilir. Daha fazla bilgi için bkz: [yineleyiciler](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
 Yineleyiciler hakkında daha fazla bilgi için bkz: [yineleyiciler](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="usage"></a>Kullanım  
 `Iterator` Değiştiricisi bu bağlamlarında kullanılabilir:  
  
-   [Function deyimi](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property deyimi](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir yineleyici işlevi gösterir. Yineleyici işlevinin bir `Yield` içinde deyimi bir [için... Sonraki](../../../visual-basic/language-reference/statements/for-next-statement.md) döngü. Her yinelemesinden [her](../../../visual-basic/language-reference/statements/for-each-next-statement.md) deyiminin gövdesinde `Main` yapılan bir çağrı oluşturur `Power` yineleyici işlevi. Yineleyici işlevi her çağrısı devam eder, sonraki yürütülmesi `Yield` sonraki yinelemesini sırasında oluşur deyimi `For…Next` döngü.  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterilmiştir bir `Get` yineleyici olduğu erişimcisi. `Iterator` Değiştirici özelliği bildiriminde olduğu.  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 Ek örnekler için bkz: [yineleyiciler](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [Yineleyiciler](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [Yield deyimi](../../../visual-basic/language-reference/statements/yield-statement.md)
