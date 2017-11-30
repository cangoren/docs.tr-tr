---
title: "Nasıl yapılır: Küçük Resimler Oluşturma"
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
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2a3866274340932819a419c622c10072dd67c439
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="2a76a-102">Nasıl yapılır: Küçük Resimler Oluşturma</span><span class="sxs-lookup"><span data-stu-id="2a76a-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="2a76a-103">Küçük resim, görüntünün küçük bir sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="2a76a-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="2a76a-104">Küçük resim çağırarak oluşturabileceğiniz <xref:System.Drawing.Image.GetThumbnailImage%2A> yöntemi bir <xref:System.Drawing.Image> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="2a76a-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a76a-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="2a76a-105">Example</span></span>  
 <span data-ttu-id="2a76a-106">Aşağıdaki örnek oluşturan bir <xref:System.Drawing.Image> JPG dosyadan nesne.</span><span class="sxs-lookup"><span data-stu-id="2a76a-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="2a76a-107">Özgün görüntüsüne 640 piksel genişliği ve yüksekliği 479 piksel sahiptir.</span><span class="sxs-lookup"><span data-stu-id="2a76a-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="2a76a-108">Kod 100 piksel genişliği ve yüksekliği, 100 piksel olan bir küçük resim oluşturur.</span><span class="sxs-lookup"><span data-stu-id="2a76a-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="2a76a-109">Aşağıdaki çizim, küçük resim göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="2a76a-109">The following illustration shows the thumbnail image.</span></span>  
  
 <span data-ttu-id="2a76a-110">![Küçük resim](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")</span><span class="sxs-lookup"><span data-stu-id="2a76a-110">![Thumbnail Image](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a76a-111">Bu örnekte, bir geri çağırma yöntemi bildirildi, ancak hiç kullanılmadı.</span><span class="sxs-lookup"><span data-stu-id="2a76a-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="2a76a-112">GDI +'in tüm sürümleri destekler.</span><span class="sxs-lookup"><span data-stu-id="2a76a-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2a76a-113">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="2a76a-113">Compiling the Code</span></span>  
 <span data-ttu-id="2a76a-114">Önceki örnekte Windows Forms ile kullanılmak üzere tasarlanmış ve gerektirip <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olarak olduğu <xref:System.Windows.Forms.Control.Paint> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="2a76a-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="2a76a-115">Örneği çalıştırmak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="2a76a-115">To run the example, follow these steps:</span></span>  
  
1.  <span data-ttu-id="2a76a-116">Yeni bir Windows Forms uygulaması oluşturma.</span><span class="sxs-lookup"><span data-stu-id="2a76a-116">Create a new Windows Forms application.</span></span>  
  
2.  <span data-ttu-id="2a76a-117">Örnek kod forma ekleyin.</span><span class="sxs-lookup"><span data-stu-id="2a76a-117">Add the example code to the form.</span></span>  
  
3.  <span data-ttu-id="2a76a-118">Form için bir işleyici oluşturmak <xref:System.Windows.Forms.Control.Paint> olayı</span><span class="sxs-lookup"><span data-stu-id="2a76a-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4.  <span data-ttu-id="2a76a-119">İçinde <xref:System.Windows.Forms.Control.Paint> işleyici, çağrı `GetThumbnail` yöntemi ve geçişi `e` için <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="2a76a-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5.  <span data-ttu-id="2a76a-120">Küçük resmini yapmak istediğiniz bir görüntü dosyasını bulun.</span><span class="sxs-lookup"><span data-stu-id="2a76a-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6.  <span data-ttu-id="2a76a-121">İçinde `GetThumbnail` yöntemi yolunu belirtin ve dosya adı görüntünüze.</span><span class="sxs-lookup"><span data-stu-id="2a76a-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7.  <span data-ttu-id="2a76a-122">Örneği çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="2a76a-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="2a76a-123">100'e 100 küçük resim formda görünür.</span><span class="sxs-lookup"><span data-stu-id="2a76a-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a76a-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2a76a-124">See Also</span></span>  
 [<span data-ttu-id="2a76a-125">Resimler, bit eşlemler ve meta dosyaları</span><span class="sxs-lookup"><span data-stu-id="2a76a-125">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="2a76a-126">Resimler, bit eşlemler, simgeler ve meta dosyaları ile çalışma</span><span class="sxs-lookup"><span data-stu-id="2a76a-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)