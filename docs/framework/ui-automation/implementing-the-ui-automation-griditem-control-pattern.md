---
title: "UI Otomasyon GridItem Denetim Düzeni Uygulama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
caps.latest.revision: "15"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: daaffd02eaaf7fcb0e64dbcda4bd2ee155163f4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a>UI Otomasyon GridItem Denetim Düzeni Uygulama
> [!NOTE]
>  Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı. Hakkında en yeni bilgiler için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Otomasyon API: UI Otomasyonu](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Bu konu kılavuzları ve uygulamak için kuralları tanıtır <xref:System.Windows.Automation.Provider.IGridItemProvider>, özellikler hakkında bilgiler dahil olmak üzere. Ek başvurular bağlantılar genel bakış sonunda listelenmiştir.  
  
 <xref:System.Windows.Automation.GridItemPattern> Denetim düzeni tek tek alt denetimler uygulamak kapsayıcıların desteklemek için kullanılan <xref:System.Windows.Automation.Provider.IGridProvider>. Bu denetim düzeni uygulama denetimleri örnekleri için bkz: [denetim düzeni eşleştirmesi UI Otomasyon istemcileri için](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Uygulama rehberi ve kuralları  
 Uygularken <xref:System.Windows.Automation.Provider.IGridProvider>, aşağıdaki yönergeleri ve kuralları dikkat edin:  
  
-   Kılavuz koordinatları koordinatları (0, 0) sahip üst sol hücre sıfır tabanlı.  
  
-   Birleştirilmiş hücreler bildirir kendi <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> ve <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> özelliklerine bağlı bunların temel bağlantı hücrede UI Otomasyon sağlayıcı tarafından tanımlandığı şekilde. Genellikle, en üstteki ve en soldaki satır veya sütun olacaktır.  
  
-   <xref:System.Windows.Automation.Provider.IGridItemProvider>birleştirme veya hücreleri bölme gibi kılavuzunun etkin işleme için sağlamaz.  
  
-   Denetimleri uygulayan <xref:System.Windows.Automation.Provider.IGridItemProvider> genellikle geçiş (diğer bir deyişle, UI Otomasyonu istemci bitişik denetimlere taşıyabilirsiniz) klavyeyi kullanarak.  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a>Gerekli üyeleri IGridItemProvider için  
 Aşağıdaki özellikleri ve yöntemleri uygulamak için gerekli olan <xref:System.Windows.Automation.Provider.IGridItemProvider>.  
  
|Gerekli üyeleri|Üye türü|Notlar|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|Özellik|Yok.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|Özellik|Yok.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|Özellik|Yok.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|Özellik|Yok.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|Özellik|Yok.|  
  
 Bu denetim düzeni ilişkili yöntemleri ya da olaylar vardır.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Özel Durumlar  
 Bu denetim düzeni ilişkili hiçbir özel durum vardır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [UI Otomasyon denetim düzenlerine genel bakış](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [UI Otomasyon sağlayıcısında denetim düzenleri desteği](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [İstemciler için UI Otomasyon denetim düzenleri](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [UI Otomasyon kılavuz denetim düzenini uygulama](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [UI Otomasyon ağacına genel bakış](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [UI otomasyonda önbelleğe almayı kullanma](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
