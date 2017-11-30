---
title: Option Infer Deyimi
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
caps.latest.revision: "72"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4634c198b5fc41a4834cbd3cd96f9d3f1863d09b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="option-infer-statement"></a>Option Infer Deyimi
Değişkenleri bildirme içinde yerel türü çıkarımı kullanımını etkinleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a>Bölümler  
  
|Terim|Tanım|  
|---|---|  
|`On`|İsteğe bağlı. Yerel türü çıkarımı sağlar.|  
|`Off`|İsteğe bağlı. Yerel türü çıkarımı devre dışı bırakır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ayarlamak için `Option Infer` bir dosyaya yazın `Option Infer On` veya `Option Infer Off` önce başka bir kaynak kod dosyasının üst. Değeri ayarlarsanız `Option Infer` IDE veya komut satırında ayarlanan değer ile dosya çakışmalarını içinde dosyasındaki değer önceliğe sahiptir.  
  
 Ayarladığınızda `Option Infer` için `On`, açıkça bir veri türü bildirmeden yerel değişkenler bildirebilirsiniz. Derleyici, başlatma ifadesinin türünden bir değişken veri türü oluşturur.  
  
 Aşağıdaki çizimde, `Option Infer` açıktır. Değişken bildirimi `Dim someVar = 2` bir tamsayı olarak tür çıkarımı tarafından bildirilmedi.  
  
 ![Bildirim IntelliSense görünümü. ] (../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")  
Option Infer açık olduğunda IntelliSense  
  
 Aşağıdaki çizimde, `Option Infer` kapalıdır. Değişken bildirimi `Dim someVar = 2` olarak bildirilen bir `Object` tür çıkarımı tarafından. Bu örnekte, **Option Strict** ayar **kapalı** üzerinde [derleme sayfası, Proje Tasarımcısı (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
 ![Bildirim IntelliSense görünümü. ] (../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")  
Option Infer kapalı olduğunda IntelliSense  
  
> [!NOTE]
>  Ne zaman bir değişken bildirilen olarak bir `Object`, program çalışırken çalışma zamanı türünü değiştirebilirsiniz. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]adlı işlemleri gerçekleştirir *kutulama* ve *kutudan çıkarma* arasında dönüştürme için bir `Object` ve yürütme yavaş olmasını sağlayan bir değer türü. Kutulama ve kutudan çıkarma hakkında daha fazla bilgi için bkz: [Visual Basic dil belirtimi](../../../visual-basic/reference/language-specification/index.md).
  
 Tür çıkarımı yordamı düzeyinde uygulanır ve sınıf, yapı, modül veya arabirim yordam dışında geçerli değildir.  
  
 Ek bilgi için bkz: [yerel türü çıkarımı](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="when-an-option-infer-statement-is-not-present"></a>Bir Option Infer deyimi mevcut değil  
 Kaynak kodu içermiyorsa bir `Option Infer` deyimi, **Option Infer** ayarı [derleme sayfası, Proje Tasarımcısı (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) kullanılır. Komut satırı derleyicisi kullanılırsa, [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) derleyici seçeneği kullanılır.  
  
#### <a name="to-set-option-infer-in-the-ide"></a>Option Infer IDE'de ayarlamak için  
  
1.  İçinde **Çözüm Gezgini**, bir proje seçin. Üzerinde **proje** menüsünde tıklatın **özellikleri**. Daha fazla bilgi için bkz: [NIB: Proje özellikleriyle yönetme Proje Tasarımcısı](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  Tıklatın **derleme** sekmesi.  
  
3.  Değer kümesinde **Option Infer** kutusu.  
  
 Yeni bir proje oluşturduğunuzda **Option Infer** ayarı **derleme** sekmesinde ayarlanmış **Option Infer** ayarı **VB varsayılanlarını** iletişim kutusu. Erişim için **VB varsayılan olarak** iletişim kutusundaki **Araçları** menüsünde tıklatın **seçenekleri**. İçinde **seçenekleri** iletişim kutusunda, genişletin **projeler ve çözümler**ve ardından **VB varsayılanları**. İlk varsayılan ayarı **VB varsayılanları** olan `On`.  
  
#### <a name="to-set-option-infer-on-the-command-line"></a>Option Infer komut satırında ayarlamak için  
  
-   Dahil [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) derleyici seçeneği **vbc** komutu.  
  
## <a name="default-data-types-and-values"></a>Varsayılan veri türleri ve değerleri  
 Veri türü ve Başlatıcı belirtmenin çeşitli birleşimleri sonuçları aşağıdaki tabloda açıklanmaktadır bir `Dim` deyimi.  
  
|Belirtilen veri türü?|Belirtilen başlatıcı?|Örnek|Sonuç|  
|---|---|---|---|  
|Hayır|Hayır|`Dim qty`|Varsa `Option Strict` olan kapalı (varsayılan), değişkenini ayarlamak `Nothing`.<br /><br /> Varsa `Option Strict` olduğundan, bir derleme zamanı hatası oluşur.|  
|Hayır|Evet|`Dim qty = 5`|Varsa `Option Infer` Başlatıcı değişken alır veri türü (varsayılan), olduğunda. Bkz: [yerel türü çıkarımı](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Varsa `Option Infer` kapalıdır ve `Option Strict` kapalıysa, değişken veri türü alır `Object`.<br /><br /> Varsa `Option Infer` kapalıdır ve `Option Strict` olduğundan, bir derleme zamanı hatası oluşur.|  
|Evet|Hayır|`Dim qty As Integer`|Değişken veri türü için varsayılan değer için başlatılır. Daha fazla bilgi için bkz: [Dim deyimi](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Evet|Evet|`Dim qty  As Integer = 5`|Başlatıcı'veri türü belirtilen veri türüne dönüştürülebilir değilse, bir derleme zamanı hatası oluşur.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler göstermektedir nasıl `Option Infer` ifade yerel türü çıkarımı etkinleştirir.  
  
 [!code-vb[VbVbalrTypeInference#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir değişken olarak tanımlandığında, çalışma zamanı türü farklı olduğunu gösterir. bir `Object`.  
  
 [!code-vb[VbVbalrTypeInference#11](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dim deyimi](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Yerel tür çıkarımı](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Compare deyimi](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Option Explicit deyimi](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Option Strict deyimi](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Visual Basic Varsayılanları, projeler, Seçenekler iletişim kutusu](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [/ optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [Kutulama ve kutudan çıkarma](../../../csharp/programming-guide/types/boxing-and-unboxing.md)