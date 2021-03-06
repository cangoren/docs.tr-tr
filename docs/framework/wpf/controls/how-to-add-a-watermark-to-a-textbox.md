---
title: "Nasıl yapılır: TextBox'a Filigran Ekleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4497b72f229a8f3d62ecb1829fda88ea3d76bbb0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a>Nasıl yapılır: TextBox'a Filigran Ekleme
Aşağıdaki örnek, kullanılabilirliğini yardımcı olmak gösterilmiştir bir <xref:System.Windows.Controls.TextBox> içinde açıklayıcı arka plan görüntüsü görüntüleyerek <xref:System.Windows.Controls.TextBox> metin kullanıcı girdi kadar bu noktada görüntü kaldırılır. Ayrıca, kullanıcının kendi giriş kaldırırsa arka plan resmini yeniden geri yüklendi. Aşağıdaki şekle bakın.  
  
 ![Arka plan resmi kutusuyla](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")  
  
> [!NOTE]
>  Arka plan resmi yerine sonra yalnızca düzenleme Bu örnekte kullanılan neden <xref:System.Windows.Controls.TextBox.Text%2A> özelliği <xref:System.Windows.Controls.TextBox>, arka plan görüntüsü ile veri bağlaması etkilemeyeceğini olduğu.  
  
## <a name="example"></a>Örnek  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [TextBox genel bakış](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox Genel Bakış](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
