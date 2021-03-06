---
title: "Nasıl yapılır: WCF Etkinleştirme Bileşenlerini Yükleme ve Yapılandırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ee57276efda7edcc464c300e2f1d100b6a7c9109
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a>Nasıl yapılır: WCF Etkinleştirme Bileşenlerini Yükleme ve Yapılandırma
Bu konu Windows İşlem Etkinleştirme Hizmeti (WAS olarak da bilinir) ayarlamak için gereken adımları açıklar [!INCLUDE[wv](../../../../includes/wv-md.md)] ana bilgisayara [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ağ protokolleri HTTP üzerinden iletişim kurmazlar Hizmetleri. Aşağıdaki bölümlerde bu yapılandırma için adımlar verilmiştir:  
  
-   Yükleme (veya yüklemesini onaylamak) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] etkinleştirme bileşenleri.  
  
-   Bir HTTP olmayan protokolünü destekleyen WAS yapılandırın. Aşağıdaki yordamda [!INCLUDE[wv](../../../../includes/wv-md.md)] TCP etkinleştirme için.  
  
 Yükleme ve WAS yapılandırma gördükten sonra [nasıl yapılır: bir WCF Hizmeti barındırma](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) oluşturmak için yordamlar için bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmet WAS kullanan bir HTTP olmayan uç noktasını kullanıma sunar.  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a>WCF HTTP olmayan etkinleştirme bileşenlerini yüklemek için  
  
1.  Tıklatın **Başlat** düğmesine tıklayın ve ardından **Denetim Masası**.  
  
2.  Tıklatın **programları**ve ardından **programlar ve Özellikler**.  
  
3.  Üzerinde **görevleri** menüsünde tıklatın **kapatma Windows özelliklerini aç veya Kapat**.  
  
4.  Bul [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] düğümünü seçin ve genişletin.  
  
5.  Seçin **WCF Http olmayan etkinleştirme bileşenleri** kutusuna ve bu ayarı kaydedin.  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a>WAS TCP etkinleştirilmesini destekleyecek şekilde yapılandırmak için  
  
1.  NET.TCP etkinleştirmeyi desteklemek için varsayılan Web sitesi ilk net.tcp bağlantı noktasına bağlı olmalıdır. İle yüklenen Appcmd.exe kullanarak bunu yapabilirsiniz [!INCLUDE[iisver](../../../../includes/iisver-md.md)] yönetim araç takımı. Bir yönetici düzeyi komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Bu komut, metnin tek bir satırdır. Bu komut net.tcp site bağlaması herhangi bir ana bilgisayar adı ile 808 numaralı TCP bağlantı noktasını dinleme varsayılan Web sitesine ekler.  
  
2.  Bir sitedeki tüm uygulamaları ortak net.tcp bağlama paylaşmak rağmen her uygulama net.tcp desteğini ayrı ayrı etkinleştirebilirsiniz. Uygulama için NET.TCP etkinleştirmek için bir yönetici düzeyi komut isteminden aşağıdaki komutu çalıştırın.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  Bu komut, metnin tek bir satırdır. Bu komut etkinleştirir /\<*WCF uygulaması*> hem http://localhost kullanılarak erişilmesi için uygulama*/\<WCF uygulaması >* ve net.tcp:// localhost /*\<WCF uygulaması >*.  
  
     Eklediğiniz net.tcp site bağlaması Bu örnek için kaldırın.  
  
     Kolaylık, aşağıdaki iki adımdan örnek dizininde bulunan RemoveNetTcpSiteBinding.cmd adlı bir toplu iş dosyası uygulanır.  
  
    1.  NET.TCP, bir yönetici düzeyi komut istemi penceresinde aşağıdaki komutu çalıştırarak etkin protokoller listesinden kaldırın.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  Bu komut, metnin tek bir satırdır.  
  
    2.  Net.tcp site bağlaması, yükseltilmiş bir komut istemi penceresinde aşağıdaki komutu çalıştırarak kaldırın:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  Bu komut, metnin tek bir satırdır.  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a>NET.TCP etkin protokoller listesinden kaldırmak için  
  
1.  NET.TCP etkin protokoller listesinden kaldırmak için bir yönetici düzeyi komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  Bu komut, metnin tek bir satırdır.  
  
### <a name="to-remove-the-nettcp-site-binding"></a>Net.tcp site bağlaması kaldırmak için  
  
1.  Bağlama net.tcp sitesini kaldırmak için yönetici düzeyi komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Bu komut, metnin tek bir satırdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [TCP etkinleştirme](../../../../docs/framework/wcf/samples/tcp-activation.md)  
 [MSMQ etkinleştirme](../../../../docs/framework/wcf/samples/msmq-activation.md)  
 [NamedPipe etkinleştirme](../../../../docs/framework/wcf/samples/namedpipe-activation.md)  
 [Windows Server App Fabric barındırma özellikleri](http://go.microsoft.com/fwlink/?LinkId=201276)
