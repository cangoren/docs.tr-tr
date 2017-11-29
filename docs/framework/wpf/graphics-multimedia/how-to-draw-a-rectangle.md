---
title: "Nasıl yapılır: Dikdörtgen Çizme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c163897af27c9b34c8cd87a3b197047f86d21ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="b8d63-102">Nasıl yapılır: Dikdörtgen Çizme</span><span class="sxs-lookup"><span data-stu-id="b8d63-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="b8d63-103">Bu örnek kullanarak dikdörtgen çizmek nasıl gösterir <xref:System.Windows.Shapes.Rectangle> öğesi.</span><span class="sxs-lookup"><span data-stu-id="b8d63-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="b8d63-104">Dikdörtgen çizmek için oluşturma bir <xref:System.Windows.Shapes.Rectangle> öğesi ve kendi <xref:System.Windows.FrameworkElement.Width%2A> ve <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="b8d63-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="b8d63-105">Dikdörtgenin içini boyamak için ayarlanmış kendi <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="b8d63-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="b8d63-106">Dikdörtgene anahat vermek için kullanın, <xref:System.Windows.Shapes.Shape.Stroke%2A> ve <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="b8d63-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="b8d63-107">Yuvarlanmış köşeleri dikdörtgene vermek için isteğe bağlı belirtin <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> ve <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="b8d63-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="b8d63-108"><xref:System.Windows.Shapes.Rectangle.RadiusX%2A> Ve <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> özellikleri dikdörtgen köşelerinde yuvarlamak için kullanılan elipsin x ve y ekseni yarıçaplarını ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="b8d63-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="b8d63-109">Aşağıdaki örnekte, iki <xref:System.Windows.Shapes.Rectangle> öğeleri içinde çizilmiştir bir <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="b8d63-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="b8d63-110">İlk dikdörtgen sahip bir <xref:System.Windows.Media.Brushes.Blue%2A> iç.</span><span class="sxs-lookup"><span data-stu-id="b8d63-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="b8d63-111">İkinci dikdörtgeni sahip bir <xref:System.Windows.Media.Brushes.Blue%2A> iç, bir <xref:System.Windows.Media.Brushes.Black%2A> anahat ve yuvarlak köşeleri.</span><span class="sxs-lookup"><span data-stu-id="b8d63-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8d63-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="b8d63-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="b8d63-113">Bu örnek kullansa da bir <xref:System.Windows.Controls.Canvas> dikdörtgenler içermek için dikdörtgen öğelerini (ve diğer tüm şekil öğelerini) tüm kullanabilirsiniz <xref:System.Windows.Controls.Panel> veya <xref:System.Windows.Controls.Control> metin dışı içeriği destekler.</span><span class="sxs-lookup"><span data-stu-id="b8d63-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="b8d63-114">Aslında, dikdörtgenler bölümlerini için arka plan sağlamak için özellikle yararlıdır <xref:System.Windows.Controls.Grid> paneller.</span><span class="sxs-lookup"><span data-stu-id="b8d63-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="b8d63-115">Bir örnek için bkz: [tablo genel bakışı](../../../../docs/framework/wpf/advanced/table-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b8d63-115">For an example, see the [Table Overview](../../../../docs/framework/wpf/advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="b8d63-116">Bu örnek daha büyük bir örneğin parçasıdır; tam bir örnek için bkz: [şekil öğeleri örneği](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="b8d63-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d63-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b8d63-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Rectangle>  
 [<span data-ttu-id="b8d63-118">Şekil öğeleri örneği</span><span class="sxs-lookup"><span data-stu-id="b8d63-118">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [<span data-ttu-id="b8d63-119">Şekiller ve temel çizim WPF genel bakış</span><span class="sxs-lookup"><span data-stu-id="b8d63-119">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [<span data-ttu-id="b8d63-120">Tablo genel bakış</span><span class="sxs-lookup"><span data-stu-id="b8d63-120">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)