---
title: "ADO.NET genel bakış"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee3bc1d8-11db-4be4-89eb-c708cf04117d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ae25f03a091d3a9705a2e445fec948d8c5e15e0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="adonet-overview"></a><span data-ttu-id="f3e98-102">ADO.NET genel bakış</span><span class="sxs-lookup"><span data-stu-id="f3e98-102">ADO.NET Overview</span></span>
<span data-ttu-id="f3e98-103">ADO.NET veri kaynakları SQL Server ve XML gibi ve OLE DB ve ODBC ile kullanıma sunulan veri kaynaklarına tutarlı erişimi sağlar.</span><span class="sxs-lookup"><span data-stu-id="f3e98-103">ADO.NET provides consistent access to data sources such as SQL Server and XML, and to data sources exposed through OLE DB and ODBC.</span></span> <span data-ttu-id="f3e98-104">Veri paylaşımı tüketici uygulamaları ADO.NET bu veri kaynaklarına bağlanmak ve alabilir, işlemek ve içerdikleri verileri güncelleştirmek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f3e98-104">Data-sharing consumer applications can use ADO.NET to connect to these data sources and retrieve, handle, and update the data that they contain.</span></span>  
  
 <span data-ttu-id="f3e98-105">ADO.NET veri erişimini veri işleme ayrı ayrı veya dağıtımınızla birlikte kullanılabilir ayrık bileşenlere ayırır.</span><span class="sxs-lookup"><span data-stu-id="f3e98-105">ADO.NET separates data access from data manipulation into discrete components that can be used separately or in tandem.</span></span> <span data-ttu-id="f3e98-106">ADO.NET bir veritabanına bağlanma, komutları çalıştırma ve sonuçları için .NET Framework veri sağlayıcısı içerir.</span><span class="sxs-lookup"><span data-stu-id="f3e98-106">ADO.NET includes .NET Framework data providers for connecting to a database, executing commands, and retrieving results.</span></span> <span data-ttu-id="f3e98-107">Bu sonuçlar ya da doğrudan bir ADO.NET yerleştirilen işlenir <xref:System.Data.DataSet> kullanıcıya geçici bir şekilde kullanıma için nesne birden çok kaynak verilerle birlikte veya Katmanlar arasında geçirildi.</span><span class="sxs-lookup"><span data-stu-id="f3e98-107">Those results are either processed directly, placed in an ADO.NET <xref:System.Data.DataSet> object in order to be exposed to the user in an ad hoc manner, combined with data from multiple sources, or passed between tiers.</span></span> <span data-ttu-id="f3e98-108">`DataSet` Nesne da bağımsız bir .NET Framework veri sağlayıcısı için uygulama yerel verileri yönetmek için kullanılan veya XML'den kaynaklıdır.</span><span class="sxs-lookup"><span data-stu-id="f3e98-108">The `DataSet` object can also be used independently of a .NET Framework data provider to manage data local to the application or sourced from XML.</span></span>  
  
 <span data-ttu-id="f3e98-109">ADO.NET sınıflarını System.Data.dll içinde bulunur ve System.Xml.dll içinde bulunan XML sınıflar ile tümleştirilir.</span><span class="sxs-lookup"><span data-stu-id="f3e98-109">The ADO.NET classes are found in System.Data.dll, and are integrated with the XML classes found in System.Xml.dll.</span></span> <span data-ttu-id="f3e98-110">Bir veritabanına bağlanan örnek kod verileri alır ve ardından bu verileri bir konsol penceresinde görüntüler için bkz: [ADO.NET kod örnekleri](../../../../docs/framework/data/adonet/ado-net-code-examples.md).</span><span class="sxs-lookup"><span data-stu-id="f3e98-110">For sample code that connects to a database, retrieves data from it, and then displays that data in a console window, see [ADO.NET Code Examples](../../../../docs/framework/data/adonet/ado-net-code-examples.md).</span></span>  
  
 <span data-ttu-id="f3e98-111">ADO.NET, yönetilen kod yerel Bileşen Nesne Modeli (COM) geliştiricilerine ActiveX Data Objects (ADO) tarafından sağlanan işlevleri benzer yazan geliştiriciler için işlevsellik sağlar.</span><span class="sxs-lookup"><span data-stu-id="f3e98-111">ADO.NET provides functionality to developers who write managed code similar to the functionality provided to native component object model (COM) developers by ActiveX Data Objects (ADO).</span></span> <span data-ttu-id="f3e98-112">ADO.NET, değil ADO .NET uygulamalarınızın veri erişimi için kullanmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="f3e98-112">We recommend that you use ADO.NET, not ADO, for accessing data in your .NET applications.</span></span>  
  
 <span data-ttu-id="f3e98-113">ADO.NET veri erişimi .NET Framework içinde en dolaysız yöntem sağlar.</span><span class="sxs-lookup"><span data-stu-id="f3e98-113">ADO.NET provides the most direct method of data access within the .NET Framework.</span></span> <span data-ttu-id="f3e98-114">Temel alınan depolama modeli yerine kavramsal bir model karşı iş uygulamalarına izin veren bir üst düzey Özet için bkz: [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).</span><span class="sxs-lookup"><span data-stu-id="f3e98-114">For a higher-level abstraction that allows applications to work against a conceptual model instead of the underlying storage model, see the [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).</span></span>  
  
 <span data-ttu-id="f3e98-115">**Gizlilik bildirimi**: System.Data.dll, System.Data.Design.dll, System.Data.OracleClient.dll, System.Data.SqlXml.dll, System.Data.Linq.dll, System.Data.SqlServerCe.dll ve System.Data.DataSetExtensions.dll derlemeler yapın bir kullanıcının özel veri özel olmayan veriler arasında ayrım.</span><span class="sxs-lookup"><span data-stu-id="f3e98-115">**Privacy Statement**: The System.Data.dll, System.Data.Design.dll, System.Data.OracleClient.dll, System.Data.SqlXml.dll, System.Data.Linq.dll, System.Data.SqlServerCe.dll, and System.Data.DataSetExtensions.dll assemblies do not distinguish between a user's private data and non-private data.</span></span>  <span data-ttu-id="f3e98-116">Bu derlemeler değil toplamak, depolamak ve herhangi bir kullanıcının özel veri taşıma.</span><span class="sxs-lookup"><span data-stu-id="f3e98-116">These assemblies do not collect, store, or transport any user's private data.</span></span> <span data-ttu-id="f3e98-117">Ancak, üçüncü taraf uygulamalar toplamak, depolamak veya bu derlemeler kullanarak bir kullanıcının özel veri taşıma.</span><span class="sxs-lookup"><span data-stu-id="f3e98-117">However, third-party applications might collect, store, or transport a user's private data using these assemblies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3e98-118">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="f3e98-118">In This Section</span></span>  
 [<span data-ttu-id="f3e98-119">ADO.NET mimarisi</span><span class="sxs-lookup"><span data-stu-id="f3e98-119">ADO.NET Architecture</span></span>](../../../../docs/framework/data/adonet/ado-net-architecture.md)  
 <span data-ttu-id="f3e98-120">Mimarisine genel bakış ve ADO.NET bileşenlerinin sağlar.</span><span class="sxs-lookup"><span data-stu-id="f3e98-120">Provides an overview of the architecture and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="f3e98-121">ADO.NET teknoloji seçenekleri ve yönergeleri</span><span class="sxs-lookup"><span data-stu-id="f3e98-121">ADO.NET Technology Options and Guidelines</span></span>](../../../../docs/framework/data/adonet/ado-net-technology-options-and-guidelines.md)  
 <span data-ttu-id="f3e98-122">Varlık veri platformuyla dahil teknolojileri ve ürünleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="f3e98-122">Describes the products and technologies included with the Entity Data Platform.</span></span>  
  
 [<span data-ttu-id="f3e98-123">LINQ ve ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f3e98-123">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 <span data-ttu-id="f3e98-124">Dil ile tümleşik sorgu (LINQ) ADO.NET nasıl uygulandığı açıklanır ve ilgili konulara bağlantılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="f3e98-124">Describes how Language-Integrated Query (LINQ) is implemented in ADO.NET and provides links to relevant topics.</span></span>  
  
 [<span data-ttu-id="f3e98-125">.NET framework veri sağlayıcıları</span><span class="sxs-lookup"><span data-stu-id="f3e98-125">.NET Framework Data Providers</span></span>](../../../../docs/framework/data/adonet/data-providers.md)  
 <span data-ttu-id="f3e98-126">.NET Framework veri sağlayıcısı ve ADO.NET ile birlikte .NET Framework veri sağlayıcıları tasarım genel bir bakış sağlar.</span><span class="sxs-lookup"><span data-stu-id="f3e98-126">Provides an overview of the design of the .NET Framework data provider and of the .NET Framework data providers that are included with ADO.NET.</span></span>  
  
 [<span data-ttu-id="f3e98-127">ADO.NET veri kümeleri</span><span class="sxs-lookup"><span data-stu-id="f3e98-127">ADO.NET DataSets</span></span>](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 <span data-ttu-id="f3e98-128">Genel bir bakış sağlar `DataSet` tasarım ve bileşenleri.</span><span class="sxs-lookup"><span data-stu-id="f3e98-128">Provides an overview of the `DataSet` design and components.</span></span>  
  
 [<span data-ttu-id="f3e98-129">ADO.NET yan yana yürütme</span><span class="sxs-lookup"><span data-stu-id="f3e98-129">Side-by-Side Execution in ADO.NET</span></span>](../../../../docs/framework/data/adonet/side-by-side-execution.md)  
 <span data-ttu-id="f3e98-130">ADO.NET sürümleri ve yan yana yürütme ve uygulama uyumluluğu üzerindeki etkilerini farklılıklar açıklanır.</span><span class="sxs-lookup"><span data-stu-id="f3e98-130">Discusses differences in ADO.NET versions and their effect on side-by-side execution and application compatibility.</span></span>  
  
 [<span data-ttu-id="f3e98-131">ADO.NET kod örnekleri</span><span class="sxs-lookup"><span data-stu-id="f3e98-131">ADO.NET Code Examples</span></span>](../../../../docs/framework/data/adonet/ado-net-code-examples.md)  
 <span data-ttu-id="f3e98-132">ADO.NET veri sağlayıcıları kullanarak verileri kod örnekleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="f3e98-132">Provides code samples that retrieve data using the ADO.NET data providers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f3e98-133">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="f3e98-133">Related Sections</span></span>  
 [<span data-ttu-id="f3e98-134">ADO.NET yenilikler nelerdir?</span><span class="sxs-lookup"><span data-stu-id="f3e98-134">What's New in ADO.NET</span></span>](../../../../docs/framework/data/adonet/whats-new.md)  
 <span data-ttu-id="f3e98-135">Yeni özellikler sunmaktadır [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3e98-135">Introduces features that are new in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
 [<span data-ttu-id="f3e98-136">ADO.NET uygulamalarının güvenliğini sağlama</span><span class="sxs-lookup"><span data-stu-id="f3e98-136">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 <span data-ttu-id="f3e98-137">Güvenli kodlama uygulamalarını ADO.NET kullanırken açıklar.</span><span class="sxs-lookup"><span data-stu-id="f3e98-137">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="f3e98-138">ADO.NET veri türü eşlemeleri</span><span class="sxs-lookup"><span data-stu-id="f3e98-138">Data Type Mappings in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 <span data-ttu-id="f3e98-139">.NET Framework veri türleri ve .NET Framework veri sağlayıcıları arasındaki veri türü eşlemeleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="f3e98-139">Describes data type mappings between .NET Framework data types and the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="f3e98-140">Alma ve ADO.NET veri değiştirme</span><span class="sxs-lookup"><span data-stu-id="f3e98-140">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 <span data-ttu-id="f3e98-141">Bir veri kaynağına bağlanmak, verileri almak ve veri değiştirme açıklar.</span><span class="sxs-lookup"><span data-stu-id="f3e98-141">Describes how to connect to a data source, retrieve data, and modify data.</span></span> <span data-ttu-id="f3e98-142">Bu içerir `DataReaders` ve `DataAdapters`.</span><span class="sxs-lookup"><span data-stu-id="f3e98-142">This includes `DataReaders` and `DataAdapters`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3e98-143">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f3e98-143">See Also</span></span>  
 [<span data-ttu-id="f3e98-144">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f3e98-144">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="f3e98-145">Visual Studio'da veri erişimi</span><span class="sxs-lookup"><span data-stu-id="f3e98-145">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)  
 [<span data-ttu-id="f3e98-146">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="f3e98-146">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)