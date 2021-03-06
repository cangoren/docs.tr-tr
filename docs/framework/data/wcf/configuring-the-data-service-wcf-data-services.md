---
title: "Veri Hizmeti (WCF Veri Hizmetleri) yapılandırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 59efd4c8-cc7a-4800-a0a4-d3f8abe6c55c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9eb89906d9179f4475125dc5e1ce42e9196e1522
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-the-data-service-wcf-data-services"></a>Veri Hizmeti (WCF Veri Hizmetleri) yapılandırma
İle [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], kullanıma Veri Hizmetleri oluşturabilirsiniz [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] akışları. Bu akışlardaki verileri çeşitli veri kaynaklarındaki gelebilir. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]Bu verileri olarak kullanıma sunmak için veri sağlayıcıları kullanır bir [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] akış. Bu sağlayıcıları içeren bir [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] sağlayıcı, bir yansıma sağlayıcısı ve özel veri hizmeti sağlayıcısı arabirimleri kümesi. Sağlayıcı uygulaması hizmeti veri modelini tanımlar. Daha fazla bilgi için bkz: [Veri Hizmetleri sağlayıcıları](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
 İçinde [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], veri hizmeti devralan bir sınıftır <xref:System.Data.Services.DataService%601> sınıfı, veri hizmeti türü ve veri modelinin varlık kapsayıcısının olduğu. Bu varlık kapsayıcısının döndüren bir veya daha fazla özellikleri olan bir <xref:System.Linq.IQueryable%601>, veri modelinde, varlık erişmek için kullanılan ayarlar.  
  
 Veri Hizmeti davranışlarını üyeleri tarafından tanımlanan <xref:System.Data.Services.DataServiceConfiguration> sınıfı ve üyeleri tarafından <xref:System.Data.Services.DataServiceBehavior> alanından erişilen sınıfı <xref:System.Data.Services.DataServiceConfiguration.DataServiceBehavior%2A> özelliği <xref:System.Data.Services.DataServiceConfiguration> sınıfı. <xref:System.Data.Services.DataServiceConfiguration> Sınıfı tarafından sağlanan `InitializeService` Northwind veri hizmeti aşağıdaki uyarlamasını olduğu gibi veri hizmeti tarafından uygulanan yöntemi:  
  
[!code-csharp[Astoria Northwind Service#DataServiceConfigComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/Astoria Northwind Service/cs/northwind.svc.cs#dataserviceconfigcomplete)]  
[!code-vb[Astoria Northwind Service#DataServiceConfigComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/Astoria Northwind Service/vb/northwind.svc.vb#dataserviceconfigcomplete)]  
  
## <a name="data-service-configuration-settings"></a>Veri Hizmeti yapılandırma ayarları  
 <xref:System.Data.Services.DataServiceConfiguration> Sınıfı aşağıdaki veri hizmet davranışları belirtmenize olanak sağlar:  
  
|Üye|Davranış|  
|------------|--------------|  
|<xref:System.Data.Services.DataServiceBehavior.AcceptCountRequests%2A>|Kullanarak veri hizmetine gönderilen sayısı istekleri devre dışı bırakmanıza olanak tanır `$count` yol kesimi ve `$inlinecount` sorgu seçeneği. Daha fazla bilgi için bkz: [OData: URI kuralları](http://go.microsoft.com/fwlink/?LinkId=185564).|  
|<xref:System.Data.Services.DataServiceBehavior.AcceptProjectionRequests%2A>|Veri yansıtma kullanarak veri hizmetine gönderilen istek desteğini devre dışı bırakmanıza olanak sağlayan `$select` sorgu seçeneği. Daha fazla bilgi için bkz: [OData: URI kuralları](http://go.microsoft.com/fwlink/?LinkId=185564).|  
|<xref:System.Data.Services.DataServiceConfiguration.EnableTypeAccess%2A>|Meta verilerde kullanılarak tanımlanmış bir dinamik meta veri sağlayıcısı için açığa çıkarılması bir veri türü etkinleştirir <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> arabirimi.|  
|<xref:System.Data.Services.DataServiceConfiguration.EnableTypeConversion%2A>|Veri Hizmeti çalışma zamanı istekte belirtilen gerçek özellik türü için yükü bulunan tür dönüştürme olup olmadığını belirlemenizi sağlar.|  
|<xref:System.Data.Services.DataServiceBehavior.InvokeInterceptorsOnLinkDelete%2A>|İki varlık arasında bir ilişki bağlantı silindiğinde değişiklik dinleyiciler üzerinde ilgili varlıklar çağrılan kayıtlı olsun veya olmasın belirtmenizi sağlar.|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxBatchCount%2A>|Değişiklik kümelerini sayısı sınırı ve tek bir toplu işlemde izin işlemleri sorgu sağlar. Daha fazla bilgi için bkz: [OData: Batch](http://go.microsoft.com/fwlink/?LinkId=185602) ve [toplu işlemleri](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxChangesetCount%2A>|Bir tek bir değişiklik kümesine dahil değişiklik sayısını sınırlamanıza olanak sağlar. Daha fazla bilgi için bkz: [nasıl yapılır: etkinleştirmek disk belleği veri hizmeti sonuçlarını](../../../../docs/framework/data/wcf/how-to-enable-paging-of-data-service-results-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxExpandCount%2A>|Kullanarak tek bir istekte eklenebilir ilgili varlıkların sayısı sınırlayarak yanıt boyutunun sınırlamanıza olanak sağlayan `$expand` sorgu işleci. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]bkz: [OData: URI kuralları](http://go.microsoft.com/fwlink/?LinkId=185564) ve [ertelenmiş içerik yüklenirken](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxExpandDepth%2A>|Kullanarak tek bir istekte eklenebilir ilgili varlıkların grafik derinliği sınırlayarak yanıt boyutunun sınırlamanıza olanak sağlayan `$expand` sorgu işleci. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]bkz: [OData: URI kuralları](http://go.microsoft.com/fwlink/?LinkId=185564) ve [ertelenmiş içerik yüklenirken](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxObjectCountOnInsert%2A>|Tek bir POST isteğinde bulunabilir eklenecek varlıkların sayısını sınırlamanıza olanak sağlar.|  
|<xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A>|Veri Hizmeti tarafından kullanılan Atom protokolü sürümünü tanımlar. Zaman değeri <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> en büyük değerinden daha düşük bir değere ayarlamak <xref:System.Data.Services.Common.DataServiceProtocolVersion>, en son işlevselliğini [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] veri hizmeti erişen istemciler için kullanılabilir değil. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Veri hizmeti sürüm](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxResultsPerCollection%2A>|Bir veri akışı döndürülen her varlık kümesindeki varlıkların sayısı sınırlayarak yanıt boyutunun sınırlamanıza olanak sağlar.|  
|<xref:System.Data.Services.DataServiceConfiguration.RegisterKnownType%2A>|Bir veri türü veri hizmeti tarafından tanınan türlerinin listesi ekler.|  
|<xref:System.Data.Services.DataServiceConfiguration.SetEntitySetAccessRule%2A>|Varlık için erişim haklarını, veri hizmeti üzerinde mevcut olan kaynaklar ayarlar. Bir yıldız işareti (`*`) değeri sağlanan erişim tüm kalan varlık kümeleri için aynı düzeyini ayarlamak name parametresi için. İstemci uygulamaları tarafından gerekli olan veri hizmeti kaynaklarına en az ayrıcalık erişimi sağlamak için varlık kümeleri için erişim ayarlamanızı öneririz. Daha fazla bilgi için bkz: [WCF Veri Hizmetleri güvenli hale getirme](../../../../docs/framework/data/wcf/securing-wcf-data-services.md). Belirli bir URI ve HTTP eylemi için gereken en düşük erişim hakları örnekler için bölümündeki tabloya bakın [en düşük kaynak erişim gereksinimlerini](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md#accessRequirements) bölümü.|  
|<xref:System.Data.Services.DataServiceConfiguration.SetEntitySetPageSize%2A>|Bir varlık için maksimum sayfa boyutunu kaynak ayarlar. Daha fazla bilgi için bkz: [nasıl yapılır: etkinleştirmek disk belleği veri hizmeti sonuçlarını](../../../../docs/framework/data/wcf/how-to-enable-paging-of-data-service-results-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.SetServiceOperationAccessRule%2A>|Veri hizmette tanımlanan hizmet işlemleri için erişim haklarını ayarlar. Daha fazla bilgi için bkz: [hizmet işlemleri](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md). Bir yıldız işareti (`*`) değeri sağlanan tüm hizmeti işlemleri için erişim aynı düzeyini ayarlamak name parametresi için. İstemci uygulamaları tarafından gerekli olan veri hizmeti kaynaklarına en az ayrıcalık erişimi sağlamak için hizmet işlemlerine erişimi ayarlamanızı öneririz. Daha fazla bilgi için bkz: [WCF Veri Hizmetleri güvenli hale getirme](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A>|Bu yapılandırma özelliği, daha fazla bilgi hata yanıt iletisinde döndürerek veri hizmeti daha kolay giderilir sağlar. Bu seçenek, bir üretim ortamında kullanılmak üzere tasarlanmamıştır. Daha fazla bilgi için bkz: [geliştirmek ve WCF Veri Hizmetleri dağıtma](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md).|  
  
<a name="accessRequirements"></a>   
## <a name="minimum-resource-access-requirements"></a>En düşük kaynak erişim gereksinimleri  
 Aşağıdaki tabloda Ayrıntılar belirli bir işlemi yürütmek için verilmelidir hakları minimum varlık kümesi. Path Örnekleri tamamladığınızda oluşturduğunuz Northwind veri hizmeti temel [Hızlı Başlangıç](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Çünkü hem <xref:System.Data.Services.EntitySetRights> numaralandırma ve <xref:System.Data.Services.ServiceOperationRights> numaralandırma kullanarak tanımlanmış <xref:System.FlagsAttribute>, tek bir varlık kümesi veya işlem için birden çok izinleri belirtmek için bir mantıksal OR işleci kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: veri hizmeti erişimi etkinleştir](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).  
  
|Yol/eylem|`GET`|`DELETE`|`MERGE`|`POST`|`PUT`|  
|------------------|-----------|--------------|-------------|------------|-----------|  
|`/Customers`|<xref:System.Data.Services.EntitySetRights.ReadMultiple>|Desteklenmez|Desteklenmiyor|<xref:System.Data.Services.EntitySetRights.WriteAppend>|Desteklenmez|  
|`/Customers('ALFKI')`|<xref:System.Data.Services.EntitySetRights.ReadSingle>|<xref:System.Data.Services.EntitySetRights.ReadSingle>ve<xref:System.Data.Services.EntitySetRights.WriteDelete>|<xref:System.Data.Services.EntitySetRights.ReadSingle>ve<xref:System.Data.Services.EntitySetRights.WriteMerge>|yok|<xref:System.Data.Services.EntitySetRights.ReadSingle>ve<xref:System.Data.Services.EntitySetRights.WriteReplace>|  
|`/Customers('ALFKI')/Orders`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadMultiple>|Desteklenmez|Desteklenmez|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle> ve <xref:System.Data.Services.EntitySetRights.WriteMerge> veya<xref:System.Data.Services.EntitySetRights.WriteReplace><br /><br /> - ve -<br /><br /> `Orders``:` ve<xref:System.Data.Services.EntitySetRights.WriteAppend>|Desteklenmez|  
|`/Customers('ALFKI')/Orders(10643)`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle> ve<xref:System.Data.Services.EntitySetRights.WriteDelete>|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle> ve<xref:System.Data.Services.EntitySetRights.WriteMerge>|Desteklenmez|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle> ve<xref:System.Data.Services.EntitySetRights.WriteReplace>|  
|`/Orders(10643)/Customer`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle> ve<xref:System.Data.Services.EntitySetRights.WriteDelete><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle> ve <xref:System.Data.Services.EntitySetRights.WriteMerge>;<br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|`Customers`: <xref:System.Data.Services.EntitySetRights.WriteAppend><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.WriteAppend> ve<xref:System.Data.Services.EntitySetRights.ReadSingle>|Desteklenmez|  
|`/Customers('ALFKI')/$links/Orders`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadMultiple>|Desteklenmez|Desteklenmez|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle> ve <xref:System.Data.Services.EntitySetRights.WriteMerge> veya<xref:System.Data.Services.EntitySetRights.WriteReplace><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|Desteklenmez|  
|`/Customers('ALFKI')/$links/Orders(10643)`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle> ve <xref:System.Data.Services.EntitySetRights.WriteMerge> veya<xref:System.Data.Services.EntitySetRights.WriteReplace><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|Desteklenmez|Desteklenmiyor|Desteklenmez|  
|`/Orders(10643)/$links/Customer`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|`Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle> ve <xref:System.Data.Services.EntitySetRights.WriteMerge> veya<xref:System.Data.Services.EntitySetRights.WriteReplace>|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle> ve<xref:System.Data.Services.EntitySetRights.WriteMerge>|Desteklenmez|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle>;<br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle> ve<xref:System.Data.Services.EntitySetRights.WriteReplace>|  
|`/Customers/$count`|<xref:System.Data.Services.EntitySetRights.ReadMultiple>|Desteklenmez|Desteklenmiyor|Desteklenmiyor|Desteklenmiyor|  
|`/Customers('ALFKI')/ContactName`|<xref:System.Data.Services.EntitySetRights.ReadSingle>|Desteklenmiyor|<xref:System.Data.Services.EntitySetRights.WriteMerge>|Desteklenmez|<xref:System.Data.Services.EntitySetRights.WriteReplace>|  
|`/Customers('ALFKI')/Address/StreetAddress/$value` <sup>1</sup>|<xref:System.Data.Services.EntitySetRights.ReadSingle>|<xref:System.Data.Services.EntitySetRights.WriteDelete>|Desteklenmez|Desteklenmiyor|Desteklenmez|  
|`/Customers('ALFKI')/ContactName/$value`|<xref:System.Data.Services.EntitySetRights.ReadSingle>|<xref:System.Data.Services.EntitySetRights.ReadSingle>ve<xref:System.Data.Services.EntitySetRights.WriteDelete>|<xref:System.Data.Services.EntitySetRights.WriteMerge>|Desteklenmez|<xref:System.Data.Services.EntitySetRights.WriteReplace>|  
|`/Customers('ALFKI')/$value` <sup>2</sup>|<xref:System.Data.Services.EntitySetRights.ReadSingle>|Desteklenmez|Desteklenmiyor|Desteklenmez|<xref:System.Data.Services.EntitySetRights.WriteReplace>|  
|`/Customers?$select=Orders/*&$expand=Orders`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadMultiple>|Desteklenmez|Desteklenmez|`Customers`: <xref:System.Data.Services.EntitySetRights.WriteAppend>|Desteklenmez|  
|`/Customers('ALFKI')?$select=Orders/*&$expand=Orders`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - ve -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadMultiple>|Desteklenmez|Desteklenmiyor|Desteklenmiyor|Desteklenmez|  
  
 <sup>1</sup> Bu örnekte, `Address` bir karmaşık tür özelliğini temsil eder `Customers` adlı bir özellik olan varlık `StreetAddress`. Northwind veri hizmetler tarafından kullanılan model bu karmaşık türün açıkça tanımlamıyor. Ne zaman veri modeli tanımlanmış kullanarak [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] kullanabileceğiniz sağlayıcısı [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] karmaşık bir tür tanımlamak için Araçlar. Daha fazla bilgi için bkz: [nasıl yapılır: oluşturmak ve karmaşık türler değiştirme](http://msdn.microsoft.com/en-us/afb8e206-0ffe-4597-b6d4-6ab566897e1d).  
  
 <sup>2</sup> bu URI, ikili büyük nesne (BLOB) döndüren bir özelliği, bu durumda, bir ortam bağlantı girişi bir varlığa ait medya kaynağı olarak tanımlandığında desteklenir `Customers`. Daha fazla bilgi için bkz: [Akış sağlayıcısı](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).  
  
<a name="versioning"></a>   
## <a name="versioning-requirements"></a>Sürüm oluşturma gereksinimleri  
 Aşağıdaki veri hizmeti yapılandırma davranışları 2 sürümünü gerektiren [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protokolü veya sonraki sürümler:  
  
-   Count istekleri için destek.  
  
-   Projeksiyon $select sorgu seçeneği için destek.  
  
 Daha fazla bilgi için bkz: [veri hizmeti sürüm](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WCF veri hizmetleri tanımlama](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Veri Hizmeti barındırma](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)
