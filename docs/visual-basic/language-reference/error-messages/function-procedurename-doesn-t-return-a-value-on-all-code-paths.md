---
title: "İşlev &#39; &lt;procedurename&gt;&#39; belirlemeden #39; tüm kod yolları bir değer döndürmesi t"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords: BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5244d97a79f2450f44fe05f63510369914375912
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>İşlev &#39; &lt;procedurename&gt;&#39; belirlemeden #39; tüm kod yolları bir değer döndürmesi t
İşlev '\<procedurename >' tüm kod yolları bir değer döndürmüyor. 'Return' deyimi eksik olabilir mi?  
  
 A `Function` yordamının bir değer döndürmüyor kendi kod aracılığıyla en az bir olası yolu vardır.  
  
 Bir değer almak bir `Function` aşağıdaki yollardan birini yordamda:  
  
-   Değer içeren bir [dönüş deyimi](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Değer atadığınız `Function` yordamı adlandırın ve ardından gerçekleştirmek bir `Exit Function` deyimi.  
  
-   Değer atadığınız `Function` yordamı adlandırın ve ardından gerçekleştirmek `End Function` deyimi.  
  
 Denetim geçirir, `Exit Function` veya `End Function` ve yordam adı herhangi bir değer atamadıysanız, yordamı dönüş verisi türüne varsayılan değerini döndürür. Daha fazla bilgi için bkz: "Davranışı" [Function deyimi](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Varsayılan olarak, bu iletiyi bir uyarıdır. Uyarıları gizleme veya uyarıları hata olarak davranma daha fazla bilgi için bkz: [yapılandırma uyarılarını Visual Basic'te](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Hata Kimliği:** BC42105  
  
## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Denetim akışı mantığınızı denetleyin ve satır başı neden olan her deyimi önce bir değer atadığınız emin olun.  
  
     Her zaman kullanıyorsanız her return yordamdan bir değer döndürür güvence altına almak daha kolay `Return` deyimi. Bu, son deyim önce yaparsanız `End Function` olması gereken bir `Return` deyimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev yordamları](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [Function deyimi](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Derle sayfası, Proje Tasarımcısı (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
