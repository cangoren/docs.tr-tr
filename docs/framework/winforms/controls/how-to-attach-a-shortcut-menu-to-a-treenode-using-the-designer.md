---
title: "Nasıl yapılır: Tasarımcı Kullanarak bir TreeNode Öğesine Kısayol Menüsü Ekleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e1ec1b0236aab0f4ac61cb58d4fe006d17594e17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>Nasıl yapılır: Tasarımcı Kullanarak bir TreeNode Öğesine Kısayol Menüsü Ekleme
Windows Forms <xref:System.Windows.Forms.TreeView> denetimi düğümleri, Windows işletim sistemlerinde Windows Explorer özelliğinin sol bölmede görüntülenen klasörleri ve dosyaları benzer hiyerarşisini görüntüler. Ayarlayarak <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> özelliği sağlayabileceğiniz bağlama duyarlı işlemleri kullanıcıya bunlar sağ tıklattığınızda <xref:System.Windows.Forms.TreeView> denetim. İlişkilendirerek bir <xref:System.Windows.Forms.ContextMenuStrip> tek bileşeniyle <xref:System.Windows.Forms.TreeNode> öğeleri kısayol menüsünün işlevselliği için özelleştirilmiş bir düzeyini ekleyebilirsiniz, <xref:System.Windows.Forms.TreeView> kontrol eder.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>Bir kısayol menüsü tasarım zamanında bir TreeNode ile ilişkilendirmek için  
  
1.  Ekleme bir <xref:System.Windows.Forms.TreeView> formunuza denetlemek ve düğüm ekleme <xref:System.Windows.Forms.TreeView> gerektiğinde. Daha fazla bilgi için bkz: [nasıl yapılır: ekleme ve kaldırma Windows Forms TreeView denetimi ile düğüm](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).  
  
2.  Ekleme bir <xref:System.Windows.Forms.ContextMenuStrip> formun bileşeni ve çalışma zamanında kullanılabilir hale getirmek istediğiniz düğümü düzeyindeki işlemleri temsil kısayol menüsünün menü öğeleri ekleyin. Daha fazla bilgi için bkz: [nasıl yapılır: bir Contextmenustrip'ne menü öğeleri Ekle](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).  
  
3.  Yeniden **TreeNodeEditor** iletişim kutusu için <xref:System.Windows.Forms.TreeView> denetlemek, düzenlemek ve ayarlamak için düğümünü seçin, <xref:System.Windows.Forms.ContextMenuStrip> eklediğiniz kısayol menüsünün özelliğine.  
  
4.  Bu özelliği ayarlandığında düğümünü sağ tıklattığınızda kısayol menüsü görüntülenir.  
  
     Ayrıca, işlemek için kod yazma isteyeceksiniz <xref:System.Windows.Forms.ToolStripItem.Click> bu menü öğeleri için olaylar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [TreeView denetimi](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [TreeView denetimine genel bakış](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [ContextMenuStrip denetimi](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
