---
title: "WebResponse türetme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Deriving from WebResponse
ms.assetid: f11d4866-a199-4087-9306-a5a4c18b13db
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3f732f60afeba71d26391ba5fb6484ab7562654a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="deriving-from-webresponse"></a>WebResponse türetme
<xref:System.Net.WebResponse> Sınıfı, .NET Framework takılabilir Protokolü modeli uygun protokole özgü yanıt oluşturmak için temel yöntemleri ve özellikleri sağlayan bir Özet temel sınıf. Kullanan uygulamalar <xref:System.Net.WebRequest> istek verileri sınıfına kaynaklardan gelen yanıtları almak bir **WebResponse**. Protokole özgü **WebResponse** descendants soyut üyelerini uygulanmalı **WebResponse** sınıfı.  
  
 İlişkili **WebRequest** sınıfı oluşturmalısınız **WebResponse** dışlar. Örneğin, <xref:System.Net.HttpWebResponse> örnekleri yalnızca arama sonucu olarak oluşturulan <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> veya <xref:System.Net.HttpWebRequest.EndGetResponse%2A?displayProperty=nameWithType>. Her **WebResponse** isteğinin bir kaynağa sonucunu içerir ve yüklenmek üzere tasarlanmamıştır.  
  
## <a name="contentlength-property"></a>ContentLength özelliğinin  
 <xref:System.Net.WebResponse.ContentLength%2A> Özellik tarafından döndürülen akış kullanılabilir veri bayt sayısını belirtir <xref:System.Net.WebResponse.GetResponseStream%2A> yöntemi. **ContentLength** özellik üstbilgi veya meta veri bilgileri sunucu tarafından döndürülen bayt sayısı belirtmez; yalnızca İstenen kaynak veri bayt sayısını belirtir.  
  
## <a name="contenttype-property"></a>ContentType özelliği  
 <xref:System.Net.WebResponse.ContentType%2A> Özelliği, protokol, sunucu tarafından gönderilen içerik türünü tanımlamak için istemciye göndermek gerektirdiği herhangi bir özel bilgiyi sağlar. Genellikle döndürülen veriler MIME içerik türü budur.  
  
## <a name="headers-property"></a>Üstbilgiler özelliği  
 <xref:System.Net.WebResponse.Headers%2A> Özelliği Yanıtla ilişkili meta verileri ad/değer çiftlerini rastgele bir koleksiyonunu içerir. Ad/değer çifti eklenebilir olarak ifade edilebilir protokol için gerekli herhangi bir meta veri **üstbilgileri** özelliği.  
  
 Kullanmak için gerekli **üstbilgileri** üstbilgi meta veriyi kullanmak için özelliği. Protokol özgü meta veriler özellikleri olarak gösterilebilir; Örneğin, <xref:System.Net.HttpWebResponse.LastModified%2A?displayProperty=nameWithType> özelliği çıkarır **son değiştirilen** HTTP üstbilgisi. Üstbilgi meta veri özelliği olarak kullanıma sunmak, kullanarak ayarlamak aynı özelliğe izin vermemelisiniz **üstbilgileri** özelliği.  
  
## <a name="responseuri-property"></a>ResponseUri özelliği  
 <xref:System.Net.WebResponse.ResponseUri%2A> Özelliği, aslında yanıt sağlanan kaynak URI'si içerir. Yeniden yönlendirme, desteklemeyen protokoller için **ResponseUri** aynı olacaktır <xref:System.Net.WebRequest.RequestUri%2A> özelliği **WebRequest** yanıt oluşturuldu. İstek Yönlendirme Protokolü'nü destekliyorsa **ResponseUri** yanıt URI'si içerecektir.  
  
## <a name="close-method"></a>Close Yöntemi  
 <xref:System.Net.WebResponse.Close%2A> Yöntemi istek ve yanıt tarafından yapılan tüm bağlantılar kapatır ve yanıt tarafından kullanılan kaynakları temizler. **Kapat** yöntemi yanıt tarafından kullanılan tüm akış örneği kapatır, ancak yanıt akışı için yapılan bir çağrı tarafından daha önce kapatılırsa bir özel durum oluşturmadığını <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> yöntemi.  
  
## <a name="getresponsestream-method"></a>GetResponseStream yöntemi  
 <xref:System.Net.WebResponse.GetResponseStream%2A> Yöntemi istenen kaynak yanıtı içeren bir akış döndürür. Yanıt akışı yalnızca kaynak tarafından döndürülen veri içerir; herhangi bir üst bilgi veya yanıta dahil meta veri yanıtı atılmış ve gerekir protokole özgü özellikleri üzerinden uygulama maruz veya **üstbilgileri** özelliği.  
  
 Tarafından döndürülen akış örneğini **GetResponseStream** yöntemi uygulama tarafından sahip olunan ve kapanış olmadan kapatılabilir **WebResponse**. Kural tarafından çağırma **WebResponse.Close** yöntemi tarafından döndürülen akış ayrıca kapatır **GetResponse**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Net.WebResponse>  
 <xref:System.Net.HttpWebResponse>  
 <xref:System.Net.FileWebResponse>  
 [Programlama takılabilir protokolleri](../../../docs/framework/network-programming/programming-pluggable-protocols.md)  
 [WebRequest türetme](../../../docs/framework/network-programming/deriving-from-webrequest.md)
