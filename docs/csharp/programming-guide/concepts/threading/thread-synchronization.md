---
title: "İş parçacığı eşitleme (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e42b1be6-c93c-479f-a148-be0759f1a4e1
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2b51775eac5221ec8c723d89323d1f4f542d2453
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="thread-synchronization-c"></a><span data-ttu-id="55a60-102">İş parçacığı eşitleme (C#)</span><span class="sxs-lookup"><span data-stu-id="55a60-102">Thread Synchronization (C#)</span></span>
<span data-ttu-id="55a60-103">Aşağıdaki bölümlerde, özellikleri ve kaynakları birden çok iş parçacıklı uygulamalarda erişimi eşitlemek için kullanılan sınıflar açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="55a60-103">The following sections describe features and classes that can be used to synchronize access to resources in multithreaded applications.</span></span>  
  
 <span data-ttu-id="55a60-104">Bir uygulamada birden çok iş parçacığı kullanmanın avantajları her iş parçacığı zaman uyumsuz olarak yürütür biridir.</span><span class="sxs-lookup"><span data-stu-id="55a60-104">One of the benefits of using multiple threads in an application is that each thread executes asynchronously.</span></span> <span data-ttu-id="55a60-105">Windows uygulamaları için bu uygulama penceresi arka planda gerçekleştirilecek uzun süren görevler sağlar ve denetimleri yanıt verebilir durumda kalır.</span><span class="sxs-lookup"><span data-stu-id="55a60-105">For Windows applications, this allows time-consuming tasks to be performed in the background while the application window and controls remain responsive.</span></span> <span data-ttu-id="55a60-106">Uygulamaları, çoklu iş parçacığı kullanımı sunucusu için farklı bir iş parçacığıyla her gelen istek işleme yeteneği sağlar.</span><span class="sxs-lookup"><span data-stu-id="55a60-106">For server applications, multithreading provides the ability to handle each incoming request with a different thread.</span></span> <span data-ttu-id="55a60-107">Önceki istek tam memnun olsaydı kadar Aksi durumda, her yeni isteği bakım değil.</span><span class="sxs-lookup"><span data-stu-id="55a60-107">Otherwise, each new request would not get serviced until the previous request had been fully satisfied.</span></span>  
  
 <span data-ttu-id="55a60-108">Ancak, zaman uyumsuz yapısı dosya tanıtıcısı, ağ bağlantıları ve bellek gibi kaynaklara erişmek iş parçacığı anlamına gelir, Eşgüdümlü olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="55a60-108">However, the asynchronous nature of threads means that access to resources such as file handles, network connections, and memory must be coordinated.</span></span> <span data-ttu-id="55a60-109">Aksi durumda, iki veya daha fazla iş parçacığı aynı anda, diğerinin eylemlerini her farkında aynı kaynak erişebilir.</span><span class="sxs-lookup"><span data-stu-id="55a60-109">Otherwise, two or more threads could access the same resource at the same time, each unaware of the other's actions.</span></span> <span data-ttu-id="55a60-110">Beklenmeyen veri bozulması sonucudur.</span><span class="sxs-lookup"><span data-stu-id="55a60-110">The result is unpredictable data corruption.</span></span>  
  
 <span data-ttu-id="55a60-111">Tam Sayı sayısal veri türleri üzerinde basit işlemleri için iş parçacıklarını eşitleme üyeleriyle gerçekleştirilebilir <xref:System.Threading.Interlocked> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="55a60-111">For simple operations on integral numeric data types, synchronizing threads can be accomplished with members of the <xref:System.Threading.Interlocked> class.</span></span> <span data-ttu-id="55a60-112">İçin tüm diğer veri türleri ve iş parçacığı güvenli olmayan kaynakları, çoklu iş parçacığı kullanımı yalnızca güvenli bir şekilde yapıları bu konudaki kullanılarak gerçekleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="55a60-112">For all other data types and non thread-safe resources, multithreading can only be safely performed using the constructs in this topic.</span></span>  
  
 <span data-ttu-id="55a60-113">Birden çok iş parçacıklı programlama hakkında arka plan bilgileri için bkz:</span><span class="sxs-lookup"><span data-stu-id="55a60-113">For background information on multithreaded programming, see:</span></span>  
  
-   [<span data-ttu-id="55a60-114">Yönetilen iş parçacığı oluşturma temelleri</span><span class="sxs-lookup"><span data-stu-id="55a60-114">Managed Threading Basics</span></span>](../../../../standard/threading/managed-threading-basics.md)  
  
-   [<span data-ttu-id="55a60-115">İş parçacığı kullanma ve iş parçacığı oluşturma</span><span class="sxs-lookup"><span data-stu-id="55a60-115">Using Threads and Threading</span></span>](../../../../standard/threading/using-threads-and-threading.md)  
  
-   [<span data-ttu-id="55a60-116">Yönetilen iş parçacığı oluşturma en iyi uygulamalar</span><span class="sxs-lookup"><span data-stu-id="55a60-116">Managed Threading Best Practices</span></span>](../../../../standard/threading/managed-threading-best-practices.md)  
  
## <a name="the-lock-keyword"></a><span data-ttu-id="55a60-117">Lock anahtar sözcüğü</span><span class="sxs-lookup"><span data-stu-id="55a60-117">The lock Keyword</span></span>  
 <span data-ttu-id="55a60-118">C# `lock` deyimi bir kod bloğu kesintisiz tamamlama çalıştığından emin olmak için kullanılabilir diğer iş parçacıkları tarafından.</span><span class="sxs-lookup"><span data-stu-id="55a60-118">The C# `lock` statement can be used to ensure that a block of code runs to completion without interruption by other threads.</span></span> <span data-ttu-id="55a60-119">Bu kod bloğu boyunca belirli bir nesne için karşılıklı dışlama kilidi elde ederek gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="55a60-119">This is accomplished by obtaining a mutual-exclusion lock for a given object for the duration of the code block.</span></span>  
  
 <span data-ttu-id="55a60-120">A `lock` deyimi bir nesne bir bağımsız değişken olarak verilen ve aynı anda yalnızca bir iş parçacığı tarafından yürütülecek olan kod bloğu tarafından izlenir.</span><span class="sxs-lookup"><span data-stu-id="55a60-120">A `lock` statement is given an object as an argument, and is followed by a code block that is to be executed by only one thread at a time.</span></span> <span data-ttu-id="55a60-121">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="55a60-121">For example:</span></span>  
  
```csharp  
public class TestThreading  
{  
    private System.Object lockThis = new System.Object();  
  
    public void Process()  
    {  
  
        lock (lockThis)  
        {  
            // Access thread-sensitive resources.  
        }  
    }  
  
}  
```  
  
 <span data-ttu-id="55a60-122">Sağlanan bağımsız değişken `lock` anahtar sözcüğü bir başvuru türüne göre bir nesne olmalıdır ve kilidi kapsamını tanımlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="55a60-122">The argument provided to the `lock` keyword must be an object based on a reference type, and is used to define the scope of the lock.</span></span> <span data-ttu-id="55a60-123">Yukarıdaki örnekte, kilit kapsamı çünkü bu işleve sınırlıdır nesnesine başvuru `lockThis` dışında işlevi yok.</span><span class="sxs-lookup"><span data-stu-id="55a60-123">In the example above, the lock scope is limited to this function because no references to the object `lockThis` exist outside the function.</span></span> <span data-ttu-id="55a60-124">Böyle bir başvuru yoksa, kilit kapsamı bu nesneye genişletir.</span><span class="sxs-lookup"><span data-stu-id="55a60-124">If such a reference did exist, lock scope would extend to that object.</span></span> <span data-ttu-id="55a60-125">NET olarak söylemek sağlanan nesne, yalnızca birden çok iş parçacığı arasında rastgele bir örneği olabilir paylaşılan kaynağı benzersiz şekilde tanımlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="55a60-125">Strictly speaking, the object provided is used solely to uniquely identify the resource being shared among multiple threads, so it can be an arbitrary class instance.</span></span> <span data-ttu-id="55a60-126">Uygulamada, ancak bu nesne genellikle hangi iş parçacığı için eşitleme gereklidir kaynak temsil eder.</span><span class="sxs-lookup"><span data-stu-id="55a60-126">In practice, however, this object usually represents the resource for which thread synchronization is necessary.</span></span> <span data-ttu-id="55a60-127">Örneğin, bir kapsayıcı nesne birden çok iş parçacığı tarafından kullanılacak ise kilitlemek için kapsayıcı sonra geçirilebilir ve kilidi aşağıdaki eşitlenmiş kod bloğu kapsayıcı erişir.</span><span class="sxs-lookup"><span data-stu-id="55a60-127">For example, if a container object is to be used by multiple threads, then the container can be passed to lock, and the synchronized code block following the lock would access the container.</span></span> <span data-ttu-id="55a60-128">Başka bir iş parçacığı kilitler sürece aynı erişmeden önce içerecek ardından nesneye erişimi güvenli bir şekilde eşitlenir.</span><span class="sxs-lookup"><span data-stu-id="55a60-128">As long as other threads locks on the same contain before accessing it, then access to the object is safely synchronized.</span></span>  
  
 <span data-ttu-id="55a60-129">Genellikle, üzerinde kilitleme önlemek en iyisidir bir `public` türü veya nesne örneklerini uygulamanızı denetiminin dışındadır.</span><span class="sxs-lookup"><span data-stu-id="55a60-129">Generally, it is best to avoid locking on a `public` type, or on object instances beyond the control of your application.</span></span> <span data-ttu-id="55a60-130">Örneğin, `lock(this)` denetiminiz dışında kod nesnesi üzerinde kilit çünkü örneği genel olarak, erişilebiliyorsa sorunlu olabilir.</span><span class="sxs-lookup"><span data-stu-id="55a60-130">For example, `lock(this)` can be problematic if the instance can be accessed publicly, because code beyond your control may lock on the object as well.</span></span> <span data-ttu-id="55a60-131">Bu, burada bu sürüm için aynı nesne iki veya daha fazla iş parçacığı bekleyin kilitlenme durumlar oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="55a60-131">This could create deadlock situations where two or more threads wait for the release of the same object.</span></span> <span data-ttu-id="55a60-132">Bir nesne aksine bir genel veri türünde kilitleme aynı nedenden dolayı sorunlara neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="55a60-132">Locking on a public data type, as opposed to an object, can cause problems for the same reason.</span></span> <span data-ttu-id="55a60-133">Değişmez değer dizeleri kilitleme özellikle riskli değişmez değer dizeleri olduğundan *interned* ortak dil çalışma zamanı (CLR) tarafından.</span><span class="sxs-lookup"><span data-stu-id="55a60-133">Locking on literal strings is especially risky because literal strings are *interned* by the common language runtime (CLR).</span></span> <span data-ttu-id="55a60-134">Bunun anlamı herhangi belirli bir dizeyi bir örneği için tüm program değişmez değer, tüm sabit değeri tam aynı nesneyi temsil uygulama etki alanları, çalışan tüm iş parçacığı üzerinde.</span><span class="sxs-lookup"><span data-stu-id="55a60-134">This means that there is one instance of any given string literal for the entire program, the exact same object represents the literal in all running application domains, on all threads.</span></span> <span data-ttu-id="55a60-135">Sonuç olarak, kilit aynı içeriği bir dizeyle herhangi bir yerden uygulama işlemi kilitler bu dizeyi uygulamadaki tüm örneklerini yerleştirilmiş.</span><span class="sxs-lookup"><span data-stu-id="55a60-135">As a result, a lock placed on a string with the same contents anywhere in the application process locks all instances of that string in the application.</span></span> <span data-ttu-id="55a60-136">Sonuç olarak, değil interned özel veya korumalı üye kilitlemek en iyisidir.</span><span class="sxs-lookup"><span data-stu-id="55a60-136">As a result, it is best to lock a private or protected member that is not interned.</span></span> <span data-ttu-id="55a60-137">Bazı sınıflar, özellikle kilitleme üyeleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="55a60-137">Some classes provide members specifically for locking.</span></span> <span data-ttu-id="55a60-138"><xref:System.Array> Türü, örneğin sağlar <xref:System.Array.SyncRoot%2A>.</span><span class="sxs-lookup"><span data-stu-id="55a60-138">The <xref:System.Array> type, for example, provides <xref:System.Array.SyncRoot%2A>.</span></span> <span data-ttu-id="55a60-139">Birçok koleksiyon türleri sağlayan bir `SyncRoot` de üye.</span><span class="sxs-lookup"><span data-stu-id="55a60-139">Many collection types provide a `SyncRoot` member as well.</span></span>  
  
 <span data-ttu-id="55a60-140">Hakkında daha fazla bilgi için `lock` deyimi, aşağıdaki konulara bakın:</span><span class="sxs-lookup"><span data-stu-id="55a60-140">For more information about the `lock` statement, see the following topics:</span></span>  
  
-   [<span data-ttu-id="55a60-141">lock deyimi</span><span class="sxs-lookup"><span data-stu-id="55a60-141">lock Statement</span></span>](../../../../csharp/language-reference/keywords/lock-statement.md)  
  
-   <xref:System.Threading.Monitor>  
  
## <a name="monitors"></a><span data-ttu-id="55a60-142">İzlemeler</span><span class="sxs-lookup"><span data-stu-id="55a60-142">Monitors</span></span>  
 <span data-ttu-id="55a60-143">Gibi `lock` anahtar sözcüğü, izleyicileri birden çok iş parçacığı tarafından eşzamanlı yürütülmesini kod bloklarını engellemek.</span><span class="sxs-lookup"><span data-stu-id="55a60-143">Like the `lock` keyword, monitors prevent blocks of code from simultaneous execution by multiple threads.</span></span> <span data-ttu-id="55a60-144"><xref:System.Threading.Monitor.Enter%2A> Yöntemi aşağıdaki deyime devam etmek tek bir iş parçacığı sağlar; diğer tüm iş parçacıklarının kadar yürütme iş parçacığı çağrıları engellenen <xref:System.Threading.Monitor.Exit%2A>.</span><span class="sxs-lookup"><span data-stu-id="55a60-144">The <xref:System.Threading.Monitor.Enter%2A> method allows one and only one thread to proceed into the following statements; all other threads are blocked until the executing thread calls <xref:System.Threading.Monitor.Exit%2A>.</span></span> <span data-ttu-id="55a60-145">Bu yalnızca gibi kullanmaktır `lock` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="55a60-145">This is just like using the `lock` keyword.</span></span> <span data-ttu-id="55a60-146">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="55a60-146">For example:</span></span>  
  
```csharp  
lock (x)  
{  
    DoSomething();  
}  
```  
  
 <span data-ttu-id="55a60-147">Bu eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="55a60-147">This is equivalent to:</span></span>  
  
```csharp  
System.Object obj = (System.Object)x;  
System.Threading.Monitor.Enter(obj);  
try  
{  
    DoSomething();  
}  
finally  
{  
    System.Threading.Monitor.Exit(obj);  
}  
```  
  
 <span data-ttu-id="55a60-148">Kullanarak `lock` anahtar sözcüğü, genellikle tercih edilen kullanarak üzerinden <xref:System.Threading.Monitor> doğrudan, hem de çünkü sınıf `lock` daha kısa olduğundan ve çünkü `lock` korunan kod bile oluşturursa temel İzleyici serbest yöntem başlanmasını sağlar bir özel durum.</span><span class="sxs-lookup"><span data-stu-id="55a60-148">Using the `lock` keyword is generally preferred over using the <xref:System.Threading.Monitor> class directly, both because `lock` is more concise, and because `lock` insures that the underlying monitor is released, even if the protected code throws an exception.</span></span> <span data-ttu-id="55a60-149">Bu ile gerçekleştirilir `finally` anahtar sözcüğü olup bir özel durum bağımsız olarak kendi ilişkili kod bloğu yürütür.</span><span class="sxs-lookup"><span data-stu-id="55a60-149">This is accomplished with the `finally` keyword, which executes its associated code block regardless of whether an exception is thrown.</span></span>  
  
## <a name="synchronization-events-and-wait-handles"></a><span data-ttu-id="55a60-150">Eşitleme olayları ve bekleme tanıtıcıları</span><span class="sxs-lookup"><span data-stu-id="55a60-150">Synchronization Events and Wait Handles</span></span>  
 <span data-ttu-id="55a60-151">Kilitleme veya İzleyici kullanarak iş parçacığı duyarlı kod bloklarını eşzamanlı yürütülmesini engellemek için yararlıdır, ancak bu yapıları başka bir olay iletişim kurmak bir iş parçacığı izin vermez.</span><span class="sxs-lookup"><span data-stu-id="55a60-151">Using a lock or monitor is useful for preventing the simultaneous execution of thread-sensitive blocks of code, but these constructs do not allow one thread to communicate an event to another.</span></span> <span data-ttu-id="55a60-152">Bu gerektirir *eşitleme olayları*, iki durumlu birine sahip nesneleri olduğu iş ve beklemediğiniz iş etkinleştirmek ve iş parçacıklarını askıya almak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="55a60-152">This requires *synchronization events*, which are objects that have one of two states, signaled and un-signaled, that can be used to activate and suspend threads.</span></span> <span data-ttu-id="55a60-153">İş parçacıkları unsignaled bir eşitleme olay beklemeye yapılan tarafından askıya alınabilir ve olay işaret durumuna değiştirerek etkinleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="55a60-153">Threads can be suspended by being made to wait on a synchronization event that is unsignaled, and can be activated by changing the event state to signaled.</span></span> <span data-ttu-id="55a60-154">Bir iş parçacığı zaten işareti olaya bekleyin kullanmaya çalışırsa, sonra iş parçacığı gecikme olmadan yürütmeye devam eder.</span><span class="sxs-lookup"><span data-stu-id="55a60-154">If a thread attempts to wait on an event that is already signaled, then the thread continues to execute without delay.</span></span>  
  
 <span data-ttu-id="55a60-155">Eşitleme olayları iki tür vardır: <xref:System.Threading.AutoResetEvent>, ve <xref:System.Threading.ManualResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="55a60-155">There are two kinds of synchronization events: <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.ManualResetEvent>.</span></span> <span data-ttu-id="55a60-156">Bunlar yalnızca, farklı <xref:System.Threading.AutoResetEvent> değişikliklerden işaret çok unsignaled otomatik olarak herhangi bir zaman, bir iş parçacığı etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="55a60-156">They differ only in that <xref:System.Threading.AutoResetEvent> changes from signaled to unsignaled automatically any time it activates a thread.</span></span> <span data-ttu-id="55a60-157">Buna karşılık, bir <xref:System.Threading.ManualResetEvent> herhangi bir sayıda iş durumuna göre etkinleştirilmesi için iş parçacığı sağlar ve yalnızca bir unsignaled döner duruma kendi <xref:System.Threading.EventWaitHandle.Reset%2A> yöntemi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="55a60-157">Conversely, a <xref:System.Threading.ManualResetEvent> allows any number of threads to be activated by its signaled state, and will only revert to an unsignaled state when its <xref:System.Threading.EventWaitHandle.Reset%2A> method is called.</span></span>  
  
 <span data-ttu-id="55a60-158">İş parçacığı arama bekleme yöntemlerden biri tarafından olaylarına gibi beklenecek yapılabilir <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, veya <xref:System.Threading.WaitHandle.WaitAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="55a60-158">Threads can be made to wait on events by calling one of the wait methods, such as <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, or <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span> <span data-ttu-id="55a60-159"><xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType>tek bir olay işaret hale beklemek için iş parçacığı neden <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> bir veya daha fazla belirtilen olayları işaret hale kadar bir iş parçacığı engeller ve <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> tüm belirtilen olaylar işaret hale kadar iş parçacığı engeller.</span><span class="sxs-lookup"><span data-stu-id="55a60-159"><xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType> causes the thread to wait until a single event becomes signaled, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> blocks a thread until one or more indicated events become signaled, and <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> blocks the thread until all of the indicated events become signaled.</span></span> <span data-ttu-id="55a60-160">Bir olay işaret olur, kendi <xref:System.Threading.EventWaitHandle.Set%2A> yöntemi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="55a60-160">An event becomes signaled when its <xref:System.Threading.EventWaitHandle.Set%2A> method is called.</span></span>  
  
 <span data-ttu-id="55a60-161">Aşağıdaki örnekte, bir iş parçacığı oluşturulur ve başlatan `Main` işlevi.</span><span class="sxs-lookup"><span data-stu-id="55a60-161">In the following example, a thread is created and started by the `Main` function.</span></span> <span data-ttu-id="55a60-162">Bir olay kullanarak yeni bir iş parçacığı bekler <xref:System.Threading.WaitHandle.WaitOne%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="55a60-162">The new thread waits on an event using the <xref:System.Threading.WaitHandle.WaitOne%2A> method.</span></span> <span data-ttu-id="55a60-163">Olay yürütüyor birincil iş parçacığı tarafından işaret hale kadar iş parçacığı askıya `Main` işlevi.</span><span class="sxs-lookup"><span data-stu-id="55a60-163">The thread is suspended until the event becomes signaled by the primary thread that is executing the `Main` function.</span></span> <span data-ttu-id="55a60-164">Olay işaret hale sonra yardımcı iş parçacığı döndürür.</span><span class="sxs-lookup"><span data-stu-id="55a60-164">Once the event becomes signaled, the auxiliary thread returns.</span></span> <span data-ttu-id="55a60-165">Bu durumda, olay yalnızca bir iş parçacığı etkinleştirme için ya da kullanıldığından <xref:System.Threading.AutoResetEvent> veya <xref:System.Threading.ManualResetEvent> sınıfları kullanılabilirdi.</span><span class="sxs-lookup"><span data-stu-id="55a60-165">In this case, because the event is only used for one thread activation, either the <xref:System.Threading.AutoResetEvent> or <xref:System.Threading.ManualResetEvent> classes could be used.</span></span>  
  
```csharp  
using System;  
using System.Threading;  
  
class ThreadingExample  
{  
    static AutoResetEvent autoEvent;  
  
    static void DoWork()  
    {  
        Console.WriteLine("   worker thread started, now waiting on event...");  
        autoEvent.WaitOne();  
        Console.WriteLine("   worker thread reactivated, now exiting...");  
    }  
  
    static void Main()  
    {  
        autoEvent = new AutoResetEvent(false);  
  
        Console.WriteLine("main thread starting worker thread...");  
        Thread t = new Thread(DoWork);  
        t.Start();  
  
        Console.WriteLine("main thread sleeping for 1 second...");  
        Thread.Sleep(1000);  
  
        Console.WriteLine("main thread signaling worker thread...");  
        autoEvent.Set();  
    }  
}  
```  
  
## <a name="mutex-object"></a><span data-ttu-id="55a60-166">Mutex nesnesi</span><span class="sxs-lookup"><span data-stu-id="55a60-166">Mutex Object</span></span>  
 <span data-ttu-id="55a60-167">A *mutex* bir izleme; benzer, eşzamanlı yürütülmesini kod bloğunu birden çok iş parçacığı tarafından aynı anda engeller.</span><span class="sxs-lookup"><span data-stu-id="55a60-167">A *mutex* is similar to a monitor; it prevents the simultaneous execution of a block of code by more than one thread at a time.</span></span> <span data-ttu-id="55a60-168">Aslında, adı "mutex" kısaltılmış "birbirini dışlayan." terimi biçimidir</span><span class="sxs-lookup"><span data-stu-id="55a60-168">In fact, the name "mutex" is a shortened form of the term "mutually exclusive."</span></span> <span data-ttu-id="55a60-169">İzleyicilerin aksine, ancak bir mutex iş parçacığı işlemler arasında eşitlemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="55a60-169">Unlike monitors, however, a mutex can be used to synchronize threads across processes.</span></span> <span data-ttu-id="55a60-170">Bir mutex tarafından temsil edilen <xref:System.Threading.Mutex> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="55a60-170">A mutex is represented by the <xref:System.Threading.Mutex> class.</span></span>  
  
 <span data-ttu-id="55a60-171">İşlemler arası eşitleme için kullanıldığında, bir mutex adlı bir *mutex adlı* başka bir uygulamada kullanılacak olduğundan ve bu nedenle bir genel veya statik değişken yoluyla paylaşılamaz.</span><span class="sxs-lookup"><span data-stu-id="55a60-171">When used for inter-process synchronization, a mutex is called a *named mutex* because it is to be used in another application, and therefore it cannot be shared by means of a global or static variable.</span></span> <span data-ttu-id="55a60-172">İki uygulamanın aynı mutex nesnesi erişebilmesi için bir ad verilmelidir.</span><span class="sxs-lookup"><span data-stu-id="55a60-172">It must be given a name so that both applications can access the same mutex object.</span></span>  
  
 <span data-ttu-id="55a60-173">Bir mutex içi işlem iş parçacığı eşitleme için kullanılır ancak kullanarak <xref:System.Threading.Monitor> izleyiciler .NET Framework için özellikle tasarlanmış olması nedeniyle genellikle tercih edilir ve bu nedenle daha iyi kaynak kullanımını olun.</span><span class="sxs-lookup"><span data-stu-id="55a60-173">Although a mutex can be used for intra-process thread synchronization, using <xref:System.Threading.Monitor> is generally preferred, because monitors were designed specifically for the .NET Framework and therefore make better use of resources.</span></span> <span data-ttu-id="55a60-174">Buna karşılık, <xref:System.Threading.Mutex> bir Win32 yapısı için bir sarmalayıcı sınıftır.</span><span class="sxs-lookup"><span data-stu-id="55a60-174">In contrast, the <xref:System.Threading.Mutex> class is a wrapper to a Win32 construct.</span></span> <span data-ttu-id="55a60-175">Bir İzleyici'den daha güçlü olsa da, bir mutex tarafından gerekli olandan daha pkı'ya pahalıdır birlikte çalışma geçişleri gerektirir <xref:System.Threading.Monitor> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="55a60-175">While it is more powerful than a monitor, a mutex requires interop transitions that are more computationally expensive than those required by the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="55a60-176">Bir mutex kullanma örneği için bkz: [zaman uyumu sağlayıcılar](../../../../standard/threading/mutexes.md).</span><span class="sxs-lookup"><span data-stu-id="55a60-176">For an example of using a mutex, see [Mutexes](../../../../standard/threading/mutexes.md).</span></span>  
  
## <a name="interlocked-class"></a><span data-ttu-id="55a60-177">Interlocked sınıfı</span><span class="sxs-lookup"><span data-stu-id="55a60-177">Interlocked Class</span></span>  
 <span data-ttu-id="55a60-178">Yöntemlerini kullanabilirsiniz <xref:System.Threading.Interlocked> birden çok iş parçacığı aynı anda güncelleştirmek veya aynı değeri karşılaştırmak çalıştığınızda oluşabilecek sorunları önlemek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="55a60-178">You can use the methods of the <xref:System.Threading.Interlocked> class to prevent problems that can occur when multiple threads attempt to simultaneously update or compare the same value.</span></span> <span data-ttu-id="55a60-179">Bu sınıfı yöntemlerinin güvenle artışı sağlar, azaltma, exchange ve herhangi bir iş parçacığı değerleri Karşılaştır.</span><span class="sxs-lookup"><span data-stu-id="55a60-179">The methods of this class let you safely increment, decrement, exchange, and compare values from any thread.</span></span>  
  
## <a name="readerwriter-locks"></a><span data-ttu-id="55a60-180">ReaderWriter kilitleri</span><span class="sxs-lookup"><span data-stu-id="55a60-180">ReaderWriter Locks</span></span>  
 <span data-ttu-id="55a60-181">Bazı durumlarda, yalnızca veriler yazılırken zaman bir kaynağı kilitlemek ve birden çok istemciye veri güncelleştirilmiyor eşzamanlı olarak veri okumaya izin vermek isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="55a60-181">In some cases, you may want to lock a resource only when data is being written and permit multiple clients to simultaneously read data when data is not being updated.</span></span> <span data-ttu-id="55a60-182"><xref:System.Threading.ReaderWriterLock> Sınıfı bir iş parçacığı kaynak değiştiriyor, ancak kaynak okunurken özel olmayan erişim sağlayan bir kaynağa özel erişim zorlar.</span><span class="sxs-lookup"><span data-stu-id="55a60-182">The <xref:System.Threading.ReaderWriterLock> class enforces exclusive access to a resource while a thread is modifying the resource, but it allows non-exclusive access when reading the resource.</span></span> <span data-ttu-id="55a60-183">ReaderWriter kilitleri beklemek bile bu iş parçacığı verileri güncelleştirmek gerektiğinde değil başka bir iş parçacığı neden özel kilit kullanışlı bir alternatiftir.</span><span class="sxs-lookup"><span data-stu-id="55a60-183">ReaderWriter locks are a useful alternative to exclusive locks, which cause other threads to wait, even when those threads do not need to update data.</span></span>  
  
## <a name="deadlocks"></a><span data-ttu-id="55a60-184">Kilitlenmeleri</span><span class="sxs-lookup"><span data-stu-id="55a60-184">Deadlocks</span></span>  
 <span data-ttu-id="55a60-185">İş parçacığı eşitleme birden çok iş parçacıklı uygulamalarda çok değerli bir kaynak, ancak her zaman oluşturma tehlike bir `deadlock`, burada birden çok iş parçacığı diğer için bekliyor ve bir durmasına uygulama gelir.</span><span class="sxs-lookup"><span data-stu-id="55a60-185">Thread synchronization is invaluable in multithreaded applications, but there is always the danger of creating a `deadlock`, where multiple threads are waiting for each other and the application comes to a halt.</span></span> <span data-ttu-id="55a60-186">Kilitlenme araba dört yönlü durağında durdurulur ve her birinin diğeri için gitmek bekliyor. bir durum benzerdir.</span><span class="sxs-lookup"><span data-stu-id="55a60-186">A deadlock is analogous to a situation in which cars are stopped at a four-way stop and each person is waiting for the other to go.</span></span> <span data-ttu-id="55a60-187">Kilitlenmeler önleme önemlidir; dikkatli planlama anahtardır.</span><span class="sxs-lookup"><span data-stu-id="55a60-187">Avoiding deadlocks is important; the key is careful planning.</span></span> <span data-ttu-id="55a60-188">Genellikle, kodlama başlamadan önce birden çok iş parçacıklı uygulamalar diyagram kilitlenme durumlarda tahmin edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="55a60-188">You can often predict deadlock situations by diagramming multithreaded applications before you start coding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55a60-189">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="55a60-189">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.WaitHandle.WaitOne%2A>  
 <xref:System.Threading.WaitHandle.WaitAny%2A>  
 <xref:System.Threading.WaitHandle.WaitAll%2A>  
 <xref:System.Threading.Thread.Join%2A>  
 <xref:System.Threading.Thread.Start%2A>  
 <xref:System.Threading.Thread.Sleep%2A>  
 <xref:System.Threading.Monitor>  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading>  
 <xref:System.Threading.EventWaitHandle.Set%2A>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="55a60-190">Birden çok iş parçacıklı uygulamalar (C#)</span><span class="sxs-lookup"><span data-stu-id="55a60-190">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="55a60-191">lock deyimi</span><span class="sxs-lookup"><span data-stu-id="55a60-191">lock Statement</span></span>](../../../../csharp/language-reference/keywords/lock-statement.md)  
 [<span data-ttu-id="55a60-192">Zaman uyumu sağlayıcılar</span><span class="sxs-lookup"><span data-stu-id="55a60-192">Mutexes</span></span>](../../../../standard/threading/mutexes.md)  
 [<span data-ttu-id="55a60-193">Birbirine kenetlenmiş işlemler</span><span class="sxs-lookup"><span data-stu-id="55a60-193">Interlocked Operations</span></span>](../../../../standard/threading/interlocked-operations.md)  
 [<span data-ttu-id="55a60-194">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="55a60-194">AutoResetEvent</span></span>](../../../../standard/threading/autoresetevent.md)  
 [<span data-ttu-id="55a60-195">İçin Veri Eşitleme çoklu iş parçacığı kullanımı</span><span class="sxs-lookup"><span data-stu-id="55a60-195">Synchronizing Data for Multithreading</span></span>](../../../../standard/threading/synchronizing-data-for-multithreading.md)