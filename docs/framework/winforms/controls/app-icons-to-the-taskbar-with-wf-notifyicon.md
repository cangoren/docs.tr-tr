---
title: "Nasıl yapılır: Windows Forms NotifyIcon Bileşeniyle TaskBar'na Uygulama Simgeleri Ekleme"
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
- cpp
f1_keywords: TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 97c31998885926e9a7372bcf3182d1c95f0b79d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a>Nasıl yapılır: Windows Forms NotifyIcon Bileşeniyle TaskBar'na Uygulama Simgeleri Ekleme
Windows Forms <xref:System.Windows.Forms.NotifyIcon> bileşen durumu görev çubuğu bildirim alanında tek bir simge görüntüler. Durum alanında birden çok simgeleri göstermek için birden çok sahip <xref:System.Windows.Forms.NotifyIcon> formunuzda bileşenleri. Bir denetim için görüntülenen simge ayarlamak için kullanın <xref:System.Windows.Forms.NotifyIcon.Icon%2A> özelliği. Ayrıca kod yazabilirsiniz <xref:System.Windows.Forms.NotifyIcon.DoubleClick> kullanıcı simgesine tıkladığında bu bir şey için olay işleyicisi. Örneğin, bir iletişim kutusu kullanıcının simgesi tarafından temsil edilen arka plan işlemi yapılandırmak görünür hale getirebilir.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.NotifyIcon> Bileşeni bir eylem veya olay oluştu uyarı kullanıcılara yalnızca, bildirim amacıyla kullanılan veya bazı sıralama durumu değişikliği oluştu. Menüleri, araç çubukları ve diğer kullanıcı arabirimi öğeleri uygulamalarla standart etkileşim için kullanmanız gerekir.  
  
### <a name="to-set-the-icon"></a>Simge ayarlamak için  
  
1.  Bir değer atadığınız <xref:System.Windows.Forms.NotifyIcon.Icon%2A> özelliği. Değer türü olmalıdır `System.Drawing.Icon` ve bir .ico dosyadan yüklenemiyor. Simge dosyası kodunda ya da üç nokta düğmesini tıklatarak belirtebilirsiniz (![VisualStudioEllipsesButton ekran](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) yanındaki <xref:System.Windows.Forms.NotifyIcon.Icon%2A> özelliğinde  **Özellikler** penceresi ve sonra dosyayı seçerek **açık** görüntülenen iletişim kutusunda.  
  
2.  Ayarlama <xref:System.Windows.Forms.NotifyIcon.Visible%2A> özelliğine `true`.  
  
3.  Ayarlama <xref:System.Windows.Forms.NotifyIcon.Text%2A> uygun bir araç ipucu dizesi özelliğine.  
  
     Aşağıdaki kod örneğinde yolunu ayarlama simgenin konumunu için **Belgelerim** klasör. Windows işletim sistemi çalıştıran bilgisayarların çoğu bu klasör içerdiğini varsayar çünkü bu konumu kullanılır. Bu konumu seçme, güvenli bir şekilde uygulamayı çalıştırmak minimum sistem erişim düzeyleri kullanıcılarla sağlar. Aşağıdaki örnek bir formla gerektiren bir <xref:System.Windows.Forms.NotifyIcon> denetimi zaten eklendi. Adlı bir simge dosyası da gerektirir `Icon.ico`.  
  
    ```vb  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
    ```  
  
    ```csharp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    notifyIcon1.Icon =   
       new System.Drawing.Icon (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Icon.ico");  
    notifyIcon1.Visible = true;  
    notifyIcon1.Text = "Antivirus program";  
    ```  
  
    ```cpp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    notifyIcon1->Icon = gcnew   
       System::Drawing::Icon(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Icon.ico"));  
    notifyIcon1->Visible = true;  
    notifyIcon1->Text = "Antivirus program";  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [Nasıl yapılır: bir kısayol menüsünü Windows Forms Notifyıcon bileşeniyle ilişkilendirme](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)  
 [Notifyıcon bileşeni](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [Notifyıcon bileşenine genel bakış](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
