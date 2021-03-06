---
title: "MissingMetadataException Sınıfı (.NET Yerel)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 408f25c4-6d60-475c-92b1-7b52b777c6db
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 607204081c71a4489a1a67ced24af12b150632e9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="missingmetadataexception-class-net-native"></a>MissingMetadataException Sınıfı (.NET Yerel)
**Windows 10, Windows uygulamaları için .NET [!INCLUDE[net_native](../../../includes/net-native-md.md)] yalnızca**  
  
 Yansıma yer almayan meta verilerini almak için kullanılan olmadığında oluşan özel durum.  
  
 **Namespace:** System.Reflection  
  
> [!IMPORTANT]
>  `MissingMetadataException` Sınıfı içindir yalnızca tarafından dahili kullanımla [!INCLUDE[net_native](../../../includes/net-native-md.md)] araç zinciri. Üçüncü taraf kodu kullanmak için hedeflenmemiş ya da özel durum, uygulama kodunuzda işlemelidir. Bunun yerine, girişlere ekleyerek özel durum ortadan, [çalışma zamanı yönergeleri dosya](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md). Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
## <a name="syntax"></a>Sözdizimi  
 [!code-csharp[ProjectN#4](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missingmetadataexception_syntax1.cs#4)]  
  
 Unutmayın `MissingMetadataException` sınıfı türer <xref:System.TypeAccessException>.  
  
 `MissingMetadataException` Sınıfı aşağıdaki üyeleri sahiptir:  
  
## <a name="constructors"></a>Oluşturucular  
  
|Oluşturucu|Açıklama|  
|-----------------|-----------------|  
|`public MissingMetadataException()`|Yeni bir örneğini başlatır `MissingMetadataException` hatayı açıklayan sistem tarafından sağlanmış bir iletiyi kullanarak sınıfı.<br /><br /> Bu oluşturucu tarafından dahili kullanımla ilgili olduğu [!INCLUDE[net_native](../../../includes/net-native-md.md)] aracı yalnızca zinciri.|  
|`public MissingMetadataException(String message)`|Yeni bir örneğini başlatır `MissingMetadataException` belirtilen hata iletisiyle sınıfı.<br /><br /> Bu oluşturucu tarafından dahili kullanımla ilgili olduğu [!INCLUDE[net_native](../../../includes/net-native-md.md)] yalnızca torol zinciri.|  
  
## <a name="properties"></a>Özellikler  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|Ek kullanıcı tanımlı özel durumla ilgili bilgiler anahtar/değer çiftleri koleksiyonu alır. (Devralınan <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public string HelpLink { get; set; }`|Alır veya bu özel durumla ilgili Yardım dosyası için bir bağlantı ayarlar. (Devralınan <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public int HResult { get; protected set; }`|Alır veya ayarlar `HRESULT`, belirli bir özel durum atanan sayısal değer kodlanmış. (Devralınan <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public Exception InnerException { get; }`|Geçerli özel durumun nedeni özel durumu alır. (Devralınan <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public string Message { get; }`|Geçerli özel durumu açıklayan bir ileti alır. (Devralınan <xref:System.TypeLoadException>.)|  
|`public string Source { get; set; }`|Alır veya uygulama veya hataya nesnesinin adını ayarlar. (Devralınan <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public string StackTrace { get; }`|Çağrı yığınındaki hemen çerçeveler dize gösterimini alır. (Devralınan <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public MethodBase TargetSite { get; }`|Geçerli bir özel durum belirtti yöntemi alır. (Devralınan <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public string TypeName { get; ]`|Yalnızca meta veri eksik türünün tam adını alır. (Devralınan <xref:System.TypeLoadException>.)|  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.  (Devralınan <xref:System.Exception?displayProperty=nameWithType>.)|  
|`protected void Finalize()`|Kaynakları serbest ve atık toplama tarafından alınmadan önce diğer temizleme işlemleri gerçekleştirmek denemek bir nesne sağlar. (Devralınan <xref:System.Object>.)|  
|`public Exception GetBaseException()`|Bir veya daha fazla sonraki özel kök nedenini özel durum döndürür. (Devralınan <xref:System.Exception?displayProperty=nameWithType>.)|  
|`public int GetHashCode()`|Bir karma kodu döndürür bir `MissingMetadataException` örneği.   (Devralınan <xref:System.Object>.)|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Ayarlar bir <xref:System.Runtime.Serialization.SerializationInfo> özel durum hakkında bilgi içeren nesne.  (Devralınan <xref:System.TypeLoadException>.)|  
|`public Type GetType()`|Geçerli örneğin çalışma zamanı türünü alır. (Devralınan <xref:System.Exception?displayProperty=nameWithType>.)|  
|`protected Object MemberwiseClone()`|Geçerli nesne basit bir kopyasını oluşturur. (Devralınan <xref:System.Object>.)|  
|`public string ToString()`|Geçerli özel durumun dize gösterimini döndürür. (Devralınan <xref:System.Exception?displayProperty=nameWithType>.)|  
  
## <a name="events"></a>Olaylar  
  
|Olay|Açıklama|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Bir özel durum seri içeren bir özel durum nesnesi oluşturmak için veri özel durumla ilgili serileştirilmiş oluşur. (Devralınan <xref:System.Exception?displayProperty=nameWithType>.)|  
  
## <a name="usage-details"></a>Kullanım ayrıntıları  
 `MissingMetadataException` Yansıma bir derlemede kullanılamaz meta verilerine erişmek için kullanıldığında, özel durum.  
  
 Çalışma zamanında bir uygulama için kullanılabilir meta veri çalışma zamanı yönergeleri (XML yapılandırması) dosyası tarafından tanımlanan *. rd.xml. Bu özel durum atma uygulamanızı önlemek için değiştirmelisiniz \*. çalışma zamanında bulunmalıdır meta verileri tanımlamak için rd.xml. Biçimi hakkında bilgi için \*. rd.xml dosya bkz [çalışma zamanı yönergeleri (rd.xml) yapılandırma dosyası başvurusu](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
> [!IMPORTANT]
>  Bu durum, uygulamanız tarafından gerekli meta verilerin çalışma zamanında kullanılamaz gösterir olduğundan, bu özel durum işleme döndürmemelidir bir `try` / `catch` bloğu. Bunun yerine, özel durumun nedeni tanılamanıza ve bir çalışma zamanı yönergeleri dosyası kullanarak kaldırın. Özel durum ortadan kaldırır, çalışma zamanı yönergeleri dosyasına ekleyebilirsiniz giriş almak için iki sorun gidericileri birini kullanabilirsiniz:  
>   
>  -   [MissingMetadataException sorun gidericisini](http://dotnet.github.io/native/troubleshooter/type.html) türleri için.  
> -   [MissingMetadataException sorun gidericisini](http://dotnet.github.io/native/troubleshooter/method.html) yöntemleri için.  
  
 `MissingMetadataException` Sınıfı benzersiz üye içeriyor; tüm üyeleri kendi taban sınıfından devralınır <xref:System.TypeAccessException>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Exception?displayProperty=nameWithType>  
 <xref:System.TypeAccessException>  
 [Missingınteropdataexception sınıfı](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)  
 [MissingRuntimeArtifactException sınıfı](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)  
 [Çalışma zamanı yönergeleri (rd.xml) yapılandırma dosyası başvurusu](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
