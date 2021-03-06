---
title: "Güvenilir Güvenlik Profili"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 6b73565409e26456ad09067066455ef2459b2e3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="reliable-secure-profile"></a>Güvenilir Güvenlik Profili
Bu örnek oluşturmak nasıl gösterir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ve [güvenilir güvenli profili](http://go.microsoft.com/fwlink/?LinkId=178140) (RSP). Bu örnek uygulama ortaya koyar bir [bağlantı yap](http://go.microsoft.com/fwlink/?LinkId=178141) güvenilir Mesajlaşma ile birlikte ve isteğe bağlı olarak oluşan kanal güvenilir güvenli bağlama oluşturmak için güvenli bir kanal tabanlı RSP belirtimi.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## <a name="discussion"></a>Tartışma  
 Bu örnek bir güvenilir zaman uyumsuz iki yönlü ileti exchange senaryo gösterir. Çift yönlü sözleşme hizmeti sahiptir ve çift yönlü geri çağırma sözleşme istemci uygular. İstemci üzerinde ayrı bir bağlantı beklenen bir yanıt için bir hizmet isteğine başlatır. İstek iletisi güvenilir bir şekilde gönderilir. İstemci, sonunda dinleyen bir uç noktası açmak istediğiniz değil. Bu nedenle, bu 'Bağlantı Yap' istek arka kanalda yanıtı geri gönderilecek hizmeti için 'Bağlantı Yap' isteklerin hizmetiyle yoklar. Bu örnek, istemci dinleyen bir uç nokta gösterme (ve bir güvenlik duvarı özel durum oluşturulmadan) HTTP üzerinden güvenli güvenilir çift yönlü iletişim sağlamak gösterilmiştir.  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Ayarlamak için derleme ve örnek çalıştırın  
  
1.  Açık **ReliableSecureProfile** çözümü.  
  
2.  Sağ tıklayın **hizmet** proje **Çözüm Gezgini**seçin **hata ayıklama**, **başlangıç yeni örnek** ve bağlam menüsünden. Bu hizmet ana bilgisayarını başlatır.  
  
3.  Sağ tıklayın **istemci** proje **Çözüm Gezgini**seçin **hata ayıklama**, **başlangıç yeni örnek** ve bağlam menüsünden. Bu istemci başlatır.  
  
4.  İstemci konsol penceresi satırına herhangi bir dize yazın ve ENTER tuşuna basın. Bu giriş dizesi Bu dize karmasını hesaplar hizmetine gönderir.  
  
5.  Hizmet geri istemci konsol penceresi sonucu görüntülemek için çift yönlü geri çağırma sözleşme işlemi çağırdığında sonucu windows istemcisi üzerinde görüntüleyin. Uzun süre çalışan bir veri işleme işleminin benzetimini yapmak için hizmette kasıtlı bir gecikme olur.  
  
6.  (Herhangi biri tarafından çevrimiçi ağ izleme araçları Ağ İzleyicisi, Fiddler vb. gibi) HTTP trafiğini izleme gösterir dizisi iletişimi için istemci ile hizmet arasında güvenilir güvenli profili tarafından düzenlenir ve nasıl oluşturduğunuzu istemci 'Bağlantı Yap' istekleri hizmetiyle yoklar. Hizmet işlenen yanıtı geri göndermek hazır aldığında, sonuçları geri göndermek için son 'Bağlantı Yap' isteğinin arka kanal kullanır.  
  
7.  Hizmet konsol penceresinde hizmeti kapatmak için ENTER tuşuna basın. İstemci konsol penceresi İstemcisi'ni kapatmak için ENTER tuşuna basın.
