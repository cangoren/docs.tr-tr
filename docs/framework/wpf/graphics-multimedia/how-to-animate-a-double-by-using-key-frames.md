---
title: "Nasıl yapılır: Anahtar Çerçeveler Kullanarak bir Çifte Animasyon Ekleme"
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
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c4ec6554ee024450e397ee7757649be7537eaae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>Nasıl yapılır: Anahtar Çerçeveler Kullanarak bir Çifte Animasyon Ekleme
Bu örnek götüren bir özelliğin değerini animasyon gösterilmektedir bir <xref:System.Double> anahtar çerçeveler kullanarak.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir dikdörtgen ekran boyunca taşır. Örnek kullanır <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> animasyon sınıfı <xref:System.Windows.Media.TranslateTransform.X%2A> özelliği bir <xref:System.Windows.Media.TranslateTransform> uygulanan bir <xref:System.Windows.Shapes.Rectangle>. Süresiz olarak yinelenen Bu animasyon üç ana kare aşağıdaki şekilde kullanır:  
  
1.  İlk üç saniye boyunca bir örneğini kullanan <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> dikdörtgeni yol boyunca bir hızda başlangıç konumundan 500 konumuna taşımak için sınıf. Gibi doğrusal anahtar çerçeveler <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> değerler arasında yumuşak bir doğrusal geçiş oluşturur.  
  
2.  Dördüncü saniye sonunda bir örneğini kullanan <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> dikdörtgeni sonraki konumuna aniden taşımak için sınıf. Gibi ayrık anahtar çerçeveler <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> değerler arasında ani atlar oluşturun. Bu örnekte, dikdörtgen başlangıç konumunda ve aniden 500 konumunda görünür.  
  
3.  Son iki saniye içinde bir örneğini kullanan <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> dikdörtgeni başlangıç konumuna geri taşımak için sınıf. Gibi Eğri anahtar çerçeveler <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> değerini göre değerler arasında değişken geçiş oluşturmak <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> özelliği. Bu örnekte, dikdörtgen yavaş taşıyarak başlar ve ardından katlanarak zaman diliminin sonuna doğru hızlanır.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Tam bir örnek için bkz: [ana kare animasyon örneği](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Diğer animasyon örnekleriyle tutarlılık için bu örnek kodu sürümlerini kullanan bir <xref:System.Windows.Media.Animation.Storyboard> uygulanacak nesne <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>. Alternatif olarak, kodda tek bir animasyonu uygularken, bunu kullanmak daha basittir <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> kullanmak yerine yöntemi bir <xref:System.Windows.Media.Animation.Storyboard>. Bir örnek için bkz: [özelliği olmadan kullanarak bir film şeridi animasyon](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Shapes.Rectangle>  
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>  
 [Anahtar çerçeve animasyonları genel bakış](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Anahtar çerçeve nasıl yapılır konuları](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
