---
title: "UI Otomasyon İstemcileri İçin Denetim Düzeni Eşleştirmesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
caps.latest.revision: "18"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 31beb7ab9a978f5bb379a3c1d61c90c19c26ca6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>UI Otomasyon İstemcileri İçin Denetim Düzeni Eşleştirmesi
> [!NOTE]
>  Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı. Hakkında en yeni bilgiler için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Otomasyon API: UI Otomasyonu](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Bu konu, denetim türlerini ve bunların ilişkili denetim düzenleri listeler.  
  
 Aşağıdaki tabloda denetim desenleri aşağıdaki kategorilere göre düzenler:  
  
-   Desteklenen. Denetim bu denetim düzeni desteklemesi gerekir.  
  
-   Koşullu desteği. Denetim denetimin durum bilgisinin bağlı olarak bu denetim düzeni destekleyebilir.  
  
-   Desteklenmez. Bu denetim düzeni denetimi desteklemiyor; özel denetimler bu denetim düzeni destekleyebilir.  
  
> [!NOTE]
>  Bazı denetimler koşullu denetim işlevselliğini bağlı olarak birkaç denetim düzenleri desteği vardır. Örneğin, menü öğesi denetim koşullu desteği olan <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>, veya <xref:System.Windows.Automation.SelectionItemPattern> menü denetimi kendi işlevinde bağlı olarak denetim düzeni.  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a>İstemciler İçin UI Otomasyon Denetim Düzenleri  
  
|Denetim türü|Desteklenir|Koşullu desteği|Desteklenmez|  
|------------------|---------------|-------------------------|-------------------|  
|Düğme|Yok.|Çağırma, Değiştir, daraltma genişletme|Yok.|  
|Takvim|Kılavuz, tablo|Seçimi, kaydırma|Değer|  
|Onay kutusu|İki Durumlu Düğme|Yok.|Yok.|  
|Birleşik Giriş Kutusu|Daraltma genişletme|Seçimi, değer|Kaydırma|  
|Veri Kılavuzu|Kılavuz|Kaydırma, seçim, tablo|Yok.|  
|Veri Öğesi|Seçim Öğesi|Daraltma, kılavuz öğesi, kaydırma öğesi, tablo, geçiş, değer genişletin|Yok.|  
|Belge|Metin|Kaydırma, değer|Yok.|  
|Düzenle|Yok.|Aralık değeri, bir metin değeri|Yok.|  
|Grup|Yok.|Daraltma genişletme|Yok.|  
|Üstbilgi|Yok.|Dönüştürme|Yok.|  
|Üstbilgi Öğesi|Yok.|Dönüştürme, çağırma|Yok.|  
|Köprü|Çağır|Değer|Yok.|  
|Görüntü|Yok.|Kılavuz öğesi, Tablo öğesi|Çağırma, seçim öğesi|  
|List|Yok.|Kılavuz, birden çok görünüm kaydırma, seçimi|Tablo|  
|Liste öğesi|Seçim Öğesi|Daraltma, kılavuz öğesi genişletme çağırma, öğeyi kaydırma geçiş, değer|Yok.|  
|Menü|Yok.|Yok.|Yok.|  
|Menü Çubuğu|Yok.|Daraltma, yerleştirme, dönüştürme genişletin|Yok.|  
|Menü Öğesi|Yok.|Daraltma genişletme, iki durumlu seçim öğesi çağırma|Yok.|  
|Bölme|Yok.|Yerleştirme. Kaydırma, dönüştürme|Pencere|  
|İlerleme Çubuğu|Yok.|Aralık değeri|Yok.|  
|Radyo Düğmesi|Seçim Öğesi|Yok.|İki Durumlu Düğme|  
|Kaydırma Çubuğu|Yok.|Aralık Değeri|Kaydırma|  
|Ayırıcı|Yok.|Yok.|Yok.|  
|Kaydırıcı|Yok.|Aralık değeri, seçim, değeri|Yok.|  
|Değer Değiştirici|Yok.|Aralık değeri, seçim, değeri|Yok.|  
|Bölünmüş Düğme|Çağırma, daraltma genişletme|Yok.|Yok.|  
|Durum Çubuğu|Yok.|Kılavuz|Yok.|  
|Tab|Seçim|Kaydırma|Yok.|  
|Sekme Öğesi|Seçim Öğesi|Yok.|Çağır|  
|Tablo|Kılavuz, kılavuz öğesi ', tablo, Tablo öğesi|Yok.|Yok.|  
|Metin|Yok.|Kılavuz öğesi, Tablo öğesi metni|Değer|  
|Parmak|Dönüştürme|Yok.|Yok.|  
|Başlık Çubuğu|Yok.|Yok.|Yok.|  
|Araç çubuğu|Yok.|Yerleştirme, daraltma, genişletme dönüştürme|Yok.|  
|Araç İpucu|Yok.|Metin, penceresi|Yok.|  
|Ağaç|Yok.|Kaydırma, seçimi|Yok.|  
|Ağaç Öğesi|Daraltma genişletme|Seçim öğesi, iki durumlu kaydırma öğesi çağırma|Yok.|  
|Pencere|Dönüştürme, penceresi|Yerleştirme|Yok.|  
  
> [!NOTE]
>  Denetim türü listelenen herhangi bir desteklenen denetim desen sahiptir ancak bu koşullu denetim düzenleri birini hiç desteklenecek sonra bir veya daha fazla koşullu desteklenen denetim düzenleri varsa zaman.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [UI Otomasyon genel bakış](../../../docs/framework/ui-automation/ui-automation-overview.md)
