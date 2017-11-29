---
title: "Nasıl yapılır: Basit değeri, bir öğenin (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5dcbe3faa457a4880a85f5827d0e5c4808b6a44b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a><span data-ttu-id="4137c-102">Nasıl yapılır: Basit değeri, bir öğenin (C#)</span><span class="sxs-lookup"><span data-stu-id="4137c-102">How to: Retrieve the Shallow Value of an Element (C#)</span></span>
<span data-ttu-id="4137c-103">Bu konuda, basit bir öğe değerini almak gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="4137c-103">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="4137c-104">Basit yalnızca belirli öğesinin değeri tek bir dize halinde birleştirilmiş tüm alt öğelerinin değerlerini içerir derin değeri aksine değerdir.</span><span class="sxs-lookup"><span data-stu-id="4137c-104">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>  
  
 <span data-ttu-id="4137c-105">Her iki çevrim kullanarak bir öğe değerini aldığınızda veya <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> özelliği, derin değeri alacak.</span><span class="sxs-lookup"><span data-stu-id="4137c-105">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property, you retrieve the deep value.</span></span> <span data-ttu-id="4137c-106">Basit değerini almak için kullanabileceğiniz `ShallowValue` genişletme yöntemi, aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="4137c-106">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the follwing example.</span></span> <span data-ttu-id="4137c-107">Basit değeri alınırken içeriğine göre öğelerini seçmek istediğinizde kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="4137c-107">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>  
  
 <span data-ttu-id="4137c-108">Aşağıdaki örnekte basit bir öğenin değerini alır. bir genişletme yöntemi bildirir.</span><span class="sxs-lookup"><span data-stu-id="4137c-108">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="4137c-109">Ardından, hesaplanan değeri içeren tüm öğeler listelemek için genişletme yöntemi sorguda kullanır.</span><span class="sxs-lookup"><span data-stu-id="4137c-109">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4137c-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="4137c-110">Example</span></span>  
 <span data-ttu-id="4137c-111">Aşağıdaki metin dosyası Report.xml, bu örnek kaynağıdır.</span><span class="sxs-lookup"><span data-stu-id="4137c-111">The following text file, Report.xml, is the source for this example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```csharp  
public static class MyExtensions  
{  
    public static string ShallowValue(this XElement xe)  
    {  
        return xe  
               .Nodes()  
               .OfType<XText>()  
               .Aggregate(new StringBuilder(),  
                          (s, c) => s.Append(c),  
                          s => s.ToString());  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement root = XElement.Load("Report.xml");  
  
        IEnumerable<XElement> query = from el in root.Descendants()  
                                      where el.ShallowValue().StartsWith("=")  
                                      select el;  
  
        foreach (var q in query)  
        {  
            Console.WriteLine("{0}{1}{2}",  
                q.Name.ToString().PadRight(8),  
                q.Attribute("Name").ToString().PadRight(20),  
                q.ShallowValue());  
        }  
    }  
}  
```  
  
 <span data-ttu-id="4137c-112">Bu örnek şu çıkışı üretir:</span><span class="sxs-lookup"><span data-stu-id="4137c-112">This example produces the following output:</span></span>  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a><span data-ttu-id="4137c-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4137c-113">See Also</span></span>  
 [<span data-ttu-id="4137c-114">LINQ-XML eksenleri (C#)</span><span class="sxs-lookup"><span data-stu-id="4137c-114">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)