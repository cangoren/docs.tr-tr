---
title: "Mağazaya üzerinden XSLT dönüştürmeleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 369850e9-004a-45d2-b5c3-5060d9135adb
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b909b754c1d0d3007e06cd04376413d02cbc2f76
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="xslt-transformations-over-different-stores"></a><span data-ttu-id="4edb8-102">Mağazaya üzerinden XSLT dönüştürmeleri</span><span class="sxs-lookup"><span data-stu-id="4edb8-102">XSLT Transformations Over Different Stores</span></span>
> [!NOTE]
>  <span data-ttu-id="4edb8-103"><xref:System.Xml.Xsl.XslTransform> Sınıftır'te eski [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4edb8-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="4edb8-104">Genişletilebilir Stil sayfası dili kullanarak Dönüşümleri (XSLT) dönüştürmeleri için gerçekleştirebilirsiniz <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="4edb8-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="4edb8-105">Bkz: [XslCompiledTransform sınıfını kullanarak](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) ve [çok sınıfı geçirme](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="4edb8-105">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="4edb8-106">ADO.NET ve XML sınıfları içinde [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] verilere erişmek için birleşik bir programlama modeli sağlar.</span><span class="sxs-lookup"><span data-stu-id="4edb8-106">The ADO.NET and the XML classes in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provide a unified programming model to access data.</span></span> <span data-ttu-id="4edb8-107">Bu verileri etiketlere göre ayrılmış metin olan XML verileri ve satırları ve sütunları oluşan tabloları olan ilişkisel veri temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="4edb8-107">That data is represented as both XML data, which is text delimited by tags, and relational data, which is tables consisting of rows and columns.</span></span> <span data-ttu-id="4edb8-108">XML'de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] XML belge nesne modeli (DOM) düğüm ağaçları burada veri erişilebilir programlı olarak erişmek ve içinde ilişkisel verileri işlemek için Araçlar ADO.NET sağlarken, içine herhangi bir veri akışından XML veri okuyan bir <xref:System.Data.DataSet> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="4edb8-108">The XML in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] reads XML data from any data stream into XML Document Object Model (DOM) node trees, where data can be accessed programmatically, while ADO.NET provides the means to access and manipulate relational data within a <xref:System.Data.DataSet> object.</span></span>  
  
 <span data-ttu-id="4edb8-109">XML DOM XML belgelerini ve okuma, yazma ve XML belgelerini gezinmek için ek sınıfları veri erişimi sağlar.</span><span class="sxs-lookup"><span data-stu-id="4edb8-109">The XML DOM provides access to data in XML documents and additional classes to read, write, and navigate in XML documents.</span></span> <span data-ttu-id="4edb8-110">Bu sınıfların desteklenen <xref:System.Xml> de ADO.NET tarafından sağlanan veri erişim Hizmetleri ile XML DOM birleştiren ad alanı.</span><span class="sxs-lookup"><span data-stu-id="4edb8-110">These classes are supported in the <xref:System.Xml> namespace, which also unifies the XML DOM with the data access services provided by ADO.NET.</span></span> <span data-ttu-id="4edb8-111"><xref:System.Xml.XmlDataDocument> İlişkisel verilere erişim sağlar.</span><span class="sxs-lookup"><span data-stu-id="4edb8-111">The <xref:System.Xml.XmlDataDocument> provides relational access to data.</span></span> <span data-ttu-id="4edb8-112"><xref:System.Xml.XmlDataDocument> Bir ADO.NET ilişkisel verileri XML eşlemeleri <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="4edb8-112">The <xref:System.Xml.XmlDataDocument> maps XML to relational data in an ADO.NET <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="4edb8-113">Tüm [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-tabanlı uygulama sınıflarda kullanabileceğiniz <xref:System.Xml> erişmek ve XML belgelerini ve ilişkisel verileri işlemek için ad alanı <xref:System.Xml.XmlDataDocument>.</span><span class="sxs-lookup"><span data-stu-id="4edb8-113">Any [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-based application can use the classes in the <xref:System.Xml> namespace to access and manipulate both XML documents and relational data in the <xref:System.Xml.XmlDataDocument>.</span></span> <span data-ttu-id="4edb8-114">Bu uygulama, toplama ve veri dağıtmak için n katmanlı mimariyi destekler.</span><span class="sxs-lookup"><span data-stu-id="4edb8-114">This implementation supports n-tiered architectures for collecting and distributing data.</span></span> <span data-ttu-id="4edb8-115">Daha fazla bilgi için bkz: [ilişkisel veri ve ADO.NET XML tümleştirme](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md).</span><span class="sxs-lookup"><span data-stu-id="4edb8-115">For more information, see [XML Integration with Relational Data and ADO.NET](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4edb8-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4edb8-116">See Also</span></span>  
 [<span data-ttu-id="4edb8-117">XSLT işlemci çok sınıfı uygular</span><span class="sxs-lookup"><span data-stu-id="4edb8-117">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)