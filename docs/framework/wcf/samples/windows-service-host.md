---
title: "Windows Hizmet Konağı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- NT Service
- NT Service Host Sample [Windows Communication Foundation]
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
caps.latest.revision: "40"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e3dd2b4880ea61f5c3236a3e15ba1c939dbc2952
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="windows-service-host"></a>Windows Hizmet Konağı
Bu örnek gösteren bir [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] yönetilen bir Windows hizmetinde barındırılan hizmeti. Windows Hizmetleri, hizmetler uygulamasını kullanarak denetlenir **Denetim Masası** ve bir sistem yeniden başlatıldıktan sonra otomatik olarak başlatılmasını yapılandırılabilir. Örnek, bir istemci programını ve bir Windows hizmeti programı oluşur. Hizmet bir .exe programı olarak uygulanır ve kendi barındırma kodunu içerir. Windows İşlem Etkinleştirme Hizmetleri (WAS) veya Internet Information Services (IIS) gibi diğer barındırma ortamlarında yazmak için ise gerekli değildir kod barındırma.  
  
> [!NOTE]
>  Kurulum yordam ve yapılandırma yönergeleri Bu örneği için bu konunun sonunda yer alır.  
  
> [!IMPORTANT]
>  Örnekler, bilgisayarınızda yüklü. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 Bu hizmet oluşturduktan sonra bu diğer herhangi bir Windows hizmeti gibi Installutil.exe yardımcı programı ile yüklenmesi gerekir. Hizmetinde değişiklik yapmak istiyorsanız, öncelikle ile kaldırmalısınız `installutil /u`. Bu örnekte dahil Setup.bat ve Cleanup.bat dosyalarını yükleme ve Windows hizmeti, başlangıç ve kapatmak ve Windows hizmeti kaldırmak için komutlardır. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmeti yalnızca yanıt verebilmesini istemcilere Windows Hizmeti çalışıyorsa. Hizmetleri uygulamasından kullanarak Windows hizmetini durdurun, **Denetim Masası** ve istemcisini çalıştıran bir <xref:System.ServiceModel.EndpointNotFoundException> istemci hizmete erişmeye çalıştığında özel durum oluştu. Windows hizmetini yeniden başlatın ve istemci yeniden çalıştırın, iletişim başarılı olur.  
  
 Hizmet koduna bir yükleyici sınıfı içeren bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ICalculator sözleşme uygulayan hizmet uygulaması sınıfı ve çalışma zamanı ana bilgisayar gibi davranan bir Windows hizmeti sınıfı. Öğesinden devralınan Yükleyici sınıfı <xref:System.Configuration.Install.Installer>, programın bir NT hizmeti olarak Installutil.exe aracı tarafından yüklenmesine izin verir. Hizmet uygulaması sınıfı `WcfCalculatorService`, olan bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] temel hizmet sözleşmesini uygulayan hizmet. Bu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] adlı bir Windows hizmeti sınıf içinde barındırılan hizmetin `WindowsCalculatorService`. Bir Windows hizmeti olarak nitelemek için sınıfının devraldığı <xref:System.ServiceProcess.ServiceBase> ve uygulayan <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> ve <xref:System.ServiceProcess.ServiceBase.OnStop> yöntemleri. İçinde <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>, <xref:System.ServiceModel.ServiceHost> nesne için oluşturulduğunda `WcfCalculatorService` yazın ve açılır. İçinde <xref:System.ServiceProcess.ServiceBase.OnStop>, ServiceHost çağırarak kapalı <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29> yöntemi <xref:System.ServiceModel.ServiceHost> nesnesi. Ana bilgisayarın taban adresi kullanılarak yapılandırılır [ \<Ekle >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md) alt öğesi olarak [ \<baseAddresses >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), bir alt öğesi olan [ \<ana bilgisayar >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) alt öğesi olarak [ \<hizmet >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) öğesi.  
  
 Temel adres tanımlanmış uç nokta kullanır ve bir [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). Aşağıdaki örnek, CalculatorService sunan uç nokta yanı sıra temel adres yapılandırmasını gösterir.  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.WcfCalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <host>  
      <baseAddresses>  
        <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
      </baseAddresses>  
    </host>  
    <!-- This endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service.  -->  
    <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    ...  
  </service>  
</services>  
```  
  
 Örneği çalıştırdığınızda, işlem isteklerini ve yanıtlarını hem hizmet hem de istemci konsol pencerelerinde görüntülenir. Her konsol penceresinde hizmet ve istemci kapatmak için ENTER tuşuna basın.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Ayarlamak için derleme ve örnek çalıştırın  
  
1.  Gerçekleştirmiş emin olun [kerelik Kurulum prosedürü Windows Communication Foundation örnekleri için](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Çözüm C# veya Visual Basic .NET sürümünü oluşturmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örnekleri derleme](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Çözüm oluşturulduktan sonra yükseltilmiş bir Setup.bat çalıştırmak [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Installutil.exe aracı kullanarak Windows hizmetini yüklemek için komut istemi. Hizmet hizmetlerinde görüntülenmelidir.  
  
4.  Tek veya çapraz bilgisayar yapılandırmasında örneği çalıştırmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örneklerini çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AppFabric barındırma ve kalıcılığı örnekleri](http://go.microsoft.com/fwlink/?LinkId=193961)
