---
title: "Nasıl yapılır: Arabelleğe Alınan Grafikleri Elle Yönetme"
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
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 678b9ad5e8f9b40f927a35e98973cabc831c5cf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manually-manage-buffered-graphics"></a>Nasıl yapılır: Arabelleğe Alınan Grafikleri Elle Yönetme
Daha gelişmiş çift arabelleğe alma senaryoları için kullandığınız [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] kendi çift arabelleğe alma mantığını uygulamak için sınıflar. Ayırma ve tek tek grafik arabellekleri yönetme sorumlu sınıfı <xref:System.Drawing.BufferedGraphicsContext> sınıfı. Her uygulamanın kendi varsayılan var. <xref:System.Drawing.BufferedGraphicsContext> , yöneten tüm bu uygulama için arabelleğe alma çift varsayılan. Çağırarak bu örneğine başvuru alabilir <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>BufferedGraphicsContext varsayılan bir başvuru almak için  
  
-   Ayarlama <xref:System.Drawing.BufferedGraphicsManager.Current%2A> aşağıdaki kod örneğinde gösterildiği gibi özelliği.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  Çağrı gerekmez `Dispose` yöntemi <xref:System.Drawing.BufferedGraphicsContext> , alırsınız başvuru <xref:System.Drawing.BufferedGraphicsManager> sınıfı. <xref:System.Drawing.BufferedGraphicsManager> Tüm bellek ayırma ve dağıtım için varsayılan işleme <xref:System.Drawing.BufferedGraphicsContext> örnekleri.  
  
     Animasyon gibi grafik açısından yoğun uygulamalar için bazen bir adanmış kullanarak performansı artırabilir <xref:System.Drawing.BufferedGraphicsContext> yerine <xref:System.Drawing.BufferedGraphicsContext> tarafından sağlanan <xref:System.Drawing.BufferedGraphicsManager>. Bu, oluşturma ve uygulama tarafından kullanılan bellek büyük olmaz ancak, uygulama ile ilişkili tüm diğer arabelleğe alınan grafikleri yönetme performans yükünü yansıtılmasını olmadan grafik arabellekleri ayrı ayrı yönetmenize olanak sağlar.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>Ayrılmış BufferedGraphicsContext oluşturmak için  
  
-   Bildirme ve yeni bir örneğini oluşturmak <xref:System.Drawing.BufferedGraphicsContext> aşağıdaki kod örneğinde gösterildiği gibi sınıfı.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Drawing.BufferedGraphicsContext>  
 [Çift arabelleğe alınan grafikleri](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [Nasıl yapılır: arabelleğe alınan grafikleri elle işleme](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)
