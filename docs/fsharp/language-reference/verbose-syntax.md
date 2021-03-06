---
title: "Ayrıntılı Sözdizimi (F#)"
description: "F # programlama dili ayrıntılı ve basit sözdizimi arasındaki fark hakkında bilgi edinin."
keywords: "Visual f #, f # işlevsel programlama"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0a6792b3-b312-4453-a025-21d9760eee5d
ms.openlocfilehash: 2cef359a879897825733a3186be97b38896f5953
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="verbose-syntax"></a>Ayrıntılı Sözdizimi

F # dilinde birçok yapıları için kullanılabilen iki tür sözdizimi vardır: *ayrıntılı sözdizimi* ve *basit sözdizimi*. Ayrıntılı sözdizimi gibi yaygın olarak kullanılmaz, ancak girintileme için daha az hassas olma avantajına sahiptir. Basit sözdizimi daha kısadır ve girinti başlangıcını ve bitişini yapıları sinyal kullanmasını yerine ek anahtar sözcükler gibi `begin`, `end`, `in`ve benzeri. Varsayılan sözdizimi basit sözdizimi şeklindedir. Bu konuda, basit sözdizimi etkinleştirilmediğinde F # yapılarını sözdizimi açıklanmaktadır. Basit sözdizimi bile etkinleştirirseniz, ayrıntılı sözdizimi için bazı yapılar hala kullanabilmeniz için ayrıntılı sözdizimi her zaman etkindir. Kullanarak basit sözdizimi devre dışı bırakabilirsiniz `#light "off"` yönergesi.


## <a name="table-of-constructs"></a>Yapıları tablosu
Aşağıdaki tabloda, bağlamlarda F # dil yapıları için basit ve ayrıntılı sözdizimi gösterilmektedir iki biçim arasında bir fark olduğu. Bu tabloda, açı köşeli ayraçlar (&lt;&gt;) kullanıcı tarafından sağlanan söz dizimi öğeleri alın. Bu yapıları içinde kullanılan sözdizimi hakkında daha ayrıntılı bilgi için her dil yapısı belgelerine bakın.



<table>
<tr>
<th>Dil yapısı</th>
<th>Basit sözdizimi</th>
<th>Ayrıntılı sözdizimi</th>
</tr>
<tr>
<td>
Bileşik deyimler
</td>
<td>

```xml
<expression1>
<expression2>
```
</td><td>

```
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>


iç içe geçmiş `let` bağlamaları

</td><td>
```
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
kod bloğu
</td><td>

```
(
    <expression1>
    <expression2>
)
```

</td><td>

```
begin
    <expression1>;
    <expression2>;
end
```
</td>
</tr>
<tr><td>
`for...do`
</td><td>

```
for counter = start to finish do
    ...
```

</td><td>

```
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```
while <condition> do
    ...
```

</td><td>

```
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```
for var in start .. finish do
    ...
```

</td><td>

```
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```
do
    ...
```

</td><td>

```
do
    ...
in
```

</td>
</tr>
<tr><td>Kayıt
</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>sınıf
</td><td>
```
type <class-name>(<params>) = ... ```

</td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td>yapı</td><td>

```
[<StructAttribute>]
type <structure-name> =
    ...
```
</td><td>

```
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td>ayrılmış birleşim</td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```
</td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end    
```

</td>
</tr>
<tr><td>arabirim</td><td>

```
type <interface-name> =
    ...
```
</td><td>

```
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td>nesne ifadesi</td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td>arabirim uygulaması</td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>türü uzantısı</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>modül</td><td>

```
module <module-name> =
    ...
```

</td><td>

```
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>



## <a name="see-also"></a>Ayrıca Bkz.
[F # dili başvurusu](index.md)

[Derleyici yönergeleri](compiler-directives.md)

[Kod biçimlendirme yönergeleri](code-formatting-guidelines.md)
