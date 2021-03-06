---
title: "Azaltma: ZipArchiveEntry.FullName yol ayırıcısı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36af59772418f5622d411f9df843f5dcd296be13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a>Azaltma: ZipArchiveEntry.FullName yol ayırıcısı
Hedefleyen uygulamalar ile başlayan [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], kullanılan yol ayırıcısı <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> özelliği, ters eğik çizgi değişti ("\\") bir eğik çizgi ("/") için .NET Framework'ün önceki sürümlerinde kullanılan.   <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType>nesneler aşırı birini çağırarak oluşturulur <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType> yöntemi.  
  
## <a name="impact"></a>Etki  
 Değişiklik 4.4.17.1 bölümüne ile uygunluk .NET uygulamasına getirir [. ZIP dosyası biçim belirtimi](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) ve sağlar. Windows olmayan sistemlerde açılması için ZIP arşivler.  
  
 Dizin yapısı korumak için .NET Framework Windows olmayan işletim sistemlerinde Macintosh gibi önceki bir sürümünü başarısız hedefleyen bir uygulama tarafından oluşturulan bir zip dosyası açılıyor. Örneğin, dosya, dosya adı, dizin yolu bir eğik çizgi ile birlikte art arda ekler kümesi oluşturur Macintosh ("\\") karakterleri ve dosya adı. Sonuç olarak, açılan sıkıştırılmış dosyaların dizin yapısını korunmaz.  
  
 Bu değişiklik etkisi. .NET Framework API'leri tarafından Windows işletim sistemi sıkıştırması ZIP dosyaları <xref:System.IO> bu API'leri bir eğik çizgi ("/") veya ters eğik çizgi sorunsuz bir şekilde işleyebilir beri ad alanı en az olmalıdır ("\\") yol ayırıcı karakter olarak.  
  
## <a name="mitigation"></a>Azaltma  
 Bu davranış istenmeyen ise, dışında bir yapılandırma ayarı ekleyerek seçebilirsiniz [ \<çalışma zamanı >](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) uygulama yapılandırma dosyasının. Aşağıdaki her ikisi de gösterir `<runtime>` bölümü ve vazgeçme anahtar.  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 Buna ek olarak, .NET Framework'ün önceki sürümlerini hedefleyen ancak üzerinde çalışan uygulamalar [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ve sonraki sürümler kabul etme Bu davranışı için bir yapılandırma ayarı ekleyerek [ \<çalışma zamanı >](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) bölümü Uygulama yapılandırma dosyası. Aşağıdaki her ikisi de gösterir `<runtime>` bölümü ve katılımı anahtar.  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yeniden hedefleme değişiklikleri](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)  
 [4.6.1 uygulama uyumluluğu](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
