---
title: '&lt;namespaceTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4a6646b94449a79c96a8720a798f48298ab32ee0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="ltnamespacetablegt"></a>&lt;namespaceTable&gt;

Ardından yönlendirme XPath filtreleri kullanılabilir önek eşlemeleri için ad alanı içeren öğeleri kümesini tanımlamak için yapılandırma bölümünü temsil eder.

**\<system.serviceModel >**   
&nbsp;&nbsp;**\<Yönlendirme >**   
&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**

## <a name="syntax"></a>Sözdizimi

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a>Öznitelikler ve öğeler

Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.

### <a name="attributes"></a>Öznitelikler

Yok.

### <a name="child-elements"></a>Alt öğeleri

|     | Açıklama |
| --- | ----------- |
| [**\<Filtre >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | XPath ifadesi için kullanılan bir ad alanı öneki eşleme tanımlar. |

### <a name="parent-elements"></a>Üst öğeler

|     | Açıklama |
| --- | ----------- |
| [**\<Yönlendirme >**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Türünü belirleme yönlendirme bir filtre kümesi tanımlamak için yapılandırma bölümünü temsil eder [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> yönlendirme yanı sıra gelen iletileri değerlendirmek için ne zaman iletileri göndermek için hedef uç nokta tanımlayan tabloları yapılırken kullanılacak bir Filtre eşleşir. |

## <a name="see-also"></a>Ayrıca bkz.

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
