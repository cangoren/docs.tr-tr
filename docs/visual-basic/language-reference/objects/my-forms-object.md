---
title: My.Forms Nesnesi
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords: My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a5aa7af1f07a29660335d968c1ecc17be5f8beec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="myforms-object"></a>My.Forms Nesnesi
Geçerli projede bildirilen her Windows formunu örneği erişmek için özellikleri sağlar.  
  
## <a name="remarks"></a>Açıklamalar  
 `My.Forms` Nesnesi, geçerli projedeki her form örneği sağlar. Özelliğin adı özelliği erişen formun adı ile aynıdır. Bir projeye form ekleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: Windows Forms projeye eklemek](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
 Tarafından sağlanan formların erişebilir `My.Forms` niteliğe olmadan formun adını kullanarak nesne. Özellik adı formun tür adıyla aynı olduğundan, bu varsayılan bir örnek sahipmiş gibi bir form erişmenize olanak tanır. Örneğin, `My.Forms.Form1.Show` eşdeğerdir `Form1.Show`.  
  
 `My.Forms` Nesne yalnızca geçerli projeyle ilişkili formları kullanıma sunar. Başvurulan DLL'lerde bildirilen formlara erişim sağlamaz. DLL sağlayan form erişmek için tam olarak yazılmış formun adını kullanın *dll*. *Formadı*.  
  
 Kullanabileceğiniz <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> uygulamanın tüm açık form koleksiyonu alınacağı özellik.  
  
 Nesne ve özellikleri yalnızca Windows uygulamaları için kullanılabilir.  
  
## <a name="properties"></a>Özellikler  
 Her bir özelliğinin `My.Forms` nesne geçerli projedeki form örneğine erişim sağlar. Özelliğin adı özelliği erişen formun adı ile aynıdır ve özellik türü formun türü ile aynıdır.  
  
> [!NOTE]
>  Bir ad çakışması varsa, bir form erişmek için özellik adı olan *RootNamespace*_*Namespace*\_*formadı*. Örneğin, iki tür adlı göz önünde bulundurun `Form1.`şu biçimlerden birini kök ad alanını olup olmadığını `WindowsApplication1` ve ad alanında `Namespace1`, bu formu üzerinden erişir `My.Forms.WindowsApplication1_Namespace1_Form1`.  
  
 `My.Forms` Nesnesini başlatma sırasında oluşturuldu uygulamanın ana form örneğine erişim sağlar. Diğer tüm formların `My.Forms` nesnesi erişilir ve depolar, formun yeni bir örneğini oluşturur. Bu özelliğe erişmek için sonraki denemeler formun örneğini döndürür.  
  
 Atayarak biçimi dispose `Nothing` oluşturan özelliğine. Özellik ayarlayıcı çağrıları <xref:System.Windows.Forms.Form.Close%2A> yöntemi form ve ardından atar `Nothing` depolanan değer. Herhangi bir değer dışındaki atarsanız `Nothing` özelliğine kurucu oluşturur bir <xref:System.ArgumentException> özel durum.  
  
 Bir özelliği olup olmadığını sınayabilirsiniz `My.Forms` nesnesini kullanarak form örneğini depolar `Is` veya `IsNot` işleci. Özelliğinin değeri olup olmadığını denetlemek için bu işleçleri kullanabilirsiniz `Nothing`.  
  
> [!NOTE]
>  Genellikle, `Is` veya `IsNot` sahip karşılaştırma yapabilmesi için özellik değeri okunamıyor. Ancak, özelliği şu anda depoluyorsa `Nothing`, özelliğin formun yeni bir örneğini oluşturur ve o örneği döndürür. Ancak, Visual Basic derleyici özelliklerini değerlendirir `My.Forms` farklı nesne ve verir `Is` veya `IsNot` değerini değiştirmeden özelliği durumunu denetlemek için işleci.  
  
## <a name="example"></a>Örnek  
 Bu örnek varsayılan başlık değiştirir `SidebarMenu` formu.  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 Çalışmak bu örnek için projenize adlı bir form olmalıdır `SidebarMenu`. Daha fazla bilgi için bkz: [nasıl yapılır: Windows Forms projeye eklemek](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
 Bu kod, yalnızca bir Windows uygulaması proje ile çalışır.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="availability-by-project-type"></a>Proje Türüne Göre Kullanılabilirlik  
  
|Proje türü|Kullanılabilir|  
|---|---|  
|Windows uygulaması|**Evet**|  
|Sınıf Kitaplığı|Hayır|  
|Konsol Uygulaması|Hayır|  
|Windows Denetim Kitaplığı|Hayır|  
|Web Denetim Kitaplığı|Hayır|  
|Windows Hizmeti|Hayır|  
|Web Sitesi|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [Nesneleri](../../../visual-basic/language-reference/objects/index.md)  
 [Nasıl yapılır: Windows Forms için bir proje ekleyin](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1)  
 [Is işleci](../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot işleci](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Uygulama formlarına erişme](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
