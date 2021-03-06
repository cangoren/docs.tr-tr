---
title: "Nasıl yapılır: Denetim Sınıfından Devralma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 75b9c56d2d9df80745cec2b811c39f5e438d07c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-from-the-control-class"></a>Nasıl yapılır: Denetim Sınıfından Devralma
Bir Windows formunda kullanmak için tamamen özel bir denetim oluşturmak istiyorsanız, gelen alması gerektiğini <xref:System.Windows.Forms.Control> sınıfı. İçinden devralma sırasında <xref:System.Windows.Forms.Control> sınıfı gerektirir daha fazla planlama ve uygulama gerçekleştirmek, ayrıca, en büyük çeşitli seçenekler ile sağlar. İçinden devralma zaman <xref:System.Windows.Forms.Control>, iş denetimleri yapar çok temel işlevleri devralır. Ndaki işlevselliği <xref:System.Windows.Forms.Control> sınıfı klavye ve fare kullanıcı girişini işleme, denetimin boyutunu ve sınırlarını tanımlar, bir windows tanıtıcı sağlar ve ileti işleme ve güvenlik sağlar. Bu durumda grafik arabiriminin denetiminin gerçek işleme olduğu, tüm boyama dahil değildir ve herhangi belirli kullanıcı etkileşimi işlevselliği dahil etmez. Tüm özel kod aracılığıyla bu yönlerinin sağlamanız gerekir.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-custom-control"></a>Özel bir denetim oluşturmak için  
  
1.  Yeni bir **Windows uygulaması** veya **Windows Denetim Kitaplığı** projesi.  
  
2.  Gelen **proje** menüsünde seçin **sınıfı Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusu, tıklatın **özel denetimi**.  
  
     Yeni bir özel denetim projenize eklenir.  
  
4.  Basın açmak için F7 **Kod düzenleyicisinde** özel denetim için.  
  
5.  Bulun <xref:System.Windows.Forms.Control.OnPaint%2A> yapılan bir çağrı dışında boş olur yöntemi <xref:System.Windows.Forms.Control.OnPaint%2A> yöntemi temel sınıf.  
  
6.  Kodu denetimi için istediğiniz herhangi bir özel boyama içerecek şekilde değiştirin.  
  
     Grafik denetimleri için işlemek için kod yazma hakkında daha fazla bilgi için bkz: [özel denetim boyama ve işleme](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
7.  Tüm özel yöntemler, özellikler veya denetiminizi dahil olayların uygulayın.  
  
8.  Kaydet ve denetiminizin sınayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel denetim çeşitleri](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [Nasıl yapılır: UserControl sınıfından devralma](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [Nasıl yapılır: mevcut Windows Formları denetimlerinden devralma](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [Nasıl yapılır: Windows formları için denetimler yazma](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [Devralınmış olay işleyicileri Visual Basic sorunlarını giderme](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [Windows Forms denetimleri geliştirme tasarım zamanında](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
