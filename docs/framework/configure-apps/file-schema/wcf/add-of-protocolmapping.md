---
title: '&lt;protocolMapping&gt; &lt;ekleme&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 255cd8518bd9c6c6c199c75aa32ca086c801d23f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a>&lt;protocolMapping&gt; &lt;ekleme&gt;
Bir Aktarım Protokolü düzeni (örn., http, net.tcp, net.pipe, vb.) arasındaki bir varsayılan protokolü eşlemeyi temsil eder ve bir [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] bağlama. Varsayılan uç noktalar çalışma zamanında oluştururken [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] yapılandırılmış eşlemelerin arar ve adresine göre hangi belirli bir için kullanılacak bağlama karar verir.  
  
 \<system.serviceModel >  
\<protocolMapping >  
\<ekleme >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>
```

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|bağlama|Varsayılan uç nokta oluşturma sırasında bir uç noktası için kullanılacak bağlama türünü belirten bir dize.|  
|bindingConfiguration|Başvurulacak bağlama yapılandırma bölümünün adını belirten dize.|  
|düzen|Varsayılan uç noktası için kullanılacak Aktarım Protokolü düzeni.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<protocolMapping >](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|Aktarım Protokolü düzenleri (örn., http, net.tcp, net.pipe, vb.) arasındaki varsayılan protokolü eşlemeleri tanımlamak için yapılandırma bölümünü temsil eder ve [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] bağlar.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki yapılandırma örnek machine.config dosyasındaki varsayılan protokolü eşlemeyi gösterir. Machine.config dosyasının değiştirerek bu varsayılan eşleme makine düzeyinde geçersiz kılabilirsiniz. Veya yalnızca bir uygulama kapsamında geçersiz kılmak isterseniz, bu bölümde, uygulama yapılandırma dosyasında geçersiz kılmak ve tek protokol düzenleri için eşleme değiştirin.  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
