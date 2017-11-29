---
title: "Nasıl yapılır: Sorgu kalıcı olmayan örnekleri için"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 294019b1-c1a7-4b81-a14f-b47c106cd723
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7c83e9364fa599d4356b69fe93ae3eaaa618c2f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-query-for-non-persisted-instances"></a><span data-ttu-id="0e756-102">Nasıl yapılır: Sorgu kalıcı olmayan örnekleri için</span><span class="sxs-lookup"><span data-stu-id="0e756-102">How to: Query for Non-persisted Instances</span></span>
<span data-ttu-id="0e756-103">Bir hizmetin yeni bir örneğini oluşturulur ve hizmet tanımlı SQL iş akışı örneği deposuna davranışı vardır, hizmet ana bilgisayarı ilk giriş o hizmet örneği için örnek deposunda oluşturur.</span><span class="sxs-lookup"><span data-stu-id="0e756-103">When a new instance of a service is created and the service has the SQL Workflow Instance Store behavior defined, the service host creates a initial entry for that service instance in the instance store.</span></span> <span data-ttu-id="0e756-104">Hizmet örneği ilk kez ediyorsa, daha sonra etkinleştirme, kurtarma ve denetim için gerekli olan ek veri birlikte geçerli örneğin durumu SQL iş akışı örneği deposuna davranışı depolar.</span><span class="sxs-lookup"><span data-stu-id="0e756-104">Subsequently when the service instance persists for the first time, the SQL Workflow Instance Store behavior stores the current instance state together with additional data that is required for activation, recovery, and control.</span></span>  
  
 <span data-ttu-id="0e756-105">İlk giriş örneği oluşturulduktan sonra bir örneği kalıcı yapılmaz, hizmet örneği kalıcı olmayan durumda olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="0e756-105">If an instance is not persisted after the initial entry for the instance is created, the service instance is said to be in the non-persisted state.</span></span> <span data-ttu-id="0e756-106">Tüm kalıcı hizmet örnekleri sorgulanan ve denetlenir.</span><span class="sxs-lookup"><span data-stu-id="0e756-106">All the persisted service instances can be queried and controlled.</span></span> <span data-ttu-id="0e756-107">Kalıcı olmayan hizmet örnekleri sorgulanan denetlenen ne.</span><span class="sxs-lookup"><span data-stu-id="0e756-107">Non-persisted service instances can neither be queried nor controlled.</span></span> <span data-ttu-id="0e756-108">Kalıcı olmayan bir örnek işlenmeyen bir özel durum nedeniyle askıya alınırsa sorgulanabilir ancak değil denetlenir.</span><span class="sxs-lookup"><span data-stu-id="0e756-108">If a non-persisted instance is suspended due to an unhandled exception it can be queried but not controlled.</span></span>  
  
 <span data-ttu-id="0e756-109">Kalıcı olmayan bir durumda aşağıdaki senaryolarda henüz kalıcı dayanıklı hizmet örnekleri kalır:</span><span class="sxs-lookup"><span data-stu-id="0e756-109">Durable service instances that are not yet persisted remain in a non-persisted state in the following scenarios:</span></span>  
  
-   <span data-ttu-id="0e756-110">Örneği ilk kez kalıcı önce Hizmet Konağı çöküyor.</span><span class="sxs-lookup"><span data-stu-id="0e756-110">The service host crashes before the instance persisted for the first time.</span></span> <span data-ttu-id="0e756-111">İlk giriş örneği için örnek deposunda kalır.</span><span class="sxs-lookup"><span data-stu-id="0e756-111">The initial entry for the instance remains in the instance store.</span></span> <span data-ttu-id="0e756-112">Örnek, kurtarılabilir değil.</span><span class="sxs-lookup"><span data-stu-id="0e756-112">The instance is not recoverable.</span></span> <span data-ttu-id="0e756-113">Bağlantılı bir ileti alınırsa örneği yeniden etkin hale gelir.</span><span class="sxs-lookup"><span data-stu-id="0e756-113">If a correlated message arrives, the instance becomes active again.</span></span>  
  
-   <span data-ttu-id="0e756-114">İlk kez kalıcı önce örneği işlenmeyen bir özel durum karşılaşır.</span><span class="sxs-lookup"><span data-stu-id="0e756-114">The instance experiences an unhandled exception before it persisted for the first time.</span></span> <span data-ttu-id="0e756-115">Aşağıdaki senaryolar ortaya</span><span class="sxs-lookup"><span data-stu-id="0e756-115">The following scenarios arise</span></span>  
  
    -   <span data-ttu-id="0e756-116">Varsa değerini **UnhandledExceptionAction** özelliği ayarlanmış **Abandon**, hizmet dağıtım bilgileri için örnek deposuna yazılır ve bellekten bir örneğidir.</span><span class="sxs-lookup"><span data-stu-id="0e756-116">If the value of the **UnhandledExceptionAction** property is set to **Abandon**, the service deployment information is written to the instance store and the instance is unloaded from memory.</span></span> <span data-ttu-id="0e756-117">Örnek Kalıcılık veritabanında kalıcı olmayan durumda kalır.</span><span class="sxs-lookup"><span data-stu-id="0e756-117">The instance remains in non-persisted state in the persistence database.</span></span>  
  
    -   <span data-ttu-id="0e756-118">Varsa değerini **UnhandledExceptionAction** özelliği ayarlanmış **AbandonAndSuspsend**, hizmet dağıtım bilgileri Kalıcılık veritabanına yazılır ve örnek durumu içinayarlandı **Askıya**.</span><span class="sxs-lookup"><span data-stu-id="0e756-118">If the value of the **UnhandledExceptionAction** property is set to **AbandonAndSuspsend**, the service deployment information is written to the persistence database and the instance state is set to **Suspended**.</span></span> <span data-ttu-id="0e756-119">Örnek, iptal, sona erdi veya sürdürülemez.</span><span class="sxs-lookup"><span data-stu-id="0e756-119">The instance cannot be resumed, canceled, or terminated.</span></span> <span data-ttu-id="0e756-120">Hizmet ana bilgisayarı örneği henüz kalıcı kurmadı ve bu nedenle veritabanı girişi örneği için tam değil çünkü yüklenemez.</span><span class="sxs-lookup"><span data-stu-id="0e756-120">The service host cannot load the instance because the instance hasn't persisted yet and, hence the database entry for the instance is not complete.</span></span>  
  
    -   <span data-ttu-id="0e756-121">Varsa değerini **UnhandledExceptionAction** özelliği ayarlanmış **iptal** veya **Sonlandır**, hizmet dağıtım bilgileri için örnek deposuna yazılır ve Örnek durumu ayarlanmış **tamamlandı**.</span><span class="sxs-lookup"><span data-stu-id="0e756-121">If the value of the **UnhandledExceptionAction** property is set to **Cancel** or **Terminate**, the service deployment information is written to the instance store and the instance state is set to **Completed**.</span></span>  
  
 <span data-ttu-id="0e756-122">Aşağıdaki bölümler SQL Kalıcılık veritabanında kalıcı olmayan örneklerini bulmak ve bu örnekler veritabanından silmek için örnek sorgular sağlar.</span><span class="sxs-lookup"><span data-stu-id="0e756-122">The following sections provide sample queries to find non-persisted instances in the SQL persistence database and to delete these instances from the database.</span></span>  
  
## <a name="to-find-all-instances-not-persisted-yet"></a><span data-ttu-id="0e756-123">Değil tüm örneklerini bulmak için henüz kalıcı</span><span class="sxs-lookup"><span data-stu-id="0e756-123">To find all instances not persisted yet</span></span>  
 <span data-ttu-id="0e756-124">Aşağıdaki SQL sorgusunu kimliği ve oluşturulması zaman içinde kalıcı olmayan tüm örnekleri için henüz Kalıcılık veritabanına döndürür.</span><span class="sxs-lookup"><span data-stu-id="0e756-124">The following SQL query returns the ID and creation time for all instances that are not persisted in to the persistence database yet.</span></span>  
  
```  
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0;  
```  
  
## <a name="to-find-all-instances-not-persisted-yet-and-also-not-loaded"></a><span data-ttu-id="0e756-125">Tüm örneklerini henüz kalıcı değildir ve ayrıca yüklenmedi bulmak için</span><span class="sxs-lookup"><span data-stu-id="0e756-125">To find all instances not persisted yet and also not loaded</span></span>  
 <span data-ttu-id="0e756-126">Aşağıdaki SQL sorgusunu kalıcı değildir ve ayrıca yüklü olmayan tüm örnekleri için kimliği ve oluşturma saati döndürür.</span><span class="sxs-lookup"><span data-stu-id="0e756-126">The following SQL query returns ID and creation time for all instances that are not persisted and also are not loaded.</span></span>  
  
```  
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and CurrentMachine is NULL;  
```  
  
## <a name="to-find-all-suspended-instances-not-persisted-yet"></a><span data-ttu-id="0e756-127">Askıya alınmış tüm örneklerini bulamaz için henüz kalıcı</span><span class="sxs-lookup"><span data-stu-id="0e756-127">To find all suspended instances not persisted yet</span></span>  
 <span data-ttu-id="0e756-128">Aşağıdaki SQL sorgusunu kimliği, oluşturulma zamanı, askıya neden ve askıya özel durum adı kalıcı değildir tüm örnekleri için ve ayrıca askıya alınmış durumda döndürür.</span><span class="sxs-lookup"><span data-stu-id="0e756-128">The following SQL query returns ID, creation time, suspension reason, and suspension exception name for all instances that are not persisted and also in a suspended state.</span></span>  
  
```  
select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and IsSuspended = 1;  
```  
  
## <a name="to-delete-non-persisted-instances-from-the-persistence-database"></a><span data-ttu-id="0e756-129">Kalıcı olmayan örnekleri Kalıcılık veritabanından silmek için</span><span class="sxs-lookup"><span data-stu-id="0e756-129">To delete non-persisted instances from the persistence database</span></span>  
 <span data-ttu-id="0e756-130">Düzenli aralıklarla kalıcı olmayan örnekleri için örnek deposuna denetleyin ve örnek bir bağıntılı iletisi almaz eminseniz örnekleri örneği Mağazası'ndan kaldırın gerekir.</span><span class="sxs-lookup"><span data-stu-id="0e756-130">You should periodically check the instance store for non-persisted instances and remove instances from the instance store if you are sure that the instance will not receive a correlated message.</span></span> <span data-ttu-id="0e756-131">Örneğin, örnek veritabanında birkaç ay olmuştur ve iş akışı genellikle birkaç gün ömrü olduğunu biliyorsanız, bunun çöken başlatılmamış bir örneği olduğunu varsaymak güvenli olacaktır.</span><span class="sxs-lookup"><span data-stu-id="0e756-131">For example, if the instance has been in the database for several months and you know that the workflow typically has a lifetime of a few days, it would be safe to assume that this is an uninitialized instance that had crashed.</span></span>  
  
 <span data-ttu-id="0e756-132">Genel olarak, askıya değil ya da yüklenemeyen kalıcı olmayan örneklerini silmek güvenlidir.</span><span class="sxs-lookup"><span data-stu-id="0e756-132">In general, it is safe to delete non-persisted instances that are not suspended or not loaded.</span></span> <span data-ttu-id="0e756-133">Değil silmelisiniz **tüm** Bu örnek kümesi yalnızca oluşturulur ancak olmayan örnekleri içerdiğinden kalıcı olmayan örnekleri henüz kalıcı.</span><span class="sxs-lookup"><span data-stu-id="0e756-133">You should not delete **all** the non-persisted instances because this instance set includes instances that are just created but are not persisted yet.</span></span> <span data-ttu-id="0e756-134">Yalnızca bir özel durum örneği yüklenmiş olan iş akışı hizmeti ana bilgisayarı neden olduğundan kalmış kalıcı olmayan örnekleri veya örneğin kendisini bir özel duruma neden silmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="0e756-134">You should only delete non-persisted instances that are left over because the workflow service host that had the instance loaded caused an exception or the instance itself caused an exception.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="0e756-135">Kalıcı olmayan örneklerini örneği Mağazası'ndan silme deposunun boyutunu azaltır ve depolama işlemlerinin performansını artırabilir.</span><span class="sxs-lookup"><span data-stu-id="0e756-135">Deleting non-persisted instances from the instance store decreases the size of the store and may improve the performance of store operations.</span></span>