---
title: "Windows Forms Denetimlerinde Özellik Tanımlama"
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
- properties [Windows Forms], defining in code
- custom controls [Windows Forms], defining properties in code
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8c3c25b9c408e5b8f0b76cdf87375875cdb06a13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="defining-a-property-in-windows-forms-controls"></a>Windows Forms Denetimlerinde Özellik Tanımlama
Özellikler genel bakış için bkz: [özelliklerine genel bakış](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52). Bir özellik tanımlarken birkaç önemli noktalar şunlardır:  
  
-   Tanımladığınız özellikleri öznitelikleri uygulamanız gerekir. Tasarımcı bir özelliğin nasıl görüntülenmelidir öznitelikleri belirtin. Ayrıntılar için bkz [bileşenleri için tasarım zamanı öznitelikleri](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3).  
  
-   Özellik değiştirme denetiminin görünümünü etkiliyorsa, çağrı <xref:System.Windows.Forms.Control.Invalidate%2A> yöntemi (denetiminizi devralan <xref:System.Windows.Forms.Control>) gelen `set` erişimcisi. <xref:System.Windows.Forms.Control.Invalidate%2A>sırayla çağırır <xref:System.Windows.Forms.Control.OnPaint%2A> denetimi yeniden çizer yöntemi. Birden çok çağrılar <xref:System.Windows.Forms.Control.Invalidate%2A> tek bir çağrı sonucunu <xref:System.Windows.Forms.Control.OnPaint%2A> verimlilik.  
  
-   .NET Framework sınıf kitaplığı, tamsayı, ondalık sayılar, Boole değerleri ve diğerleri gibi ortak veri türleri için tür dönüştürücüleri sağlar. Genellikle amacı tür dönüştürücüsü, dize değeri bir dönüştürme (dize verilerini diğer veri türleri için) sağlamaktır. Ortak veri türleri değerleri dizeler ve uygun veri türlerini dizelere dönüştürme varsayılan türü dönüştürücü ile ilişkilendirilmiş. Özel bir özellik tanımlarsanız (diğer bir deyişle, standart olmayan) veri türü olacaktır bu özellik ile ilişkilendirmek için tür dönüştürücüsünü belirten bir özniteliği uygulamak. Öznitelik, bir Özel UI türü Düzenleyici özelliği ile ilişkilendirmek için de kullanabilirsiniz. UI türü Düzenleyici bir özellik ya da veri türü düzenlemek için bir kullanıcı arabirimi sağlar. Bir renk seçici UI türü Düzenleyici örneğidir. Öznitelikleri örnekleri, bu konunun sonunda verilir.  
  
    > [!NOTE]
    >  Tür dönüştürücüsünü veya UI türü Düzenleyici özel özellik için kullanılabilir değilse, bir açıklandığı gibi uygulayabileceğiniz [genişletme tasarım zamanı desteği](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2).  
  
 Aşağıdaki kod parçası adlı özel bir özelliğini tanımlar `EndColor` özel denetim için `FlashTrackBar`.  
  
```vb  
Public Class FlashTrackBar  
   Inherits Control  
   ...  
   ' Private data member that backs the EndColor property.  
   Private _endColor As Color = Color.LimeGreen  
  
   ' The Category attribute tells the designer to display  
   ' it in the Flash grouping.   
   ' The Description attribute provides a description of  
   ' the property.   
   <Category("Flash"), _  
   Description("The ending color of the bar.")>  _  
   Public Property EndColor() As Color  
      ' The public property EndColor accesses _endColor.  
      Get  
         Return _endColor  
      End Get  
      Set  
         _endColor = value  
         If Not (baseBackground Is Nothing) And showGradient Then  
            baseBackground.Dispose()  
            baseBackground = Nothing  
         End If  
         ' The Invalidate method calls the OnPaint method, which redraws    
         ' the control.  
         Invalidate()  
      End Set  
   End Property  
   ...  
End Class  
```  
  
```csharp  
public class FlashTrackBar : Control {  
   ...  
   // Private data member that backs the EndColor property.  
   private Color endColor = Color.LimeGreen;  
   // The Category attribute tells the designer to display  
   // it in the Flash grouping.   
   // The Description attribute provides a description of  
   // the property.   
   [  
   Category("Flash"),  
   Description("The ending color of the bar.")  
   ]  
   // The public property EndColor accesses endColor.  
   public Color EndColor {  
      get {  
         return endColor;  
      }  
      set {  
         endColor = value;  
         if (baseBackground != null && showGradient) {  
            baseBackground.Dispose();  
            baseBackground = null;  
         }  
         // The Invalidate method calls the OnPaint method, which redraws   
         // the control.  
         Invalidate();  
      }  
   }  
   ...  
}  
```  
  
 Aşağıdaki kod parçası tür dönüştürücüsünü ve UI türü Düzenleyici özelliği ile ilişkilendiren `Value`. Bu durumda `Value` bir tamsayı ve bir varsayılan türü dönüştürücü sahip ancak <xref:System.ComponentModel.TypeConverterAttribute> özniteliği geçerli bir özel tür dönüştürücüsünü (`FlashTrackBarValueConverter`) yüzde olarak görüntülemek tasarımcı sağlar. UI türü düzenleyici `FlashTrackBarValueEditor`, görsel olarak görüntülenecek yüzdesini sağlar. Bu örnek ayrıca, tür dönüştürücüsünü veya Düzenleyicisi tarafından belirtilen gösterir <xref:System.ComponentModel.TypeConverterAttribute> veya <xref:System.ComponentModel.EditorAttribute> özniteliği varsayılan dönüştürücü geçersiz kılar.  
  
```vb  
<Category("Flash"), _  
TypeConverter(GetType(FlashTrackBarValueConverter)), _  
Editor(GetType(FlashTrackBarValueEditor), _  
GetType(UITypeEditor)), _  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")>  _  
Public ReadOnly Property Value() As Integer  
...  
End Property  
```  
  
```csharp  
[  
Category("Flash"),   
TypeConverter(typeof(FlashTrackBarValueConverter)),  
Editor(typeof(FlashTrackBarValueEditor), typeof(UITypeEditor)),  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")  
]  
public int Value {  
...  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Forms denetimlerindeki Özellikler](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [Reset yöntemleri ve ShouldSerialize ile varsayılan değerleri tanımlama](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 [Özellik değişti olayları](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 [Windows Forms denetimlerindeki öznitelikler](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)
