---
title: "Nasıl yapılır: Bir Windows Formunda Basit Bağlantılı Denetim Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b95892641000287f57840ec57cd65147b986829
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a>Nasıl yapılır: Bir Windows Formunda Basit Bağlantılı Denetim Oluşturma
İle *basit bağlama*, tek bir veri öğesi, bir veri kümesi tablodaki bir sütun değeri gibi bir denetimi görüntüleme. Basit bir denetim herhangi bir özelliği bir veri değerine Bağ.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-simple-bind-a-control"></a>Basit-Denetim bağlamak için  
  
1.  Bir veri kaynağına bağlanın. Daha fazla bilgi için bkz: [bir veri kaynağına bağlanma](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  Form denetimi seçin ve görüntüleme **özellikleri** penceresi.  
  
3.  Genişletme **(veri bağlamaları)** özelliği.  
  
     En sık bağlı özellikleri altında görüntülenir **(veri bağlamaları)** özelliği. Örneğin, çoğu denetimleri içinde **metin** özelliği en sık bağlı.  
  
4.  Özelliği, istiyorsanız bağlama yaygın olarak bağlanmış özelliklerin biri değil,'ı tıklatın **üç nokta** düğmesi (![VisualStudioEllipsesButton ekran](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton") ) içinde **(Gelişmiş)** görüntülemek için kutusunu **biçimlendirme ve Gelişmiş bağlama** bu denetim için özelliklerin tam bir listesi ile iletişim kutusu.  
  
5.  Altında aşağı açılan okunu tıklatıp bağlamak istediğiniz özelliği seçin **bağlama**.  
  
     Kullanılabilir veri kaynaklarının listesi görüntülenir.  
  
6.  İstediğiniz tek bir veri öğesi bulana kadar bağlamak istediğiniz veri kaynağı'nı genişletin. Örneğin, bir veri kümesi'nin tablodaki bir sütun değerine bağlanıyorsanız, veri kümesinin adını genişletin ve ardından sütun adlarını görüntülemek için tablo adını genişletin.  
  
7.  Bağlanacak bir öğenin adına tıklayın.  
  
8.  Çalışmakta olduğunuz varsa **biçimlendirme ve Gelişmiş bağlama** iletişim kutusu, tıklatın **Tamam** geri dönmek için **özellikleri** penceresi.  
  
9. Denetimin ek özellikler bağlamak istiyorsanız, 3 ile 7 arasındaki adımları yineleyin.  
  
    > [!NOTE]
    >  Yalnızca tek bir veri öğesi basit-bağlama denetimleri göstermek için bir Windows formunda basit bağlantılı denetimleri ile gezinti mantığı dahil çok normaldir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.Binding>  
 [Windows Forms veri bağlama](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Veri bağlama ve Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
