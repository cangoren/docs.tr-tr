---
title: "Dış XSLT stil sayfaları ve belgeleri çözümleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 920cfe3b-d525-4bb2-abf6-9431651f9cf9
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a5e84935f9fff1f993a677d408287cd775269f03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="resolving-external-xslt-style-sheets-and-documents"></a>Dış XSLT stil sayfaları ve belgeleri çözümleme
Alırken birkaç kez dönüştürme sırasında dış kaynaklara çözmeniz gerekebilir.  
  
> [!NOTE]
>  <xref:System.Xml.Xsl.XslTransform> Sınıftır'te eski [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Genişletilebilir Stil sayfası dili kullanarak Dönüşümleri (XSLT) dönüştürmeleri için gerçekleştirebilirsiniz <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı.  
  
 Alırken birkaç kez dönüştürme sırasında dış kaynaklara çözmeniz gerekebilir:  
  
-   Sırasında <xref:System.Xml.Xsl.XslTransform.Load%2A> harici stil sayfası bulunamadı.  
  
-   Sırasında <xref:System.Xml.Xsl.XslTransform.Load%2A> herhangi çözümlemek için `<xsl:include>` veya `<xsl:import>` öğeler stil sayfanızda bulundu.  
  
-   Sırasında <xref:System.Xml.Xsl.XslTransform.Transform%2A> herhangi çözümlemek için `document()` işlevleri.  
  
## <a name="using-the-xmlresolver-class"></a>XmlResolver sınıfını kullanma  
 Bir ağ kaynağına erişmek için kimlik doğrulama gerekliyse kullanmak <xref:System.Xml.Xsl.XslTransform.Load%2A> sahip yöntemleri bir <xref:System.Xml.XmlResolver> iletilecek parametre <xref:System.Xml.XmlResolver> ayarlamak gerekli kimlik bilgisi özelliklere sahip nesne.  
  
 Özel bir varsa <xref:System.Xml.XmlResolver> kullanmak istediğiniz veya farklı kimlik bilgileri belirtmeniz gerekiyorsa, gerekli, dış kaynak çözünürlüğü gerektiği zaman bağlı olarak görev aşağıdaki tabloda listelenmektedir.  
  
|Hangi işlemin çözümlemesi gerektirir|Gerekli görev|  
|--------------------------------------|-------------------|  
|Sırasında <xref:System.Xml.Xsl.XslTransform.Load%2A> stil sayfası bulunamadı.|Aşırı yüklenmiş belirtin <xref:System.Xml.Xsl.XslTransform.Load%2A> , bir parametre olarak alır yöntemi bir <xref:System.Xml.XmlResolver> stil sayfası kimlik bilgileri gerektiren bir kaynakta ise.|  
|Sırasında <xref:System.Xml.Xsl.XslTransform.Load%2A> çözmek için `<xsl:include>` veya `<xsl:import>`.|Aşırı yüklenmiş belirtin <xref:System.Xml.Xsl.XslTransform.Load%2A> , bir parametre olarak alır yöntemi bir <xref:System.Xml.XmlResolver>. <xref:System.Xml.XmlResolver> Tarafından başvurulan stil sayfaları yüklemek için kullanılan `import` veya `include` deyimleri. İçinde geçirirseniz `null`, dış kaynaklara güvenilmedi.|  
|Herhangi bir çözümlemek için bir dönüşüm sırasında `document()` işlevleri.|Belirtin <xref:System.Xml.XmlResolver> kullanarak dönüştürme sırasında <xref:System.Xml.Xsl.XslTransform.Transform%2A> yönteminin alan bir <xref:System.Xml.XmlResolver> bağımsız değişkeni.|  
  
 `document()` İşlevi alır XML kaynaklar stil sayfası içinden ayrıca Giriş akışı tarafından sağlanan ilk XML verileri. Bu işlev eklenmesi olabilir XML verileri, başka bir yerde, bulunan verdiğinden bir <xref:System.Xml.XmlResolver> ile bir `null` için sağlanan değer <xref:System.Xml.Xsl.XslTransform.Transform%2A> yöntemi engeller `document()` yürütülmesini işlevi. Kullanmak istiyorsanız, `document()` işlev, kullanın <xref:System.Xml.Xsl.XslTransform.Transform%2A> yönteminin alan bir <xref:System.Xml.XmlResolver> uygun izinlere sahip yanı sıra bir parametre olarak ayarlayın.  
  
 Daha fazla bilgi için <xref:System.Xml.Xsl.XslTransform.Load%2A> yöntemi ve kullanımı <xref:System.Xml.XmlResolver>, bkz: <xref:System.Xml.Xsl.XslTransform.Load%28System.String%2CSystem.Xml.XmlResolver%29?displayProperty=nameWithType>.  
  
 Zaman <xref:System.Xml.Xsl.XslTransform.Transform%2A> yöntemi çağrıldığında, izinleri yükleme sırasında sağlanan bulgu göre hesaplanır ve izin kümesi için tüm dönüştürme süreci atanmış. Varsa `document()` işlevi izinleri bulunamadı kümesinde bir özel durum gerektiren bir eylem başlatmak dener.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çok sınıfı ile XSLT dönüştürmeler](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [XSLT işlemci çok sınıfı uygular](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [Bir çok çıkışlarından](../../../../docs/standard/data/xml/outputs-from-an-xsltransform.md)  
 [Mağazaya üzerinden XSLT dönüştürmeleri](../../../../docs/standard/data/xml/xslt-transformations-over-different-stores.md)  
 [Stil sayfası parametreleri ve uzantı nesneleri için XsltArgumentList](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md)  
 [Komut dosyası stil XSLT kullanarak \<msxsl: script >](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md)  
 [Msxsl: node-set() işlevi için destek](../../../../docs/standard/data/xml/support-for-the-msxsl-node-set-function.md)  
 [Dönüşümleri XPathNavigator](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [Dönüşümleri XPathNodeIterator](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [Çok XPathDocument giriş](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [Çok XmlDataDocument giriş](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)  
 [Çok XmlDocument giriş](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
