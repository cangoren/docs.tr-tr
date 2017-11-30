---
title: "Nasıl yapılır: Tasarımcı Kullanarak Windows Formları Denetimi Tarafından Görüntülenen Resmi Ayarlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
- setting images [Windows Forms], Windows Forms controls
ms.assetid: ae80d07a-e469-4251-90ca-df71f5852454
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eee3c8c3f3890054e443f6246b8fa43fd2ef09b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="7ee08-102">Nasıl yapılır: Tasarımcı Kullanarak Windows Formları Denetimi Tarafından Görüntülenen Resmi Ayarlama</span><span class="sxs-lookup"><span data-stu-id="7ee08-102">How to: Set the Image Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="7ee08-103">Çeşitli Windows Forms denetimleri görüntüleri görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7ee08-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="7ee08-104">Görüntü denetimi belirten düğmesi üzerinde bir disk simgesi gibi amacı kavuşturuldu simge olabilir **kaydetmek** komutu.</span><span class="sxs-lookup"><span data-stu-id="7ee08-104">The image can be an icon that clarifies the purpose of the control, such as a disk icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="7ee08-105">Alternatif olarak, simge denetimi istediğiniz görünümü vermek için bir arka plan görüntüsü olabilir.</span><span class="sxs-lookup"><span data-stu-id="7ee08-105">Alternatively, the icon can be a background image to give the control the appearance you want.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ee08-106">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="7ee08-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7ee08-107">Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="7ee08-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7ee08-108">Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="7ee08-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="7ee08-109">Bir denetimi tarafından görüntülenen resmi ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="7ee08-109">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="7ee08-110">İçinde **özellikleri** penceresinde, seçin **görüntü** veya **BackgroundImage** denetiminin özelliği üç nokta düğmesini ('ı</span><span class="sxs-lookup"><span data-stu-id="7ee08-110">In the **Properties** window, select the **Image** or **BackgroundImage** property of the control, then click the ellipsis button (</span></span>  
  
     <span data-ttu-id="7ee08-111">![VisualStudioEllipsesButton ekran](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")</span><span class="sxs-lookup"><span data-stu-id="7ee08-111">![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")</span></span>  
  
     <span data-ttu-id="7ee08-112">) görüntülemek için **Select Resource** iletişim kutusu.</span><span class="sxs-lookup"><span data-stu-id="7ee08-112">) to display the **Select Resource** dialog box.</span></span>  
  
2.  <span data-ttu-id="7ee08-113">Görüntülemek istediğiniz görüntüyü seçin.</span><span class="sxs-lookup"><span data-stu-id="7ee08-113">Select the image you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee08-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7ee08-114">See Also</span></span>  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [<span data-ttu-id="7ee08-115">Ayrı Windows Forms denetimlerini etiketleme ve kısayollarını sunma</span><span class="sxs-lookup"><span data-stu-id="7ee08-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)