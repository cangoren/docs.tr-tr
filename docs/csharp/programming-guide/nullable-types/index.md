---
title: "Boş Değer Atanabilir Türler (C# Programlama Kılavuzu)"
ms.date: 05/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: "44"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: af7de7ea0be5368371e4bb174f6313e98f93ac4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-types-c-programming-guide"></a><span data-ttu-id="906a2-102">Boş Değer Atanabilir Türler (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="906a2-102">Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="906a2-103">Boş değer atanabilir türler örnekleridir <xref:System.Nullable%601?displayProperty=nameWithType> yapısı.</span><span class="sxs-lookup"><span data-stu-id="906a2-103">Nullable types are instances of the <xref:System.Nullable%601?displayProperty=nameWithType> struct.</span></span> <span data-ttu-id="906a2-104">Boş değer atanabilir bir tür değerleri temel alınan değer türü artı ek için doğru aralığı gösterebilir `null` değeri.</span><span class="sxs-lookup"><span data-stu-id="906a2-104">A nullable type can represent the correct range of values for its underlying value type, plus an additional `null` value.</span></span> <span data-ttu-id="906a2-105">Örneğin, bir `Nullable<Int32>`, okunur "Boş değer atanabilir, Int32," atanabilir herhangi bir değer -2147483648 2147483647 için ya da bu atanabilir `null` değeri.</span><span class="sxs-lookup"><span data-stu-id="906a2-105">For example, a `Nullable<Int32>`, pronounced "Nullable of Int32," can be assigned any value from -2147483648 to 2147483647, or it can be assigned the `null` value.</span></span> <span data-ttu-id="906a2-106">A `Nullable<bool>` değerler atanabilir [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), veya [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="906a2-106">A `Nullable<bool>` can be assigned the values [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), or [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="906a2-107">Atama olanağı `null` veritabanları ve bir değer atanamaz öğeleri içeren diğer veri türleri ile ilgilenirken sayısal ve Boole türleri için özellikle yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="906a2-107">The ability to assign `null` to numeric and Boolean types is especially useful when you are dealing with databases and other data types that contain elements that may not be assigned a value.</span></span> <span data-ttu-id="906a2-108">Örneğin, bir veritabanında bir Boole alanı değerleri depolayabilir `true` veya `false`, veya tanımsız olabilir.</span><span class="sxs-lookup"><span data-stu-id="906a2-108">For example, a Boolean field in a database can store the values `true` or `false`, or it may be undefined.</span></span> 
  
[!code-csharp[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]  
  
<span data-ttu-id="906a2-109">Daha fazla örnek için bkz: [boş değer atanabilir türleri kullanma](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span><span class="sxs-lookup"><span data-stu-id="906a2-109">For more examples, see [Using Nullable Types](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span></span>  
  
## <a name="nullable-types-overview"></a><span data-ttu-id="906a2-110">Boş değer atanabilir türler genel bakış</span><span class="sxs-lookup"><span data-stu-id="906a2-110">Nullable Types Overview</span></span>  
 <span data-ttu-id="906a2-111">Boş değer atanabilir türler aşağıdaki özelliklere sahiptir:</span><span class="sxs-lookup"><span data-stu-id="906a2-111">Nullable types have the following characteristics:</span></span>  
  
-   <span data-ttu-id="906a2-112">Boş değer atanabilir türleri temsil eden değeri atanabilir değer türü değişkenleri `null`.</span><span class="sxs-lookup"><span data-stu-id="906a2-112">Nullable types represent value-type variables that can be assigned the value of `null`.</span></span> <span data-ttu-id="906a2-113">Bir başvuru türüne göre boş değer atanabilir bir tür oluşturulamıyor.</span><span class="sxs-lookup"><span data-stu-id="906a2-113">You cannot create a nullable type based on a reference type.</span></span> <span data-ttu-id="906a2-114">(Başvuru türleri zaten Destek `null` değeri.)</span><span class="sxs-lookup"><span data-stu-id="906a2-114">(Reference types already support the `null` value.)</span></span>  
  
-   <span data-ttu-id="906a2-115">Sözdizimi `T?` için toplu özelliktir <xref:System.Nullable%601>, burada `T` değer türü değil.</span><span class="sxs-lookup"><span data-stu-id="906a2-115">The syntax `T?` is shorthand for <xref:System.Nullable%601>, where `T` is a value type.</span></span> <span data-ttu-id="906a2-116">İki tür birbirinin yerine kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="906a2-116">The two forms are interchangeable.</span></span>  
  
-   <span data-ttu-id="906a2-117">Sıradan değer türü için örneğin gibi bir değer null olabilir bir tür atama `int? x = 10;` veya `double? d = 4.108`.</span><span class="sxs-lookup"><span data-stu-id="906a2-117">Assign a value to a nullable type just as you would for an ordinary value type, for example `int? x = 10;` or `double? d = 4.108`.</span></span> <span data-ttu-id="906a2-118">Boş değer atanabilir bir tür, değer atanabilir `null`:`int? x = null.`</span><span class="sxs-lookup"><span data-stu-id="906a2-118">A nullable type can also be assigned the value `null`: `int? x = null.`</span></span>  
  
-   <span data-ttu-id="906a2-119">Kullanım <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType> değer ise atanan değer veya temel alınan türü için varsayılan değer döndürmek için yöntemini `null`, örneğin`int j = x.GetValueOrDefault();`</span><span class="sxs-lookup"><span data-stu-id="906a2-119">Use the <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType> method to return either the assigned value, or the default value for the underlying type if the value is `null`, for example `int j = x.GetValueOrDefault();`</span></span>  
  
-   <span data-ttu-id="906a2-120">Kullanım <xref:System.Nullable%601.HasValue%2A> ve <xref:System.Nullable%601.Value%2A> salt okunur özellikler için null sınamak ve aşağıdaki örnekte gösterildiği gibi değeri almak için:`if(x.HasValue) j = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="906a2-120">Use the <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> read-only properties to test for null and retrieve the value, as shown in the following example: `if(x.HasValue) j = x.Value;`</span></span>  
  
    -   <span data-ttu-id="906a2-121">`HasValue` Özelliği döndürür `true` değişkeni bir değer içeriyorsa veya `false` , `null`.</span><span class="sxs-lookup"><span data-stu-id="906a2-121">The `HasValue` property returns `true` if the variable contains a value, or `false` if it is `null`.</span></span>  
  
    -   <span data-ttu-id="906a2-122">`Value` Özelliği bir atanmışsa değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="906a2-122">The `Value` property returns a value if one is assigned.</span></span> <span data-ttu-id="906a2-123">Aksi halde, bir <xref:System.InvalidOperationException?displayProperty=nameWithType> oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="906a2-123">Otherwise, a <xref:System.InvalidOperationException?displayProperty=nameWithType> is thrown.</span></span>  
  
    -   <span data-ttu-id="906a2-124">İçin varsayılan değer `HasValue` olan `false`.</span><span class="sxs-lookup"><span data-stu-id="906a2-124">The default value for `HasValue` is `false`.</span></span> <span data-ttu-id="906a2-125">`Value` Özelliğine sahip bir varsayılan değeri yok.</span><span class="sxs-lookup"><span data-stu-id="906a2-125">The `Value` property has no default value.</span></span>  
  
    -   <span data-ttu-id="906a2-126">Aynı zamanda `==` ve `!=` aşağıdaki örnekte gösterildiği gibi null olabilir bir tür işleçlerle:`if (x != null) y = x;`</span><span class="sxs-lookup"><span data-stu-id="906a2-126">You can also use the `==` and `!=` operators with a nullable type, as shown in the following example: `if (x != null) y = x;`</span></span>  
  
-   <span data-ttu-id="906a2-127">Kullanım `??` geçerli değeri null olabilir bir tür olduğunda uygulanan varsayılan bir değer atamak için işleci `null` alamayan bir tür için örneğin atanır`int? x = null; int y = x ?? -1;`</span><span class="sxs-lookup"><span data-stu-id="906a2-127">Use the `??` operator to assign a default value that will be applied when a nullable type whose current value is `null` is assigned to a non-nullable type, for example `int? x = null; int y = x ?? -1;`</span></span>  
  
-   <span data-ttu-id="906a2-128">İç içe geçmiş boş değer atanabilir türler izin verilmiyor.</span><span class="sxs-lookup"><span data-stu-id="906a2-128">Nested nullable types are not allowed.</span></span> <span data-ttu-id="906a2-129">Aşağıdaki satırı derlenmez:`Nullable<Nullable<int>> n;`</span><span class="sxs-lookup"><span data-stu-id="906a2-129">The following line will not compile: `Nullable<Nullable<int>> n;`</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="906a2-130">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="906a2-130">Related Sections</span></span>  
 <span data-ttu-id="906a2-131">Daha fazla bilgi için:</span><span class="sxs-lookup"><span data-stu-id="906a2-131">For more information:</span></span>  
  
-   [<span data-ttu-id="906a2-132">Boş değer atanabilir türleri kullanma</span><span class="sxs-lookup"><span data-stu-id="906a2-132">Using Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [<span data-ttu-id="906a2-133">Boş değer atanabilir türleri kutulama</span><span class="sxs-lookup"><span data-stu-id="906a2-133">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [<span data-ttu-id="906a2-134">?? İşleci</span><span class="sxs-lookup"><span data-stu-id="906a2-134">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="906a2-135">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="906a2-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="906a2-136">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="906a2-136">See Also</span></span>  
 <xref:System.Nullable>  
 [<span data-ttu-id="906a2-137">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="906a2-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="906a2-138">C#</span><span class="sxs-lookup"><span data-stu-id="906a2-138">C#</span></span>](../../../csharp/index.md)  
 [<span data-ttu-id="906a2-139">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="906a2-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="906a2-140">Tam olarak 'kaldırılmış' anlamı nedir?</span><span class="sxs-lookup"><span data-stu-id="906a2-140">What exactly does 'lifted' mean?</span></span>](http://go.microsoft.com/fwlink/?LinkId=112382)