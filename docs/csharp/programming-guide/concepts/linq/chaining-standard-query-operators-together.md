---
title: "Zincirleme standart sorgu işleçleri birlikte (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 47e936bffd79784b0ee6850bfc29d1d1f5b3224d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="chaining-standard-query-operators-together-c"></a><span data-ttu-id="818f4-102">Zincirleme standart sorgu işleçleri birlikte (C#)</span><span class="sxs-lookup"><span data-stu-id="818f4-102">Chaining Standard Query Operators Together (C#)</span></span>
<span data-ttu-id="818f4-103">Son konusunda budur [Öğreticisi: zincirleme sorguları birlikte (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) Öğreticisi.</span><span class="sxs-lookup"><span data-stu-id="818f4-103">This is the final topic in the [Tutorial: Chaining Queries Together (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) tutorial.</span></span>  
  
 <span data-ttu-id="818f4-104">Standart sorgu işleçleri de birbirine zincirlenebilir.</span><span class="sxs-lookup"><span data-stu-id="818f4-104">The standard query operators can also be chained together.</span></span> <span data-ttu-id="818f4-105">Örneğin, interject <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> işleci ve bu da yavaş bir şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="818f4-105">For example, you can interject the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> operator, and it also operates in a lazy fashion.</span></span> <span data-ttu-id="818f4-106">Ara sonuç tarafından gerçekleştirilip.</span><span class="sxs-lookup"><span data-stu-id="818f4-106">No intermediate results are materialized by it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="818f4-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="818f4-107">Example</span></span>  
 <span data-ttu-id="818f4-108">Bu örnekte, <xref:System.Linq.Enumerable.Where%2A> yöntemi çağırmadan önce çağrılır `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="818f4-108">In this example, the <xref:System.Linq.Enumerable.Where%2A> method is called before calling `ConvertCollectionToUpperCase`.</span></span> <span data-ttu-id="818f4-109"><xref:System.Linq.Enumerable.Where%2A> Yöntemi çalışır neredeyse tam olarak aynı şekilde Bu öğreticide, önceki örneklerde kullanılan yavaş yöntemleri `ConvertCollectionToUpperCase` ve `AppendString`.</span><span class="sxs-lookup"><span data-stu-id="818f4-109">The <xref:System.Linq.Enumerable.Where%2A> method operates in almost exactly the same way as the lazy methods used in previous examples in this tutorial, `ConvertCollectionToUpperCase` and `AppendString`.</span></span>  
  
 <span data-ttu-id="818f4-110">Bir fark vardır, bu durumda, <xref:System.Linq.Enumerable.Where%2A> yöntemi kendi kaynak toplulukta tekrarlanan ilk öğe koşulu iletmez ve geçirmek sonraki öğeyi alır belirler.</span><span class="sxs-lookup"><span data-stu-id="818f4-110">One difference is that in this case, the <xref:System.Linq.Enumerable.Where%2A> method iterates through its source collection, determines that the first item does not pass the predicate, and then gets the next item, which does pass.</span></span> <span data-ttu-id="818f4-111">Ardından, ikinci öğesi üretir.</span><span class="sxs-lookup"><span data-stu-id="818f4-111">It then yields the second item.</span></span>  
  
 <span data-ttu-id="818f4-112">Ancak, temel aynı fikirdir: olmasını sahip oldukları sürece, Ara koleksiyonları gerçekleştirilip değil.</span><span class="sxs-lookup"><span data-stu-id="818f4-112">However, the basic idea is the same: Intermediate collections are not materialized unless they have to be.</span></span>  
  
 <span data-ttu-id="818f4-113">Sorgu ifadeleri kullanıldığında, standart sorgu işleçleri çağrıları dönüştürülür ve aynı ilkeler uygulanır.</span><span class="sxs-lookup"><span data-stu-id="818f4-113">When query expressions are used, they are converted to calls to the standard query operators, and the same principles apply.</span></span>  
  
 <span data-ttu-id="818f4-114">Bu bölümdeki Office Açık XML belgeleri sorgulama örnekleri tümünün aynı ilkesini kullanın.</span><span class="sxs-lookup"><span data-stu-id="818f4-114">All of the examples in this section that are querying Office Open XML documents use the same principle.</span></span> <span data-ttu-id="818f4-115">Ertelenmiş yürütme ve geç değerlendirme LINQ (ve LINQ-XML) etkili bir şekilde kullanmak için anlamanız gereken temel kavramlar bazılarıdır.</span><span class="sxs-lookup"><span data-stu-id="818f4-115">Deferred execution and lazy evaluation are some of the fundamental concepts that you must understand  to use LINQ (and LINQ to XML) effectively.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            where s.CompareTo("D") >= 0  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="818f4-116">Bu örnek şu çıkışı üretir:</span><span class="sxs-lookup"><span data-stu-id="818f4-116">This example produces the following output:</span></span>  
  
```  
ToUpper: source >abc<  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
## <a name="see-also"></a><span data-ttu-id="818f4-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="818f4-117">See Also</span></span>  
 [<span data-ttu-id="818f4-118">Öğretici: Sorguları birlikte (C#) zincirleme</span><span class="sxs-lookup"><span data-stu-id="818f4-118">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)