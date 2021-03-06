---
title: "Güvenlik ve Genel Salt Okunur Dizi Alanları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ae2e9a7dd9e08344c254b52c7139c6d1dd2776a3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="security-and-public-read-only-array-fields"></a>Güvenlik ve Genel Salt Okunur Dizi Alanları
Hiçbir zaman genel salt okunur dizi alanları salt okunur genel dizi alanları değiştirilebildiğinden sınır davranışı veya güvenlik uygulamalarınızın tanımlamak için yönetilen kitaplıklarından kullanın.  
  
## <a name="remarks"></a>Açıklamalar  
 Bazı .NET framework sınıfları platforma özgü sınır parametreleri içeren salt okunur ortak alanları içerir.  Örneğin, <xref:System.IO.Path.InvalidPathChars> bir dosya yolu dizesinde izin verilmeyen karakterler tanımlayan bir dizi bir alandır.  Pek çok benzer alanları .NET Framework mevcut.  
  
 Genel salt okunur alanların değerlerini ister <xref:System.IO.Path.InvalidPathChars> kodu veya paylaşımları, kodun uygulama etki alanı kodu tarafından değiştirilebilir.  Uygulamalarınızı sınır davranışını tanımlamak için bu gibi salt okunur genel dizi alanları kullanmamanız gerekir.  Bunu yaparsanız, kötü amaçlı kod sınır tanımları alter ve kodunuzu beklenmedik bir şekilde kullanın.  
  
 Sürüm 2.0 ve daha sonra .NET Framework, genel dizi alanları kullanmak yerine yeni bir dizi döndüren yöntemler kullanmanız gerekir.  Örneğin, kullanmak yerine <xref:System.IO.Path.InvalidPathChars> alan, kullanmanız gereken <xref:System.IO.Path.GetInvalidPathChars%2A> yöntemi.  
  
 .NET Framework türleri genel alanlar sınır türlerinin dahili olarak tanımlamak için kullanmamanızı unutmayın.  Bunun yerine, .NET Framework ayrı özel alanları kullanır.  Bu ortak alanların değerlerini değiştirme .NET Framework türleri davranışını değiştirmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenli kodlama yönergeleri](../../../docs/standard/security/secure-coding-guidelines.md)
