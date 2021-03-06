---
title: "Namespace önek özelliklerini değiştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7ce6e4b705188b9c1d0949703991633e3f450689
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-prefix-properties"></a>Namespace önek özelliklerini değiştirme
**XmlNode** sınıfı belirli bir düğümle ilişkilendirilen ad alanı öneki değiştirmenize izin verir. Örneğin, aşağıdaki kod, bir öğenin değiştirilmesini önek gösterir.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **Çıktı**  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 Bir düğümün önek değiştirmek kendi ad değiştirmez. Ad yalnızca düğüm oluşturulduğunda ayarlayabilirsiniz. Ağaç kalır, yeni ad alanı öznitelikler çıkışı ayarladığınız önek karşılamak için kalıcı. Yeni ad alanı oluşturulamazsa düğüm kendi yerel ve ad alanına korur şekilde önek değiştirilir. Aşağıdaki örnek eklenmekte olan bir ad özniteliği gösterir.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **Çıktı**  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 Ne zaman ağaç kalıcı bir dizeye çağrısı sonucunda **belge. InnerXml**, `xmlns:a='123'` özniteliği ad alanını korumak için eklenmiştir `test` öğesi. Bu `'123'`, ve bunu kalan `'123'`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML belge nesne modeli (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
