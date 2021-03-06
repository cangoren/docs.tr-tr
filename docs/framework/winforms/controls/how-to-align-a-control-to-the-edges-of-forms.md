---
title: "Nasıl yapılır: Denetimi Formların Kenarlarına Hizalama"
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
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a55212ac4d770848355ace1b0ef3fff3cc50f871
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a>Nasıl yapılır: Denetimi Formların Kenarlarına Hizalama
Formlarınızı için ayarlayarak hizalar denetiminizi yapabileceğiniz <xref:System.Windows.Forms.Control.Dock%2A> özelliği. Bu özellik, Denetim biçiminde bulunduğu belirler. <xref:System.Windows.Forms.Control.Dock%2A> Özelliği aşağıdaki değerlere ayarlanabilir:  
  
|Ayar|Denetim etkisi|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|Formun altına noktaları.|  
|<xref:System.Windows.Forms.DockStyle.Fill>|Formdaki tüm kalan alanı doldurur.|  
|<xref:System.Windows.Forms.DockStyle.Left>|Formun sol tarafına noktaları.|  
|<xref:System.Windows.Forms.DockStyle.None>|Yoksa her yerden ve onu görünen tarafından belirtilen konumda yerleştirme kendi <xref:System.Windows.Forms.Control.Location%2A> özelliği.|  
|<xref:System.Windows.Forms.DockStyle.Right>|Formun sağ tarafındaki noktaları.|  
|<xref:System.Windows.Forms.DockStyle.Top>|Formun üstüne noktaları.|  
  
 Bu özellik Visual Studio tasarım-zamanı desteği yoktur.  
  
### <a name="to-set-the-dock-property-for-your-control-at-run-time"></a>Çalışma zamanında denetiminizi Dock özelliğini ayarlamak için  
  
1.  Ayarlama <xref:System.Windows.Forms.Control.Dock%2A> özelliğini uygun değere kod.  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>  
 [Özel Windows Forms denetimleri .NET Framework ile geliştirme](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Nasıl yapılır: FlowLayoutPanel denetiminde alt denetimleri sabitleme ve yerleştirme](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [Nasıl yapılır: TableLayoutPanel denetiminde alt denetimleri sabitleme ve yerleştirme](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [AutoSize özelliğine genel bakış](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
