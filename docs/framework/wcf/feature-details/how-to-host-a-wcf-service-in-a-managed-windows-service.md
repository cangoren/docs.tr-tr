---
title: "Nasıl yapılır: Yönetilen Bir Windows Hizmetinde Bir WCF Hizmeti Barındırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e8572541e0bf9ddcfb93939c177b5cb8c440b41
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a>Nasıl yapılır: Yönetilen Bir Windows Hizmetinde Bir WCF Hizmeti Barındırma
Bu konu oluşturmak için gereken temel adımlarda özetler bir [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bir Windows hizmeti tarafından barındırılan hizmet. Senaryo barındırma uzun süreli olduğundan seçeneği yönetilen Windows hizmeti tarafından etkin [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] etkinleştirildi, değil ileti güvenli bir ortamda Internet Information Services (IIS) dışında barındırılan hizmeti. Hizmet ömrü, bunun yerine işletim sistemi tarafından denetlenir. Barındırma bu seçenek, tüm Windows sürümlerinde kullanılabilir.  
  
 Windows Hizmetleri Microsoft.ManagementConsole.SnapIn Microsoft Yönetim Konsolu (MMC) ile yönetilebilir ve sistem önyüklendiğinde otomatik olarak başlatılmasını yapılandırılabilir. Bu barındırma seçeneği barındıran uygulama etki alanı (AppDomain) kaydetme oluşan bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmet yönetilen bir Windows hizmet böylece hizmeti işlem ömrü Windows Hizmetleri için Hizmet Denetim Yöneticisi (SCM) tarafından denetlenir.  
  
 Hizmet koduna bir hizmet uygulaması hizmet sözleşmesi, bir Windows hizmet sınıfı ve bir yükleyici sınıfı içerir. Hizmet uygulaması sınıfı `CalculatorService`, olan bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmet. `CalculatorWindowsService` Bir Windows hizmetidir. Bir Windows hizmeti olarak nitelemek için sınıfının devraldığı `ServiceBase` ve uygulayan `OnStart` ve `OnStop` yöntemleri. İçinde `OnStart`, <xref:System.ServiceModel.ServiceHost> için oluşturulan `CalculatorService` yazın ve açılır. İçinde `OnStop`, hizmeti durdurulur ve atıldı. Konak, uygulama ayarları'nda yapılandırılmış hizmet ana bilgisayarı için bir taban adresi sağlamaktan sorumludur. Öğesinden devralınan Yükleyici sınıfı <xref:System.Configuration.Install.Installer>, programın bir Windows hizmeti olarak Installutil.exe aracı tarafından yüklenmesine izin verir.  
  
### <a name="construct-the-service-and-provide-the-hosting-code"></a>Hizmet oluşturmak ve barındırma kodu sağlayın  
  
1.  "Hizmet" adlı yeni bir Visual Studio konsol uygulama projesi oluşturun.  
  
2.  Program.cs için adını da yeniden adlandırın.  
  
3.  Ad alanı için Microsoft.ServiceModel.Samples değiştirin.  
  
4.  Aşağıdaki derlemeler başvurular ekleyin.  
  
    -   System.ServiceModel.dll  
  
    -   System.ServiceProcess.dll  
  
    -   System.Configuration.Install.dll  
  
5.  Aşağıdaki using deyimlerini adını da ekleyin.  
  
     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]  
  
6.  Tanımlamak `ICalculator` aşağıdaki kodda gösterildiği gibi hizmet sözleşme.  
  
     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]  
  
7.  Adlı bir sınıf hizmet sözleşmesini uygulama `CalculatorService` aşağıdaki kodda gösterildiği gibi.  
  
     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]  
  
8.  Adlı yeni bir sınıf oluşturmak `CalculatorWindowsService` devraldığı <xref:System.ServiceProcess.ServiceBase> sınıfı. Adlı bir yerel değişken Ekle `serviceHost` başvuru <xref:System.ServiceModel.ServiceHost> örneği. Tanımlamak `Main` çağıran yöntemi`ServiceBase.Run(new CalculatorWindowsService)`  
  
     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]  
  
9. Geçersiz kılma <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> oluşturarak ve yeni açma yöntemini <xref:System.ServiceModel.ServiceHost> örneği aşağıdaki kodda gösterildiği gibi.  
  
     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]  
  
10. Geçersiz kılma <xref:System.ServiceProcess.ServiceBase.OnStop%2A> yöntemi kapanış <xref:System.ServiceModel.ServiceHost> aşağıdaki kodda gösterildiği gibi.  
  
     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]  
  
11. Adlı yeni bir sınıf oluşturmak `ProjectInstaller` devraldığı <xref:System.Configuration.Install.Installer> ve ile işaretlenmiş <xref:System.ComponentModel.RunInstallerAttribute> kümesine `true`. Bu, Windows hizmeti tarafından Installutil.exe aracı yüklü olmasını sağlar.  
  
     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]  
  
12. Kaldırma `Service` proje oluşturduğunuzda, oluşturulan sınıf.  
  
13. Uygulama yapılandırma dosyası projeye ekleyin. Aşağıdaki yapılandırma XML dosyasının içeriğini değiştirin.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>    <services>  
          <!-- This section is optional with the new configuration model  
               introduced in .NET Framework 4. -->  
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                   behaviorConfiguration="CalculatorServiceBehavior">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
              </baseAddresses>  
            </host>  
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
            <endpoint address=""  
                      binding="wsHttpBinding"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->  
            <endpoint address="mex"  
                      binding="mexHttpBinding"  
                      contract="IMetadataExchange" />  
          </service>  
        </services>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="CalculatorServiceBehavior">  
              <serviceMetadata httpGetEnabled="true"/>  
              <serviceDebug includeExceptionDetailInFaults="False"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     App.config dosyasını sağ tıklatın **Çözüm Gezgini** seçip **özellikleri**. Altında **çıktı dizinine Kopyala** seçin **yeniyse Kopyala**.  
  
     Bu örnek, yapılandırma dosyasında uç noktalar açıkça belirtir. Hizmeti için uç nokta eklemezseniz çalışma zamanı varsayılan uç noktaları ekler. Bu örnekte, hizmetin sahip olduğu bir <xref:System.ServiceModel.Description.ServiceMetadataBehavior> kümesine `true`, hizmetiniz etkin meta veri yayımlama de vardır. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Varsayılan uç noktalar, bağlamaları ve davranışları, bkz: [Basitleştirilmiş yapılandırma](../../../../docs/framework/wcf/simplified-configuration.md) ve [WCF hizmetleri için Basitleştirilmiş yapılandırma](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
### <a name="install-and-run-the-service"></a>Yükleyin ve hizmet çalıştırın  
  
1.  Çözüm oluşturmak için yapı `Service.exe` yürütülebilir.  
  
2.  Açık [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] komut istemi açın ve proje dizinine gidin. Tür `installutil bin\service.exe` Windows hizmetini yüklemek için komut isteminde.  
  
    > [!NOTE]
    >  Kullanmıyorsanız, [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] komut isteminde, olduğundan emin olun `%WinDir%\Microsoft.NET\Framework\v4.0.<current version>` sistem yolunda dizindir.  
  
     Tür `services.msc` Hizmet Denetim Yöneticisi (SCM) erişmek için komut isteminde. Windows hizmeti Hizmetleri'nde "WCFWindowsServiceSample" görünmelidir. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmeti yalnızca yanıt verebilmesini istemcilere Windows Hizmeti çalışıyorsa. Hizmeti başlatmak için SCM ve "Başlat" veya türü sağ **net Başlat WCFWindowsServiceSample** komut isteminde.  
  
3.  Hizmete değişiklik yaparsanız, öncelikle durdurmak ve bunu kaldırın. Hizmeti durdurmak, SCM hizmetinde sağ tıklatın ve "Durdur" seçin veya **türü net stop WCFWindowsServiceSample** komut isteminde. Windows hizmetini durdurun ve sonra bir istemci çalıştırırsanız unutmayın bir <xref:System.ServiceModel.EndpointNotFoundException> istemci hizmete erişmeye çalıştığında özel durum oluştu. Windows hizmet türünü kaldırmak için **InstallUtil /u bin\service.exe** komut isteminde.  
  
## <a name="example"></a>Örnek  
 Bu konuda kullanılan kod tam bir listesi verilmiştir.  
  
 [!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
 [!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]  
  
 "Kendi kendine barındırma" seçeneği gibi bazı barındırma kod uygulamanın bir parçası yazılması barındırma ortamı Windows hizmetini gerektirir. Hizmeti bir konsol uygulaması olarak uygulanır ve kendi barındırma kodu içerir. Windows İşlem Etkinleştirme Hizmeti (WAS) barındıran Internet Information Services (IIS) gibi diğer ortamlarda barındırma, geliştiricilerin yazmak için ise gerekli değildir kod barındırma.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Basitleştirilmiş yapılandırma](../../../../docs/framework/wcf/simplified-configuration.md)  
 [Yönetilen bir uygulamada barındırma](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)  
 [Barındırma hizmetleri](../../../../docs/framework/wcf/hosting-services.md)  
 [Windows Server App Fabric barındırma özellikleri](http://go.microsoft.com/fwlink/?LinkId=201276)
