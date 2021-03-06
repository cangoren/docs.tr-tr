---
title: "İzleme ve İletileri Günlüğe Kaydetme için Önerilen Ayarlar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1894ee59b6120abfe4cb216baba086fcd1650f77
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a>İzleme ve İletileri Günlüğe Kaydetme için Önerilen Ayarlar
Bu konu, önerilen izleme ve farklı işletim ortamlar için ileti günlüğe kaydetme ayarlarını açıklar.  
  
## <a name="recommended-settings-for-a-production-environment"></a>Bir üretim ortamı için önerilen ayarları  
 WCF izleme kaynakları kullanıyorsanız, bir üretim ortamı için ayarlanmış `switchValue` uyarı. WCF kullanıyorsanız `System.ServiceModel` izleme kaynağı, Ayarla `switchValue` özniteliğini `Warning` ve `propagateActivity` özniteliğini `true`. Kullanıcı tanımlı izleme kaynağı kullanıyorsanız, ayarlamak `switchValue` özniteliğini `Warning, ActivityTracing`. Bu kullanarak el ile yapılabilir [Yapılandırma Aracı (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md). İsabet performans düşündüğünüz değil, ayarlayabileceğiniz `switchValue` özniteliğini `Information` tüm yukarıda açıklanan durumlarda, hangi oluşturur, izleme verilerinin oldukça büyük bir miktarını. Aşağıdaki örnek, bu önerilen ayarları gösterir.  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a>Dağıtım veya hata ayıklama için önerilen ayarları  
 Dağıtım veya hata ayıklama ortamı için seçin `Information` veya `Verbose`, birlikte `ActivityTracing` ya da bir kullanıcı tarafından tanımlanan için veya `System.ServiceModel` izleme kaynağı. Hata ayıklama geliştirmek için de bir ek izleme kaynağı eklemeniz gerekir (`System.ServiceModel.MessageLogging`) ileti günlüğe kaydetmeyi etkinleştirmek için yapılandırma. Dikkat `switchValue` özniteliği bu izleme kaynağı üzerinde hiçbir etkisi vardır.  
  
 Önerilen ayarları kullanan paylaşılan bir dinleyici kullanarak, aşağıdaki örnekte gösterilmiştir `XmlWriterTraceListener`.  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"   
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a>Ayarları değiştirmek için WMI kullanma  
 Çalışma zamanında yapılandırma ayarlarını değiştirmek için WMI kullanabilirsiniz (etkinleştirerek `wmiProviderEnabled` şekilde yapılandırmasında özniteliği daha önce yapılandırma örneği). Örneğin, WMI CIM Studio içinde izleme kaynağı düzeyleri uyarıdan bilgileri çalışma zamanında değiştirmek için kullanabilirsiniz. Bu şekilde dinamik hata ayıklama performans maliyeti oldukça yüksek olabilir bilmeniz gerekir. WMI kullanma hakkında daha fazla bilgi için bkz: [tanılama için Windows Yönetim araçları kullanarak](../../../../../docs/framework/wcf/diagnostics/wmi/index.md) konu.  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a>ASP.NET izleme, bağıntılı olaylar etkinleştir  
 ASP.NET olay izleme etkinleştirilmemişse ASP.NET olayları bağıntı kimliği (ActivityID) ayarlamayın. ASP.NET olaylarına açmak zorunda bağıntılı olaylar düzgün şekilde görmek için komut konsolunda şu komutu kullanarak izleme, hangi çağrılabilir giderek **Başlat**, **çalıştırmak** ve türü **cmd** ,  
  
```  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 ASP.NET olayları izlemeyi devre dışı bırakmak için aşağıdaki komutu kullanın,  
  
```  
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tanılama için Windows Yönetim Araçları'nı kullanma](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)
