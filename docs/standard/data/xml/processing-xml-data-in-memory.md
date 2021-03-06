---
title: "XML verilerini işlemek bellek içi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec4ccbff095071b279e07cee6a1aab3ca830423f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="processing-xml-data-in-memory"></a>XML verilerini işlemek bellek içi
Microsoft .NET Framework XML verilerini işlemek için üç modeli içerir: <xref:System.Xml.XmlDocument> sınıfı, <xref:System.Xml.XPath.XPathDocument> sınıfı ve [LINQ-XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).  
  
 <xref:System.Xml.XmlDocument> Sınıfı W3C belge nesne modeli (DOM) Düzey 1 çekirdeğini uygular ve çekirdek DOM Düzey 2 öneriler. DOM bir bellek içi (önbellek) olan bir XML belgesi gösterimini ağacı. İle <xref:System.Xml.XmlDocument> ve kendi ilgili sınıflar, XML belgeleri oluşturmak, yükleme ve erişim verilerini, verileri değiştirme ve değişiklikleri kaydedilsin.  
  
 <xref:System.Xml.XPath.XPathDocument> XPath veri modelini temel alan bir salt okunur, bellek içi veri deposu bir sınıftır. <xref:System.Xml.XPath.XPathNavigator> Sınıfı sunar birkaç düzenleme seçenekleri ve gezinti özellikleri salt okunur bulunan XML belgelerini üzerinden bir imleç modeli kullanılarak <xref:System.Xml.XPath.XPathDocument> sınıfı yanı sıra <xref:System.Xml.XmlDocument> sınıfı.  
  
 [LINQ-XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) .NET Framework sürüm 3.5 XML verilerini işlemek için yeni modelidir. Yararlanır bir bellek içi modelini olan [LINQ (dil ile tümleşik sorgu)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d). LINQ C# ve Visual Basic yeni sorgu özellikleri sağlamak üzere dili sözdizimi genişletir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [DOM modelini kullanarak işlem XML verileri](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 Kullanarak anlatılmaktadır <xref:System.Xml.XmlDocument>ve ilişkili sınıfları XML verileri işleyemedi.  
  
 [XPath veri modelini kullanarak işlem XML verileri](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 Kullanarak anlatılmaktadır <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, ve <xref:System.Xml.XPath.XPathNavigator> sınıfları XML veri işleyecek.  
  
 [LINQ-XML kullanılarak XML verilerini işlemek](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 XML LINQ kısa bir genel bakış sağlar ve LINQ-XML belgeleri için bağlantılar sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [XML belgeleri ve verileri](../../../../docs/standard/data/xml/index.md)
