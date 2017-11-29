---
title: "Veri kümesi ilişkisel XML yapısından çıkarımını yapma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 5a846bc321aab19cb1d04ba55ca4cca4b7188bcd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="inferring-dataset-relational-structure-from-xml"></a><span data-ttu-id="68b1a-102">Veri kümesi ilişkisel XML yapısından çıkarımını yapma</span><span class="sxs-lookup"><span data-stu-id="68b1a-102">Inferring DataSet Relational Structure from XML</span></span>
<span data-ttu-id="68b1a-103">İlişkisel yapısı veya şema, bir <xref:System.Data.DataSet> tablolar, sütunlar, kısıtlamalar ve ilişkileri oluşur.</span><span class="sxs-lookup"><span data-stu-id="68b1a-103">The relational structure, or schema, of a <xref:System.Data.DataSet> is made up of tables, columns, constraints, and relations.</span></span> <span data-ttu-id="68b1a-104">Yüklenirken bir <xref:System.Data.DataSet> , XML'den şema önceden tanımlanmış ya da, açıkça veya yüklenen XML'den çıkarım aracılığıyla oluşturulamaz.</span><span class="sxs-lookup"><span data-stu-id="68b1a-104">When loading a <xref:System.Data.DataSet> from XML, the schema can be predefined, or it can be created, either explicitly or through inference, from the XML being loaded.</span></span> <span data-ttu-id="68b1a-105">Şema ve içeriğini yükleme hakkında daha fazla bilgi için bir <xref:System.Data.DataSet> , XML'den bkz [bir veri kümesini XML dosyası şuradan yükleniyor](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) ve [XML'den veri kümesi şema bilgileri yüklenirken](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="68b1a-105">For more information about loading the schema and contents of a <xref:System.Data.DataSet> from XML, see [Loading a DataSet from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) and [Loading DataSet Schema Information from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).</span></span>  
  
 <span data-ttu-id="68b1a-106">Varsa şeması bir <xref:System.Data.DataSet> oluşturuluyor ya da XML Şeması Tanım Dili (XSD) kullanarak şemasını açıkça belirtmek için tercih edilen yöntem, XML'den olduğu (açıklandığı gibi [türetme DataSet ilişkisel yapısı XML Şeması'ndan (XSD) ](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)) veya XML verileri azaltılmış (XDR).</span><span class="sxs-lookup"><span data-stu-id="68b1a-106">If the schema of a <xref:System.Data.DataSet> is being created from XML, the preferred method is to explicitly specify the schema using either the XML Schema definition language (XSD) (as described in [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)) or the XML-Data Reduced (XDR).</span></span> <span data-ttu-id="68b1a-107">XML, şeması XML Şeması veya XDR şema varsa <xref:System.Data.DataSet> XML öğeleri ve özniteliklerinin yapısından sonuçlandı.</span><span class="sxs-lookup"><span data-stu-id="68b1a-107">If no XML Schema or XDR schema is available in the XML, the schema of the <xref:System.Data.DataSet> can be inferred from the structure of the XML elements and attributes.</span></span>  
  
 <span data-ttu-id="68b1a-108">Bu bölüm için kurallar açıklanmaktadır <xref:System.Data.DataSet> XML öğeleri ve öznitelikleri ve bunların yapısı ve olayla elde edilen göstererek şema çıkarım <xref:System.Data.DataSet> şema.</span><span class="sxs-lookup"><span data-stu-id="68b1a-108">This section describes the rules for <xref:System.Data.DataSet> schema inference by showing XML elements and attributes and their structure, and the resulting inferred <xref:System.Data.DataSet> schema.</span></span>  
  
 <span data-ttu-id="68b1a-109">Tüm öznitelikleri bir XML belgesi mevcut Çıkarma işleminde yer alması gerekir.</span><span class="sxs-lookup"><span data-stu-id="68b1a-109">Not all attributes present in an XML document should be included in the inference process.</span></span> <span data-ttu-id="68b1a-110">Namespace nitelenmiş öznitelikler için XML belgesi önemli meta veriler içerebilir ancak için <xref:System.Data.DataSet> şema.</span><span class="sxs-lookup"><span data-stu-id="68b1a-110">Namespace-qualified attributes can include metadata that is important for the XML document but not for the <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="68b1a-111">Kullanarak <xref:System.Data.DataSet.InferXmlSchema%2A>, çıkarma işlemi sırasında yok sayılacak ad alanları belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="68b1a-111">Using <xref:System.Data.DataSet.InferXmlSchema%2A>, you can specify namespaces to be ignored during the inference process.</span></span> <span data-ttu-id="68b1a-112">Daha fazla bilgi için bkz: [XML'den veri kümesi şema bilgileri yüklenirken](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="68b1a-112">For more information, see [Loading DataSet Schema Information from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68b1a-113">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="68b1a-113">In This Section</span></span>  
 [<span data-ttu-id="68b1a-114">Veri kümesi şemasını çıkarım işlem özeti</span><span class="sxs-lookup"><span data-stu-id="68b1a-114">Summary of the DataSet Schema Inference Process</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/summary-of-the-dataset-schema-inference-process.md)  
 <span data-ttu-id="68b1a-115">Şeması çıkarımını yapma için kurallar üst düzey bir özeti verilmektedir bir <xref:System.Data.DataSet> XML'den.</span><span class="sxs-lookup"><span data-stu-id="68b1a-115">Provides a high-level summary of the rules for inferring the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="68b1a-116">Tabloları çıkarımını yapma</span><span class="sxs-lookup"><span data-stu-id="68b1a-116">Inferring Tables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md)  
 <span data-ttu-id="68b1a-117">Tablolarla olayla XML öğeleri açıklanır bir <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="68b1a-117">Describes the XML elements that are inferred as tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="68b1a-118">Sütunları çıkarımını yapma</span><span class="sxs-lookup"><span data-stu-id="68b1a-118">Inferring Columns</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-columns.md)  
 <span data-ttu-id="68b1a-119">XML öğeleri ve tablo sütun olarak algılanır öznitelikleri açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="68b1a-119">Describes the XML elements and attributes that are inferred as table columns.</span></span>  
  
 [<span data-ttu-id="68b1a-120">İlişkileri çıkarımını yapma</span><span class="sxs-lookup"><span data-stu-id="68b1a-120">Inferring Relationships</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-relationships.md)  
 <span data-ttu-id="68b1a-121">Açıklar <xref:System.Data.DataRelation> ve <xref:System.Data.ForeignKeyConstraint> oluşturulan nesneler iç içe geçmiş için tabloları sonuçlandı.</span><span class="sxs-lookup"><span data-stu-id="68b1a-121">Describes the <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects created for nested, inferred tables.</span></span>  
  
 [<span data-ttu-id="68b1a-122">Öğe metni çıkarımını yapma</span><span class="sxs-lookup"><span data-stu-id="68b1a-122">Inferring Element Text</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-element-text.md)  
 <span data-ttu-id="68b1a-123">XML öğeleri metin için oluşturulan sütunları ve ne zaman metin XML öğeleri yoksayılır açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="68b1a-123">Describes the columns that are created for text in XML elements, and explains when text in XML elements is ignored.</span></span>  
  
 [<span data-ttu-id="68b1a-124">Çıkarım sınırlamaları</span><span class="sxs-lookup"><span data-stu-id="68b1a-124">Inference Limitations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inference-limitations.md)  
 <span data-ttu-id="68b1a-125">Şema çıkarım sınırlamaları açıklanır.</span><span class="sxs-lookup"><span data-stu-id="68b1a-125">Discusses the limitations of schema inference.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="68b1a-126">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="68b1a-126">Related Sections</span></span>  
 [<span data-ttu-id="68b1a-127">Bir veri kümesini XML kullanma</span><span class="sxs-lookup"><span data-stu-id="68b1a-127">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="68b1a-128">Açıklar nasıl <xref:System.Data.DataSet> nesne XML verileri ile etkileşim kurar.</span><span class="sxs-lookup"><span data-stu-id="68b1a-128">Describes how the <xref:System.Data.DataSet> object interacts with XML data.</span></span>  
  
 [<span data-ttu-id="68b1a-129">Türetilen DataSet ilişkisel yapısından XML Şeması (XSD)</span><span class="sxs-lookup"><span data-stu-id="68b1a-129">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="68b1a-130">İlişkisel yapısı veya şema açıklayan bir <xref:System.Data.DataSet> XML Şeması Tanım Dili (XSD) şemadan oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="68b1a-130">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="68b1a-131">ADO.NET genel bakış</span><span class="sxs-lookup"><span data-stu-id="68b1a-131">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 <span data-ttu-id="68b1a-132">ADO.NET açıklar mimarisi ve bileşenleri ve bunları mevcut veri kaynaklarına erişmek ve uygulama verilerini yönetmek için kullanma.</span><span class="sxs-lookup"><span data-stu-id="68b1a-132">Describes the ADO.NET architecture and components and how to use them to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b1a-133">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="68b1a-133">See Also</span></span>  
 [<span data-ttu-id="68b1a-134">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="68b1a-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)