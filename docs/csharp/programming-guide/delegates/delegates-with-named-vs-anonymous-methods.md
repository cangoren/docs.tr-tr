---
title: "Temsilciler adlandırılmış vs ile. Anonim Yöntemler (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 59317ad3cd9a5d360d0375bf46ff0c9f752a5944
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a>Temsilciler adlandırılmış vs ile. Anonim Yöntemler (C# Programlama Kılavuzu)
A [temsilci](../../../csharp/language-reference/keywords/delegate.md) adlandırılmış bir yöntem ile ilişkili olabilir. Adlandırılmış bir yöntemi kullanarak bir temsilci örneği, yöntemi bir parametre örneğin geçirilir:  
  
 [!code-csharp[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]  
  
 Bu, adlandırılmış bir yöntem kullanılarak çağrılır. Adlandırılmış bir yöntemle oluşturulan temsilcileri ya da kapsülleyen bir [statik](../../../csharp/language-reference/keywords/static.md) yöntemi veya örnek yöntemi. Adlandırılmış yöntemleri bir temsilci önceki sürümlerinde, C# örneği oluşturmak için tek yoludur. Ancak, yeni bir yöntem oluşturma ek yükü istenmeyen olduğu bir durumda, C#, bir temsilci örneği ve onu çağrıldığında, temsilci işleyecek kod bloğu hemen belirtmenize olanak sağlar. Blok lambda ifadesi ya da anonim yöntemi içerebilir. Daha fazla bilgi için bkz: [anonim işlevler](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Temsilci parametre olarak geçirmek yöntemi temsilci bildirimi olarak aynı imzaya sahip olmalıdır.  
  
 Bir temsilci örneği ya da statik kapsülleyen veya yöntemi örneği olabilir.  
  
 Temsilci kullanabilirsiniz ancak bir [çıkışı](../../../csharp/language-reference/keywords/out.md) parametresi önerilmez kullanımı ile çok noktaya yayın olay temsilcileri hangi temsilcinin çağrılacağı bilemezsiniz olduğundan.  
  
## <a name="example-1"></a>Örnek 1  
 Bildirme ve bir temsilci kullanarak basit bir örnek verilmiştir. Dikkat hem temsilci `Del`ve ilişkili yöntemi `MultiplyNumbers`, aynı imzaya sahip  
  
 [!code-csharp[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]  
  
## <a name="example-2"></a>Örnek 2  
 Aşağıdaki örnekte, bir temsilci hem de statik olarak eşlenmiş ve örneği her belirli bilgiler yöntemleri ve döndürür.  
  
 [!code-csharp[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# programlama kılavuzu](../../../csharp/programming-guide/index.md)  
 [Temsilciler](../../../csharp/programming-guide/delegates/index.md)  
 [Anonim yöntemler](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
 [Nasıl yapılır: temsilcileri (çok noktaya yayın temsilcileri) birleştirme](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
 [Olayları](../../../csharp/programming-guide/events/index.md)
