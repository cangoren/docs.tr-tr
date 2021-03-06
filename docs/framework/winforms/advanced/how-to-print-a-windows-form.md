---
title: "Nasıl yapılır: Bir Windows Formunu Yazdırma"
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
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9149b90317036c7c62c5fca3056bb697df56e543
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-print-a-windows-form"></a>Nasıl yapılır: Bir Windows Formunu Yazdırma
Geliştirme sürecinin bir parçası olarak, genellikle Windows formu bir kopyasını yazdırmak istersiniz. Aşağıdaki kod örneğinde geçerli formun bir kopyasını kullanarak yazdırma gösterilmektedir <xref:System.Drawing.Graphics.CopyFromScreen%2A> yöntemi.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu içeren bir tam bir kod örneğidir bir `Main` yöntemi.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Aşağıdaki koşullar özel bir duruma neden olabilir:  
  
-   Yazıcı erişim iznine sahip değil.  
  
-   Yazıcı yüklü değil.  
  
## <a name="net-framework-security"></a>.NET Framework Güvenliği  
 Bu kod örneği çalıştırmak için bilgisayarınızda kullandığınız yazıcıya erişim izni olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Nasıl yapılır: GDI + ile görüntü işleme](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)  
 [Nasıl yapılır: Windows Forms'ta grafik yazdırma](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
