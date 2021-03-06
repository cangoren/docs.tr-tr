---
title: "&lt;bkz:&gt; (C# programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 065c85ba411794858c8c4d70de0ac1467da1fe56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltseegt-c-programming-guide"></a>&lt;bkz:&gt; (C# programlama Kılavuzu)
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Parametreler  
 cref = " `member`"  
 Bir üye ya da geçerli derleme ortamından çağrılacak kullanılabilir alan başvuru. Verilen code öğesi var ve geçirir derleyici denetler `member` çıktı XML öğesi adı. Yer *üye* çift tırnak işareti ("").  
  
## <a name="remarks"></a>Açıklamalar  
 \<Bkz > etiketi metin içindeki bir bağlantıdan belirtmenize olanak sağlar. Kullanım [ \<seealso >](../../../csharp/programming-guide/xmldoc/seealso.md) metin bir Ayrıca bkz. bölümünde yerleştirilmesi gerektiğini belirtmek için. Kullanım [cref özniteliği](../../../csharp/programming-guide/xmldoc/cref-attribute.md) kod öğeleri için belgeleri sayfalara iç köprüler oluşturmak için.  
  
 İle derleme [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) bir dosyaya işlem belgesi açıklamaları için.  
  
 Aşağıdaki örnekte gösterildiği bir \<bkz > Özet bölümü içindeki etiketi.  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# programlama kılavuzu](../../../csharp/programming-guide/index.md)  
 [Belge açıklamaları için önerilen etiketler](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
