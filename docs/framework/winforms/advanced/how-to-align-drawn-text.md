---
title: "Nasıl yapılır: Çizilmiş Metni Hizalama"
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
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a2f2f6bd088ad58277839cf7e32a98d67ca3bd15
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-align-drawn-text"></a>Nasıl yapılır: Çizilmiş Metni Hizalama
Özel çizim gerçekleştirdiğinizde, genellikle bir form veya denetim çizilmiş metni ortalamak isteyebilirsiniz. Kolayca ile çizilmiş metni hizalama <xref:System.Drawing.Graphics.DrawString%2A> veya <xref:System.Windows.Forms.TextRenderer.DrawText%2A> doğru biçimlendirme nesnesi oluşturma ve uygun biçimde bayrakları ayarlayarak yöntemleri.  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>Ortalanmış metin GDI + (DrawString) ile çizmek için  
  
1.  Kullanım bir <xref:System.Drawing.StringFormat> uygun ile <xref:System.Drawing.Graphics.DrawString%2A> yöntemi ortalanmış metni belirtin.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>Ortalanmış (DrawText) GDI ile metin çizmek için  
  
1.  Kullanım <xref:System.Windows.Forms.TextFormatFlags> kaydırma yanı sıra dikey ve yatay olarak uygun metinle ortalama için numaralandırma <xref:System.Windows.Forms.TextRenderer.DrawText%2A> yöntemi.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Önceki kod örnekleri Windows Forms ile kullanılmak üzere tasarlanmıştır ve ihtiyaç <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olarak olduğu <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: GDI ile metin çizme](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [Yazı tipleri ve metin kullanma](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Nasıl yapılır: yazı tipi aileleri ve yazı tipleri](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
