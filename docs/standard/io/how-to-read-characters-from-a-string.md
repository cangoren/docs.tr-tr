---
title: "Nasıl yapılır: Dizeden Karakterleri Okuma"
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
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9116ec63bfc1d12daf7627186a52bd29d5918485
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-characters-from-a-string"></a>Nasıl yapılır: Dizeden Karakterleri Okuma
Aşağıdaki kod örnekleri, bir dizeden karakterleri zaman uyumlu ve zaman uyumsuz olarak okumak gösterilmektedir.  
  
## <a name="example"></a>Örnek  
 Bu örnek, 13 karakterlerinden eşzamanlı olarak bir dize bir dizide depolar ve bu karakterleri görüntüler okur. Ardından dize kalan karakterleri okur, altıncı öğede başlangıç dizi depolar ve dizinin içeriğini görüntüler.  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a>Örnek  
 Sonraki örnekte tüm karakterler zaman uyumsuz olarak okur bir <xref:System.Windows.Controls.TextBox> denetleyen ve bunları bir dizide depolar. Ardından zaman uyumsuz olarak her harf ya da boşluk karakteri bir satır sonu arkasından ayrı bir satırda Yazar bir <xref:System.Windows.Controls.TextBlock> denetim.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IO.StringReader>  
 <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
 [Zaman uyumsuz dosya g/ç](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [NIB: Nasıl yapılır: bir dizin listesi oluşturma](http://msdn.microsoft.com/en-us/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [Nasıl yapılır: Okuma ve yeni oluşturulan veri dosyasına yazma](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [Nasıl yapılır: açın ve bir günlük dosyasına Ekle](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [Nasıl yapılır: dosyadan metin okuma](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [Nasıl yapılır: bir dosyaya metin yazma](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [Nasıl yapılır: bir dizeye karakter yazma](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [Dosya ve akış t-O](../../../docs/standard/io/index.md)
