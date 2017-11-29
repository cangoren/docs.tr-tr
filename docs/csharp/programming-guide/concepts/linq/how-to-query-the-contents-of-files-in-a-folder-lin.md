---
title: "Nasıl yapılır: bir klasördeki (LINQ) (C#) metin dosyaların içeriğini sorgulama"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f5b4dce7-1a34-4eb4-9bf1-60d5bdda264c
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a95e0ee8e3520562312f03c1f83b6cde4aac32a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-query-the-contents-of-text-files-in-a-folder-linq-c"></a><span data-ttu-id="4b7e6-102">Nasıl yapılır: bir klasördeki (LINQ) (C#) metin dosyaların içeriğini sorgulama</span><span class="sxs-lookup"><span data-stu-id="4b7e6-102">How to: Query the Contents of Text Files in a Folder (LINQ) (C#)</span></span>
<span data-ttu-id="4b7e6-103">Bu örnek, belirtilen dizin ağacındaki tüm dosyalar üzerinde sorgu, her dosyayı açın ve içeriğini inceleyin gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="4b7e6-103">This example shows how to query over all the files in a specified directory tree, open each file, and inspect its contents.</span></span> <span data-ttu-id="4b7e6-104">Bu tür bir teknik dizinler oluşturmak veya bir dizin ağacında içeriğini dizinlerini tersine çevirmek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="4b7e6-104">This type of technique could be used to create indexes or reverse indexes of the contents of a directory tree.</span></span> <span data-ttu-id="4b7e6-105">Bu örnekte, bir basit bir dize araması gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="4b7e6-105">A simple string search is performed in this example.</span></span> <span data-ttu-id="4b7e6-106">Ancak, daha karmaşık tür desen eşleştirme bir normal ifade ile gerçekleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="4b7e6-106">However, more complex types of pattern matching can be performed with a regular expression.</span></span> <span data-ttu-id="4b7e6-107">Daha fazla bilgi için bkz: [nasıl yapılır: normal ifadeler (C#) ile LINQ sorgularını birleştirme](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4b7e6-107">For more information, see [How to: Combine LINQ Queries with Regular Expressions (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b7e6-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="4b7e6-108">Example</span></span>  
  
```csharp  
class QueryContents  
{  
    public static void Main()  
    {  
        // Modify this path as necessary.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        string searchTerm = @"Visual Studio";  
  
        // Search the contents of each file.  
        // A regular expression created with the RegEx class  
        // could be used instead of the Contains method.  
        // queryMatchingFiles is an IEnumerable<string>.  
        var queryMatchingFiles =  
            from file in fileList  
            where file.Extension == ".htm"  
            let fileText = GetFileText(file.FullName)  
            where fileText.Contains(searchTerm)  
            select file.FullName;  
  
        // Execute the query.  
        Console.WriteLine("The term \"{0}\" was found in:", searchTerm);  
        foreach (string filename in queryMatchingFiles)  
        {  
            Console.WriteLine(filename);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Read the contents of the file.  
    static string GetFileText(string name)  
    {  
        string fileContents = String.Empty;  
  
        // If the file has been deleted since we took   
        // the snapshot, ignore it and return the empty string.  
        if (System.IO.File.Exists(name))  
        {  
            fileContents = System.IO.File.ReadAllText(name);  
        }  
        return fileContents;  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4b7e6-109">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="4b7e6-109">Compiling the Code</span></span>  
 <span data-ttu-id="4b7e6-110">.NET Framework sürüm 3.5 veya daha yüksek System.Core.dll başvuru hedefleyen bir proje oluşturun ve `using` System.Linq ve System.IO ad alanları için yönergeleri.</span><span class="sxs-lookup"><span data-stu-id="4b7e6-110">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b7e6-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4b7e6-111">See Also</span></span>  
 [<span data-ttu-id="4b7e6-112">LINQ ve dosya dizinleri (C#)</span><span class="sxs-lookup"><span data-stu-id="4b7e6-112">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)  
 [<span data-ttu-id="4b7e6-113">LINQ to nesneler (C#)</span><span class="sxs-lookup"><span data-stu-id="4b7e6-113">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)