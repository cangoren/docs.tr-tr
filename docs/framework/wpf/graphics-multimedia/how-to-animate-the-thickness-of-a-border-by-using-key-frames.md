---
title: "Nasıl yapılır: Anahtar Çerçeveler Kullanarak Kenarlık Kalınlığına Animasyon Ekleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08950b2b92bfcbd28472327f12a2ee49abfd9fed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="d279a-102">Nasıl yapılır: Anahtar Çerçeveler Kullanarak Kenarlık Kalınlığına Animasyon Ekleme</span><span class="sxs-lookup"><span data-stu-id="d279a-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="d279a-103">Bu örnek animasyon gösterilmektedir <xref:System.Windows.Controls.Control.BorderThickness%2A> özelliği bir <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="d279a-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d279a-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="d279a-104">Example</span></span>  
 <span data-ttu-id="d279a-105">Aşağıdaki örnek kullanır <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> animasyon sınıfı <xref:System.Windows.Controls.Control.BorderThickness%2A> özelliği bir <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="d279a-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="d279a-106">Bu animasyon üç ana kare aşağıdaki şekilde kullanır:</span><span class="sxs-lookup"><span data-stu-id="d279a-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="d279a-107">Birinci yarım saniye boyunca bir örneğini kullanan <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> kenarlığın kalınlığı aşamalı olarak artırmak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="d279a-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="d279a-108">Örnek kullanır <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> değerler arasında yumuşak doğrusal bir artış oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="d279a-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2.  <span data-ttu-id="d279a-109">Sonraki sonunda yarım ikinci bir örneğini kullanır <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> aniden kenarlığın kalınlığı artırmak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="d279a-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="d279a-110">Bu gibi ayrık anahtar çerçeveler türetilen <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> değerler arasında ani atlar oluşturur, animasyonun hareketi düzensiz olur.</span><span class="sxs-lookup"><span data-stu-id="d279a-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3.  <span data-ttu-id="d279a-111">Son iki saniye boyunca bir örneğini kullanan <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> kenarlığın kalınlığı azaltmak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="d279a-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="d279a-112">Eğri anahtar çerçeveler olanlar gibi türetilen <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> değerlerine göre değerler arasında değişken geçiş oluşturmak <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="d279a-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="d279a-113">Bu anahtar çerçeve animasyon yavaş başlar ve zaman diliminin sonuna doğru katlanarak hızlanır.</span><span class="sxs-lookup"><span data-stu-id="d279a-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="d279a-114">Tam bir örnek için bkz: [ana kare animasyon örneği](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="d279a-114">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d279a-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d279a-115">See Also</span></span>  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>  
 [<span data-ttu-id="d279a-116">Anahtar çerçeve animasyonları genel bakış</span><span class="sxs-lookup"><span data-stu-id="d279a-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="d279a-117">Anahtar çerçeve nasıl yapılır konuları</span><span class="sxs-lookup"><span data-stu-id="d279a-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)  
 [<span data-ttu-id="d279a-118">BorderThickness değerini animasyon ekleme</span><span class="sxs-lookup"><span data-stu-id="d279a-118">Animate a BorderThickness Value</span></span>](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)