---
title: "Nasıl yapılır: Yineleme Döngüsü Sırasında Animasyon Değerlerini Biriktirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4abe19f4548ed41eb19ae4dffb37b832a7df71d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>Nasıl yapılır: Yineleme Döngüsü Sırasında Animasyon Değerlerini Biriktirme
Bu örnek nasıl kullanılacağını gösterir <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Yinelenen döngüler arasında animasyon değerlerini birikmesine özelliği.  
  
## <a name="example"></a>Örnek  
 Kullanım <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Yinelenen döngüler arasında bir animasyonun temel değerlerini birikmesine özelliği. Örneğin, bir animasyon 9 kez yinelenmesi ayarlarsanız (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9 x") ve 10-15 arasında animasyon için özelliğini ayarlayın (= 10 = 15), özelliği 10-15'ten 20 ikinci döngü sırasında ilk döngü sırasında 15'e canlandırır , üçüncü döngü vb. sırasında 25 20. Bu nedenle, her animasyon döngüsünün önceki animasyon döngüsünün bitiş animasyon değerden temel değer olarak kullanır.  
  
 Kullanabileceğiniz `IsCumulative` en temel animasyonları ve çoğu anahtar çerçeve animasyonları özelliği. Daha fazla bilgi için bkz: [animasyon genel bakış](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) ve [anahtar çerçeve animasyonları genel bakış](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 Aşağıdaki örnek, dört dikdörtgenin genişliği animasyon tarafından bu davranış gösterir. Örnek:  
  
-   İlk dikdörtgen canlandırır <xref:System.Windows.Media.Animation.DoubleAnimation> ve ayarlar <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> özelliğine `true`.  
  
-   İkinci dikdörtgen canlandırır <xref:System.Windows.Media.Animation.DoubleAnimation> ve ayarlar <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> varsayılan değerini özelliğine `false`.  
  
-   Üçüncü dikdörtgen canlandırır <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> ve ayarlar <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> özelliğine `true`.  
  
-   Son dikdörtgen canlandırır <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> ve ayarlar <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> özelliğine `false`.  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Animasyon çıkış değeri başlangıç değeri bir animasyon ekleme](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)  
 [Animasyonu yineleyin](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)  
 [Animasyon genel bakış](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Anahtar çerçeve animasyonları genel bakış](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Nasıl Yapılır Konuları](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
