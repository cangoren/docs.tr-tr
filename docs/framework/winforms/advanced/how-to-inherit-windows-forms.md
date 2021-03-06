---
title: "Nasıl yapılır: Windows Formlarını Devralma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e986c79887ad19c77761b5ce134e4a3d68200d1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-windows-forms"></a>Nasıl yapılır: Windows Formlarını Devralma
Temel formlardan devralarak yeni Windows Forms oluşturma en iyi çabalarınız bunu gerektiren her zaman bir form tamamen yeniden sürecinde geçmeden çoğaltmak için kullanışlı bir yoludur.  
  
 Tasarım zamanı kullanarak form devralma hakkında daha fazla bilgi için **devralma Seçici** iletişim kutusu ve görsel olarak güvenlik düzeyleri arasında ayrım yapma devralınan denetimleri için bkz: [nasıl yapılır: formları kullanarak devral Devralma Seçici iletişim kutusu](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).  
  
 **Not** bir formdan devralmak için dosya veya ad alanı, formu içeren bir yürütülebilir dosya veya DLL'e oluşturulmuş olmalıdır. Projeyi oluşturmak için tercih **yapı** gelen **yapı** menüsü. Ayrıca, ad alanı referansı formun devralma sınıfı eklenmesi gerekir. Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-inherit-a-form-programmatically"></a>Bir form program aracılığıyla devralmak için  
  
1.  Sınıfınızda, devralınan istediğiniz formu içeren ad alanı için bir başvuru ekleyin.  
  
2.  Sınıf tanımında form devralmak için bir başvuru ekleyin. Başvuru noktayla, ardından taban formun adını ve ardından formu içeren ad alanı içermesi gerekir.  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 Forms devralırken her olay hem temel sınıfını hem de devralınan sınıfı tarafından işlenmediğinden oluşabilecek sorunları, iki kez çağrılan olay işleyicileri açısından göz önünde bulundurun. Bu sorunu önlemek nasıl daha fazla bilgi için bkz: [sorun giderme devralınmış olay işleyicileri Visual Basic'te](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Inherits deyimi](~/docs/visual-basic/language-reference/statements/inherits-statement.md)  
 [Imports deyimi (.NET Namespace ve türü)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [kullanma](~/docs/csharp/language-reference/keywords/using.md)  
 [Taban formun görünüşünü değiştirmenin etkileri](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)  
 [Windows Forms görsel devralma](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
