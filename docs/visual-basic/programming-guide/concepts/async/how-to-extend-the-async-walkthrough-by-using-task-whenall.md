---
title: "Nasıl yapılır: Task.WhenAll (Visual Basic) kullanarak zaman uyumsuz izlenecek yolu genişletme"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 49cca45336cb25850c888e3389e97b323c70d89d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a><span data-ttu-id="4b9d4-102">Nasıl yapılır: Task.WhenAll (Visual Basic) kullanarak zaman uyumsuz izlenecek yolu genişletme</span><span class="sxs-lookup"><span data-stu-id="4b9d4-102">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>
<span data-ttu-id="4b9d4-103">Zaman uyumsuz çözümde performansını artırabilir [izlenecek yol: Web kullanarak zaman uyumsuz ve bekleme (Visual Basic) tarafından erişme](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) kullanarak <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-103">You can improve the performance of the async solution in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) by using the <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4b9d4-104">Bu yöntem, zaman uyumsuz olarak görevleri koleksiyonu temsil edilir birden çok zaman uyumsuz işlemleri bekler.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-104">This method asynchronously awaits multiple asynchronous operations, which are represented as a collection of tasks.</span></span>  
  
 <span data-ttu-id="4b9d4-105">Web siteleri farklı hızlarda karşıdan kılavuzda fark.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-105">You might have noticed in the walkthrough that the websites download at different rates.</span></span> <span data-ttu-id="4b9d4-106">Bazen, Web siteleri, kalan tüm indirmeleri gecikmeler çok yavaş biridir.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-106">Sometimes one of the websites is very slow, which delays all the remaining downloads.</span></span> <span data-ttu-id="4b9d4-107">Kılavuzda oluşturacağınız zaman uyumsuz çözümleri çalıştırdığınızda, program kolayca beklemek istemiyorsanız, ancak aynı zamanda tüm indirmeleri başlatmak ve biri, beklemeden devam daha hızlı indirmeler izin vermek için daha iyi bir seçenek olacaktır sonlandırabilirsiniz 's  ertelendi.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-107">When you run the asynchronous solutions that you build in the walkthrough, you can end the program easily if you don't want to wait, but a better option would be to start all the downloads at the same time and let faster downloads continue without waiting for the one that’s delayed.</span></span>  
  
 <span data-ttu-id="4b9d4-108">Uyguladığınız `Task.WhenAll` yöntemine görevleri koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-108">You apply the `Task.WhenAll` method to a collection of tasks.</span></span> <span data-ttu-id="4b9d4-109">Uygulamayı `WhenAll` koleksiyondaki her görev tamamlanana kadar tamamlanmadıysa tek bir görev döndürür.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-109">The application of `WhenAll` returns a single task that isn’t complete until every task in the collection is completed.</span></span> <span data-ttu-id="4b9d4-110">Paralel olarak çalıştırmak için görevler görüntülenir, ancak hiçbir ek iş parçacığı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-110">The tasks appear to run in parallel, but no additional threads are created.</span></span> <span data-ttu-id="4b9d4-111">Herhangi bir sırada görevleri gerçekleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-111">The tasks can complete in any order.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4b9d4-112">Aşağıdaki yordamlar uzantıları da geliştirilmiş zaman uyumsuz uygulamalara açıklar [izlenecek yol: Web kullanarak zaman uyumsuz ve bekleme (Visual Basic) tarafından erişme](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="4b9d4-112">The following procedures describe extensions to the async applications that are developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="4b9d4-113">Kılavuzu tamamladıktan veya koddan indirme uygulamaları geliştirmek [Geliştirici kod örnekleri](http://go.microsoft.com/fwlink/?LinkId=255191).</span><span class="sxs-lookup"><span data-stu-id="4b9d4-113">You can develop the applications by either completing the walkthrough or downloading the code from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
>   
>  <span data-ttu-id="4b9d4-114">Örneği çalıştırmak için Visual Studio 2012 veya daha sonra bilgisayarınıza yüklenmiş olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-114">To run the example, you must have Visual Studio 2012 or later installed on your computer.</span></span>  
  
### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a><span data-ttu-id="4b9d4-115">Task.WhenAll GetURLContentsAsync çözümünüze eklemek için</span><span class="sxs-lookup"><span data-stu-id="4b9d4-115">To add Task.WhenAll to your GetURLContentsAsync solution</span></span>  
  
1.  <span data-ttu-id="4b9d4-116">Ekleme `ProcessURLAsync` da geliştirilmiş ilk uygulamaya yöntemi [izlenecek yol: Web kullanarak zaman uyumsuz ve bekleme (Visual Basic) tarafından erişme](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="4b9d4-116">Add the `ProcessURLAsync` method to the first application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="4b9d4-117">Koddan yüklediyseniz [Geliştirici kod örnekleri](http://go.microsoft.com/fwlink/?LinkId=255191)AsyncWalkthrough projesini açın ve ardından ekleyin `ProcessURLAsync` MainWindow.xaml.vb dosyasına kayıt yapar.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-117">If you downloaded the code from  [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191), open the AsyncWalkthrough project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>  
  
    -   <span data-ttu-id="4b9d4-118">Kod gözden geçirme tamamlayarak geliştirdiyseniz eklemek `ProcessURLAsync` içeren uygulamaya `GetURLContentsAsync` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-118">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that includes the `GetURLContentsAsync` method.</span></span> <span data-ttu-id="4b9d4-119">İlk örnek "Tam kod örnekleri gelen izlenecek yolu" bölümünde bu uygulama için MainWindow.xaml.vb dosyasıdır.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-119">The MainWindow.xaml.vb file for this application is the first example in the "Complete Code Examples from the Walkthrough" section.</span></span>  
  
     <span data-ttu-id="4b9d4-120">`ProcessURLAsync` Yöntemi birleştirir gövdesini Eylemler `For Each` içinde döngü `SumPageSizesAsync` özgün izlenecek adımları.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-120">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="4b9d4-121">Metodu zaman uyumsuz olarak bir bayt dizisi olarak belirtilen bir Web sitesi içeriğini indirir ve ardından görüntüler ve bayt dizisi uzunluğunu döndürür.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-121">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  <span data-ttu-id="4b9d4-122">Out yorum yapmak veya silme `For Each` içinde döngü `SumPageSizesAsync`, aşağıdaki kodda gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-122">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>  
  
    ```vb  
    'Dim total = 0  
    'For Each url In urlList  
  
    '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
    '    ' The previous line abbreviates the following two assignment statements.  
  
    '    ' GetURLContentsAsync returns a task. At completion, the task  
    '    ' produces a byte array.  
    '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
    '    'Dim urlContents As Byte() = Await getContentsTask  
  
    '    DisplayResults(url, urlContents)  
  
    '    ' Update the total.  
    '    total += urlContents.Length  
    'Next  
    ```  
  
3.  <span data-ttu-id="4b9d4-123">Bir görev koleksiyonunu oluşturun.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-123">Create a collection of tasks.</span></span> <span data-ttu-id="4b9d4-124">Aşağıdaki kodu tanımlayan bir [sorgu](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) , tarafından çalıştırıldığında <xref:System.Linq.Enumerable.ToArray%2A> yöntemi, her Web sitesi içeriğini indirme görevleri koleksiyonu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-124">The following code defines a [query](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="4b9d4-125">Sorgu değerlendirildiğinde görevleri başlatılır.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-125">The tasks are started when the query is evaluated.</span></span>  
  
     <span data-ttu-id="4b9d4-126">Yöntemine aşağıdaki kodu ekleyin `SumPageSizesAsync` bildirimi sonra `urlList`.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-126">Add the following code to method `SumPageSizesAsync` after the declaration of `urlList`.</span></span>  
  
    ```vb  
    ' Create a query.   
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  <span data-ttu-id="4b9d4-127">Uygulama `Task.WhenAll` görevleri koleksiyonu için `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-127">Apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="4b9d4-128">`Task.WhenAll`görevlerin koleksiyonundaki tüm görevler tamamlandığında bittikten tek bir görev döndürür.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-128">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>  
  
     <span data-ttu-id="4b9d4-129">Aşağıdaki örnekte, `Await` ifade tek tamamlanmasını bekler, görev `WhenAll` döndürür.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-129">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="4b9d4-130">Dizisi her tamsayı indirilen bir Web sitesi uzunluğu olduğu, için ifadeyi hesaplar.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-130">The expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="4b9d4-131">Aşağıdaki kodu ekleyin `SumPageSizesAsync`, yalnızca önceki adımda eklediğiniz koddan sonra.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-131">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  <span data-ttu-id="4b9d4-132">Son olarak, <xref:System.Linq.Enumerable.Sum%2A> tüm Web siteleri uzunlukları toplamı hesaplamak için yöntem.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-132">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to calculate the sum of the lengths of all the websites.</span></span> <span data-ttu-id="4b9d4-133">Aşağıdaki satırı ekleyin `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-133">Add the following line to `SumPageSizesAsync`.</span></span>  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a><span data-ttu-id="4b9d4-134">Task.WhenAll HttpClient.GetByteArrayAsync çözüme eklemek için</span><span class="sxs-lookup"><span data-stu-id="4b9d4-134">To add Task.WhenAll to the HttpClient.GetByteArrayAsync solution</span></span>  
  
1.  <span data-ttu-id="4b9d4-135">Aşağıdaki sürümü eklemek `ProcessURLAsync` da geliştirilmiş ikinci uygulamaya [izlenecek yol: Web kullanarak zaman uyumsuz ve bekleme (Visual Basic) tarafından erişme](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="4b9d4-135">Add the following version of `ProcessURLAsync` to the second application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="4b9d4-136">Koddan yüklediyseniz [Geliştirici kod örnekleri](http://go.microsoft.com/fwlink/?LinkId=255191)AsyncWalkthrough_HttpClient projesini açın ve ardından ekleyin `ProcessURLAsync` MainWindow.xaml.vb dosyasına kayıt yapar.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-136">If you downloaded the code from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191), open the AsyncWalkthrough_HttpClient project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>  
  
    -   <span data-ttu-id="4b9d4-137">Kod gözden geçirme tamamlayarak geliştirdiyseniz eklemek `ProcessURLAsync` kullanan uygulama için `HttpClient.GetByteArrayAsync` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-137">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that uses the `HttpClient.GetByteArrayAsync` method.</span></span> <span data-ttu-id="4b9d4-138">Bu uygulama için MainWindow.xaml.vb "Tam kod örnekleri gelen izlenecek yolu" bölümündeki ikinci örneğe dosyasıdır.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-138">The MainWindow.xaml.vb file for this application is the second example in the "Complete Code Examples from the Walkthrough" section.</span></span>  
  
     <span data-ttu-id="4b9d4-139">`ProcessURLAsync` Yöntemi birleştirir gövdesini Eylemler `For Each` içinde döngü `SumPageSizesAsync` özgün izlenecek adımları.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-139">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="4b9d4-140">Metodu zaman uyumsuz olarak bir bayt dizisi olarak belirtilen bir Web sitesi içeriğini indirir ve ardından görüntüler ve bayt dizisi uzunluğunu döndürür.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-140">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>  
  
     <span data-ttu-id="4b9d4-141">Tek farkı `ProcessURLAsync` yöntemidir önceki yordamda kullanımını <xref:System.Net.Http.HttpClient> örneği `client`.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-141">The only difference from the `ProcessURLAsync` method in the previous procedure is the use of the <xref:System.Net.Http.HttpClient> instance, `client`.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  <span data-ttu-id="4b9d4-142">Out yorum yapmak veya silme `For Each` içinde döngü `SumPageSizesAsync`, aşağıdaki kodda gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-142">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>  
  
    ```vb  
    'Dim total = 0   
    'For Each url In urlList   
    '    ' GetByteArrayAsync returns a task. At completion, the task   
    '    ' produces a byte array.   
    '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)   
  
    '    ' The following two lines can replace the previous assignment statement.   
    '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)   
    '    'Dim urlContents As Byte() = Await getContentsTask   
  
    '    DisplayResults(url, urlContents)   
  
    '    ' Update the total.   
    '    total += urlContents.Length   
    'Next  
    ```  
  
3.  <span data-ttu-id="4b9d4-143">Tanımlayan bir [sorgu](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) , tarafından çalıştırıldığında <xref:System.Linq.Enumerable.ToArray%2A> yöntemi, her Web sitesi içeriğini indirme görevleri koleksiyonu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-143">Define a [query](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="4b9d4-144">Sorgu değerlendirildiğinde görevleri başlatılır.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-144">The tasks are started when the query is evaluated.</span></span>  
  
     <span data-ttu-id="4b9d4-145">Yöntemine aşağıdaki kodu ekleyin `SumPageSizesAsync` bildirimi sonra `client` ve `urlList`.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-145">Add the following code to method `SumPageSizesAsync` after the declaration of `client` and `urlList`.</span></span>  
  
    ```vb  
    ' Create a query.  
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url, client)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  <span data-ttu-id="4b9d4-146">Ardından, uygulama `Task.WhenAll` görevleri koleksiyonu için `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-146">Next, apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="4b9d4-147">`Task.WhenAll`görevlerin koleksiyonundaki tüm görevler tamamlandığında bittikten tek bir görev döndürür.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-147">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>  
  
     <span data-ttu-id="4b9d4-148">Aşağıdaki örnekte, `Await` ifade tek tamamlanmasını bekler, görev `WhenAll` döndürür.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-148">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="4b9d4-149">Tamamlandığında, `Await` dizisi her tamsayı indirilen bir Web sitesi uzunluğu olduğu, için ifadeyi hesaplar.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-149">When complete, the `Await` expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="4b9d4-150">Aşağıdaki kodu ekleyin `SumPageSizesAsync`, yalnızca önceki adımda eklediğiniz koddan sonra.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-150">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  <span data-ttu-id="4b9d4-151">Son olarak, <xref:System.Linq.Enumerable.Sum%2A> tüm Web siteleri uzunlukları toplamını almak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-151">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to get the sum of the lengths of all the websites.</span></span> <span data-ttu-id="4b9d4-152">Aşağıdaki satırı ekleyin `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-152">Add the following line to `SumPageSizesAsync`.</span></span>  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-test-the-taskwhenall-solutions"></a><span data-ttu-id="4b9d4-153">Task.WhenAll çözümleri test etmek için</span><span class="sxs-lookup"><span data-stu-id="4b9d4-153">To test the Task.WhenAll solutions</span></span>  
  
-   <span data-ttu-id="4b9d4-154">Programı çalıştırmak için F5 tuşuna ya da çözüm için seçin ve ardından **Başlat** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-154">For either solution, choose the F5 key to run the program, and then choose the **Start** button.</span></span> <span data-ttu-id="4b9d4-155">Çıkış zaman uyumsuz çözümlerinde çıktısını benzemelidir [izlenecek yol: Web kullanarak zaman uyumsuz ve bekleme (Visual Basic) tarafından erişme](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="4b9d4-155">The output should resemble the output from the async solutions in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="4b9d4-156">Ancak, Web sitelerinin her zaman farklı bir sırada görüntülendiğine dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-156">However, notice that the websites appear in a different order each time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b9d4-157">Örnek</span><span class="sxs-lookup"><span data-stu-id="4b9d4-157">Example</span></span>  
 <span data-ttu-id="4b9d4-158">Aşağıdaki kod kullanan projeye uzantıları gösterir `GetURLContentsAsync` web sunucusundan içerik indirmek için yöntem.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-158">The following code shows the extensions to the project that uses the `GetURLContentsAsync` method to download content from the web.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        ' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' Create a query.   
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url)  
  
        ' Use ToArray to execute the query and start the download tasks.  
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' You can do other work here before awaiting.  
  
        ' Await the completion of all the running tasks.  
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
        '' The previous line is equivalent to the following two statements.  
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
        'Dim lengths As Integer() = Await whenAllTask  
  
        Dim total = lengths.Sum()  
  
        'Dim total = 0  
        'For Each url In urlList  
  
        '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
        '    ' The previous line abbreviates the following two assignment statements.  
  
        '    ' GetURLContentsAsync returns a task. At completion, the task  
        '    ' produces a byte array.  
        '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
        '    'Dim urlContents As Byte() = Await getContentsTask  
  
        '    DisplayResults(url, urlContents)  
  
        '    ' Update the total.  
        '    total += urlContents.Length  
        'NextNext  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    ' The actions from the foreach loop are moved to this async method.  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        Using response As WebResponse = Await webReq.GetResponseAsync()  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                ' CopyToAsync returns a Task, not a Task<T>.  
                Await responseStream.CopyToAsync(content)  
            End Using  
        End Using  
  
        ' Return the result as a byte array.  
        Return content.ToArray()  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="example"></a><span data-ttu-id="4b9d4-159">Örnek</span><span class="sxs-lookup"><span data-stu-id="4b9d4-159">Example</span></span>  
 <span data-ttu-id="4b9d4-160">Aşağıdaki kod bir yöntem projesine uzantıları gösterir `HttpClient.GetByteArrayAsync` web sunucusundan içerik indirmek için.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-160">The following code shows the extensions to the project that uses method `HttpClient.GetByteArrayAsync` to download content from the web.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        '' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Declare an HttpClient object and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' Create a query.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client)  
  
        ' Use ToArray to execute the query and start the download tasks.  
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' You can do other work here before awaiting.  
  
        ' Await the completion of all the running tasks.  
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
        '' The previous line is equivalent to the following two statements.  
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
        'Dim lengths As Integer() = Await whenAllTask  
  
        Dim total = lengths.Sum()  
  
        ''<snippet7>  
        'Dim total = 0  
        'For Each url In urlList  
        '    ' GetByteArrayAsync returns a task. At completion, the task  
        '    ' produces a byte array.  
        '    '<snippet31>  
        '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
        '    '</snippet31>  
  
        '    ' The following two lines can replace the previous assignment statement.  
        '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)  
        '    'Dim urlContents As Byte() = Await getContentsTask  
  
        '    DisplayResults(url, urlContents)  
  
        '    ' Update the total.  
        '    total += urlContents.Length  
        'NextNext  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://www.msdn.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b9d4-161">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4b9d4-161">See Also</span></span>  
 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="4b9d4-162">İzlenecek yol: Async kullanarak Web'e erişme ve bekleme (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b9d4-162">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)