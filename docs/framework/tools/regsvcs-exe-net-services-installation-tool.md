---
title: "Regsvcs.exe (.NET Hizmetleri Yükleme Aracı)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ddd937ec891f5e00410b74fffd152e23431652f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="regsvcsexe-net-services-installation-tool"></a>Regsvcs.exe (.NET Hizmetleri Yükleme Aracı)
.NET Hizmetleri Yükleme aracı aşağıdaki eylemleri gerçekleştirir:  
  
-   Bir derlemeyi yükler ve kaydeder.  
  
-   Bir tür kitaplığı üretir, kaydeder ve belirtilen bir COM+ uygulamasına yükler.  
  
-   Sınıfınıza program aracılığıyla eklediğiniz hizmetleri yapılandırır.  
  
 Aracı çalıştırmak için, Geliştirici Komut İstemi (veya Windows 7'de Visual Studio Komut İstemi) kullanın. Daha fazla bilgi için bkz: [komut istemlerini](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Komut satırına şunu yazın:  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll   
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Bağımsız Değişken|Açıklama|  
|--------------|-----------------|  
|*assemblyFile.dll*|Kaynak derleme dosyası. Derlemenin tanımlayıcı ad ile imzalanması gerekir. Daha fazla bilgi için bkz: [bir derlemeyi tanımlayıcı adla imzalama](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).|  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**/appdir:** *yolu*|Uygulamanın kök dizinini belirtir.|  
|**Appname:** *applicationName*|Bulunacak veya oluşturulacak COM+ uygulamasının adını belirtir.|  
|**/c**|Hedef uygulamayı oluşturur.|  
|**/ componly**|Yalnızca bileşenleri yapılandırır; yöntemleri ve arabirimleri yoksayar.|  
|**/exapp**|Varolan bir uygulamayı beklemek üzere aracı belirtir.|  
|**/extlb**|Varolan bir tür kitaplığını kullanır.|  
|**/FC**|Hedef uygulamayı bulur veya oluşturur.|  
|**/ Help**|Araç için komut sözdizimini ve seçenekleri görüntüler.|  
|**/noreconfig**|Varolan bir hedef uygulamayı yeniden yapılandırmaz.|  
|**/ nologo**|Microsoft başlangıç başlığı görüntüsünü bastırır.|  
|**/parname:** *adı*|Bulunacak veya oluşturulacak COM+ uygulamasının adını veya kimliğini belirtir.|  
|**/reconfig**|Varolan bir hedef uygulamayı yeniden yapılandırır. Bu varsayılandır.|  
|**TLB:** *typelibraryfile*|Yüklenecek tür kitaplığı dosyasını belirtir.|  
|**/u**|Hedef uygulamayı kaldırır.|  
|**istemci bilgisayarlara**|Sessiz modu belirtir; logo ve başarı iletisi görüntüsünü bastırır.|  
|**/?**|Araç için komut sözdizimini ve seçenekleri görüntüler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Regsvcs.exe tarafından belirtilen kaynak derleme dosyası gerektirir *assemblyFile.dll*. Bu derlemenin tanımlayıcı ad ile imzalanması gerekir. Güçlü ad imzalama hakkında daha fazla bilgi için bkz: [bir derlemeyi tanımlayıcı adla imzalama](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md). Hedef uygulamanın ve tür kitaplığı dosyasının adları isteğe bağlıdır. *ApplicationName* bağımsız değişkeni kaynak derleme dosyasından oluşturulabilir ve Regsvcs.exe tarafından zaten yoksa, oluşturulur. *Typelibraryfile* bağımsız değişkeni bir tür kitaplığı adı belirtebilirsiniz. Bir tür kitaplığı adı belirtmezseniz, Regsvcs.exe derleme adını varsayılan olarak kullanır.  
  
 Regsvcs.exe bir bileşenin yöntemleri kaydettiğinde tabi olan [taleplerini](http://msdn.microsoft.com/en-us/e5283e28-2366-4519-b27d-ef5c1ddc1f48) ve [bağlantı talepleri](../../../docs/framework/misc/link-demands.md) bu yöntemleri. Araç tam olarak güvenilen bir ortamda yürütüldüğünden, izin taleplerinin çoğu başarılı olur. Ancak, Regsvcs.exe bileşenleri için isteğe bağlı veya bağlantı bir istek tarafından korunan yöntemleriyle kaydı yapılamıyor <xref:System.Security.Permissions.StrongNameIdentityPermission> veya <xref:System.Security.Permissions.PublisherIdentityPermission>.  
  
 Regsvcs.exe'yi kullanmak için yerel bilgisayarda yönetici ayrıcalıklarına sahip olmanız gerekir.  
  
 Bu eylemlerden herhangi birini gerçekleştirirken Regsvcs.exe başarısız olursa, ilgili hata iletilerini görüntüler.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki komut içinde yer alan tüm ortak sınıflar ekler `myTest.dll` için `myTargetApp` (bir var olan COM + uygulaması) ve üretir `myTest.tlb` tür kitaplığı.  
  
```  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 Aşağıdaki komut içinde yer alan tüm ortak sınıflar ekler `myTest.dll` için `myTargetApp` (bir var olan COM + uygulaması) ve üretir `newTest.tlb` tür kitaplığı.  
  
```  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araçları](../../../docs/framework/tools/index.md)  
 [Nasıl yapılır: bir derlemeyi tanımlayıcı adla imzalama](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [Komut istemleri](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
