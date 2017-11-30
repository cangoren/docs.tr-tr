---
title: WorkflowApplication ReadLine ana bilgisayar
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7b362be-cb42-40d7-b9ef-cfc4aed2455b
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a65ca3d3d4a787132246312e28213e71defc94ec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="workflowapplication-readline-host"></a><span data-ttu-id="a9a9a-102">WorkflowApplication ReadLine ana bilgisayar</span><span class="sxs-lookup"><span data-stu-id="a9a9a-102">WorkflowApplication ReadLine Host</span></span>
<span data-ttu-id="a9a9a-103">Bu örnek bir genel ReadLine ana bilgisayardır.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-103">This sample is a generic ReadLine host.</span></span> <span data-ttu-id="a9a9a-104">Yük ve birlikte kullanarak tüm iş akışını çalıştırma `ReadLine` etkinlik (veya bu gibi veri yer işaretleri dizelerle sürdürüldü almanız diğer etkinlikler).</span><span class="sxs-lookup"><span data-stu-id="a9a9a-104">You can load and run any workflow using the included `ReadLine` activity (or other activities like it that get data from bookmarks resumed with strings).</span></span> <span data-ttu-id="a9a9a-105">Çıktı `WriteLine` etkinlik veya herhangi bir şeyi yazma <xref:System.Activities.Statements.WriteLine.TextWriter%2A> uzantısı konak penceresine yönlendirilir.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-105">Output from the `WriteLine` activity or anything writing to the <xref:System.Activities.Statements.WriteLine.TextWriter%2A> extension is directed to the host window.</span></span> <span data-ttu-id="a9a9a-106">Bir örnek boşta olduğunda, bu örnek için kullanılabilir yer işaretleri açılan kutuda görünür.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-106">When an instance is idle, the available bookmarks for that instance appear in a combo box.</span></span> <span data-ttu-id="a9a9a-107">Yer işareti seçerek, bazı metinleri giriş yapma ve sürdürme yer işareti düğmesine basarak iş akışının yürütülmesini devam eder.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-107">Selecting a bookmark, inputting some text, and pressing the resume bookmark button continue the execution of the workflow.</span></span> <span data-ttu-id="a9a9a-108">İptal etmek, iptal etmek veya seçili bir iş akışı sonlandırılmak.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-108">You can also cancel, abort, or terminate a selected workflow.</span></span> <span data-ttu-id="a9a9a-109">Kalıcılık varsayılan olarak açık – konak kapatın ve geri getirmek ve örnek listesi veritabanında depolanan örnekleri ile doldurulur.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-109">Persistence is on by default – you can shut down the host and bring it back, and the instance list is populated with the instances stored in the database.</span></span> <span data-ttu-id="a9a9a-110">İzleme kullanılır çıktıya <xref:System.Activities.WorkflowApplication>-düzeyinde etkinlik düzeyinde ayrıntılı izleme ekleme seçeneğine sahip bir konağa olayları.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-110">Tracking is used to output <xref:System.Activities.WorkflowApplication>-level events to the host with the option to add detailed tracking at the activity level.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="a9a9a-111">Örnek Ayrıntıları</span><span class="sxs-lookup"><span data-stu-id="a9a9a-111">Sample Details</span></span>  
 <span data-ttu-id="a9a9a-112">Bu konak iki katmanı vardır: Görünüm ve örnek Yöneticisi.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-112">There are two layers to this host: the view and the instance manager.</span></span> <span data-ttu-id="a9a9a-113">Görünüm oluşan `HostView` ve `WorkflowApplicationInfo` sınıfları.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-113">The view consists of the `HostView` and `WorkflowApplicationInfo` classes.</span></span> <span data-ttu-id="a9a9a-114">Bu konak için genel deseni içindir `HostView` kullanılabilir seçenekler kullanıcıya görüntülenecek sınıf temel alarak `WorkflowApplicationInfo` temsil ettikleri örnekleri ile eşitleme makul tutulan nesneleri.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-114">The general pattern for this host is for the `HostView` class to display available options to the user based on `WorkflowApplicationInfo` objects that are kept reasonably in synchronization with the instances they represent.</span></span> <span data-ttu-id="a9a9a-115">Örnek Yöneticisi katman oluşan `WorkflowApplicationManager` tüm konak iletişimler çekirdek olan sınıf ve `WorkflowDefinitionExtension` örneği ile başlatıldı program tanımı arasındaki ilişki devam ederse sınıfı ve diğer birkaç sınıfları.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-115">The instance manager layer consists of the `WorkflowApplicationManager` class, which is the core of all host communications, and the `WorkflowDefinitionExtension` class, which persists the relationship between an instance and the program definition it was started with and a few other classes.</span></span> <span data-ttu-id="a9a9a-116">`HostView` Çağrıları üzerinde işlemlerini kontrol `WorkflowApplicationManager`.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-116">The `HostView` calls control operations on the `WorkflowApplicationManager`.</span></span> <span data-ttu-id="a9a9a-117">Bu çağrı bir Esnek kullanıcı arabirimi korumak için genellikle uyumsuzdur.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-117">These calls are typically asynchronous to maintain a responsive user interface.</span></span> <span data-ttu-id="a9a9a-118">Zaman uyumsuz tam, çağırdığında `WorkflowApplicationManager` iyi tanımlanmış bir arabirimi aracılığıyla görünüm katmana geri çağrılar (`IHostView`).</span><span class="sxs-lookup"><span data-stu-id="a9a9a-118">When the asynchronous calls complete, the `WorkflowApplicationManager` makes calls back into the view layer through a well-defined interface (`IHostView`).</span></span> <span data-ttu-id="a9a9a-119">`HostView` Sınıfı çoğunlukla bu çağrılarından gönderir `WorkflowApplicationManager` kullanıcı arabirimi iş parçacığı sınıfı.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-119">The `HostView` class most often dispatches these calls from the `WorkflowApplicationManager` class to the user interface thread.</span></span> <span data-ttu-id="a9a9a-120">Metin yazma, iş parçacığı açısından güvenli yapılır <xref:System.Activities.Statements.WriteLine.TextWriter%2A> tarafından sağlanan nesnelerini `HostView` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-120">Text writing is done to thread-safe <xref:System.Activities.Statements.WriteLine.TextWriter%2A> objects provided by the `HostView` class.</span></span> <span data-ttu-id="a9a9a-121">Kullanıcı arabirimi olayları oluşturma tek şey değil.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-121">The user interface is not the only thing generating events.</span></span> <span data-ttu-id="a9a9a-122"><xref:System.Activities.WorkflowApplication> Nesneler de sinyal `WorkflowApplicationManager` zaman Git `Idle`, `Complete`, veya `Aborted`, örneğin.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-122">The <xref:System.Activities.WorkflowApplication> objects also signal the `WorkflowApplicationManager` when they go `Idle`, `Complete`, or are `Aborted`, for example.</span></span> <span data-ttu-id="a9a9a-123">`WorkflowApplicationManager` Sınıfı temizleme gönderme veya iş konağa güncelleştirme olay iş parçacığı alır.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-123">The `WorkflowApplicationManager` class gets off the event thread by dispatching clean up or updating work to the host.</span></span>  
  
 <span data-ttu-id="a9a9a-124">Kaydı başlatmak için kullanılan dosya, bir <xref:System.Activities.WorkflowApplication> da sayesinde kolaylaşır `WorkflowDefinitionExtension` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-124">The recording of the file used to launch a <xref:System.Activities.WorkflowApplication> is facilitated by the `WorkflowDefinitionExtension` class.</span></span> <span data-ttu-id="a9a9a-125">Bunu uygulayan <xref:System.Activities.Persistence.PersistenceIOParticipant> içinde Kalıcılık katılmak ve iş akışı tanımı yoluna kalıcı hale getirmek için arabirim.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-125">It implements the <xref:System.Activities.Persistence.PersistenceIOParticipant> interface to participate in persistence and persist the path to the workflow definition.</span></span>  
  
 <span data-ttu-id="a9a9a-126">`WorkflowApplicationManager.Load` Yöntemi yüklenmesi tamamlanmamış gerekli iş akışı programları örneği oluşturmak için depolanmış yolunu kullanır <xref:System.Activities.WorkflowApplication> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-126">The `WorkflowApplicationManager.Load` method uses the stored path to instantiate the workflow programs required for loading unfinished <xref:System.Activities.WorkflowApplication> objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a9a9a-127">Ayarlamak için derleme ve örnek çalıştırın</span><span class="sxs-lookup"><span data-stu-id="a9a9a-127">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a9a9a-128">Bu örnek, yüklenecek SQL Express gerektirir.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-128">This sample requires SQL Express to be installed.</span></span> <span data-ttu-id="a9a9a-129">SQL Express ile birlikte gelen [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9a9a-129">SQL Express comes with [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="a9a9a-130">Visual Studio 2010 Komut istemi açın.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-130">Open a Visual Studio 2010 command prompt.</span></span>  
  
3.  <span data-ttu-id="a9a9a-131">Örnek dizine (\WF\Basic\Execution\ControllingWorkflowApplications) gidin ve CreateInstanceStore.cmd çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-131">Navigate to the sample directory (\WF\Basic\Execution\ControllingWorkflowApplications) and run CreateInstanceStore.cmd.</span></span>  
  
4.  <span data-ttu-id="a9a9a-132">CreateInstanceStore.cmd komut dosyası, SQL Server 2008 Express varsayılan örneğinde veritabanı oluşturma dener.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-132">The CreateInstanceStore.cmd script attempts to create the database on the default instance of SQL Server 2008 Express.</span></span> <span data-ttu-id="a9a9a-133">Veritabanını farklı bir örneğinde yüklemek istiyorsanız, bunu yapmak için komut dosyasını değiştirin.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-133">If you want to install the database on a different instance, modify the script to do so.</span></span>  
  
5.  <span data-ttu-id="a9a9a-134">WorkflowApplicationReadLineHost projeyi derleyin ve komut satırından çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-134">Compile the WorkflowApplicationReadLineHost project and run it from the command line.</span></span>  
  
6.  <span data-ttu-id="a9a9a-135">Çalışan sonra kapatma veya isteğe bağlı olarak Kalıcılık kapatabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-135">Once running, you can optionally turn persistence off or on.</span></span> <span data-ttu-id="a9a9a-136">Ayrıca, isteğe bağlı olarak ayrıntılı etkinlik açmak veya kapatmak izlemeyi açabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-136">Further, you can optionally turn detailed activity tracking on or off.</span></span>  
  
7.  <span data-ttu-id="a9a9a-137">Yanındaki üç nokta düğmesine basın **çalıştırmak** XAML dosyasında tanımlanan iş akışı gözatmak için düğmeyi</span><span class="sxs-lookup"><span data-stu-id="a9a9a-137">Press the ellipsis button next to the **Run** button to browse for a workflow defined in a XAML file</span></span>  
  
     <span data-ttu-id="a9a9a-138">İki örnek SampleWorkflows klasörü altında bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-138">Two samples can be found under the SampleWorkflows folder.</span></span> <span data-ttu-id="a9a9a-139">Parallel1.xaml örnek boşta gider.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-139">The parallel1.xaml example goes idle.</span></span>  
  
8.  <span data-ttu-id="a9a9a-140">Bir örnek seçildikten sonra basın **çalıştırmak** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-140">Once an example is selected, press the **Run** button.</span></span>  
  
9. <span data-ttu-id="a9a9a-141">Varsa veya iş akışının boşta gittiğinde **yer işaretleri** birleşik giriş kutusu kullanılabilir yer işaretleri ile doldurulur.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-141">If or when the workflow goes idle, the **Bookmarks** combo box is populated with available bookmarks.</span></span>  
  
10. <span data-ttu-id="a9a9a-142">Bu noktada yer işareti sürdürmek, iptal, durdurmak veya iş akışının sonlandırmak için seçeneklerdir.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-142">The options at this point are to resume a bookmark, cancel, abort, or terminate the workflow.</span></span> <span data-ttu-id="a9a9a-143">Ana bilgisayar kapatın ve yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-143">You can also shut down the host and restart it.</span></span> <span data-ttu-id="a9a9a-144">Kalıcılık üzerinde bırakılırsa örnekleri kapanışında kaldırıldı ve yukarı başlangıç yeniden.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-144">If persistence is left on, the instances are unloaded on shutdown and reloaded on start up.</span></span>  
  
     <span data-ttu-id="a9a9a-145">Yer işareti sürdürmek için istenen yer işaretini seçin, birleşik giriş kutusu ve tuşuna yanındaki metin kutusuna bir değer yazın **sürdürme yer işareti**.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-145">To resume a bookmark, select the desired bookmark, type in a value in the text box next to the combo box and press **Resume Bookmark**.</span></span>  
  
#### <a name="to-remove-the-instance-store-database"></a><span data-ttu-id="a9a9a-146">Örnek deposu veritabanı kaldırmak için</span><span class="sxs-lookup"><span data-stu-id="a9a9a-146">To remove the instance store database</span></span>  
  
1.  <span data-ttu-id="a9a9a-147">Visual Studio 2010 Komut istemi açın.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-147">Open a Visual Studio 2010 command prompt.</span></span>  
  
2.  <span data-ttu-id="a9a9a-148">Örnek dizine (\WF\Basic\Execution\ControllingWorkflowApplications) gidin ve RemoveInstanceStore.cmd çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-148">Navigate to the sample directory (\WF\Basic\Execution\ControllingWorkflowApplications) and run RemoveInstanceStore.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a9a9a-149">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-149">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a9a9a-150">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-150">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a9a9a-151">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a9a9a-152">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-152">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ControllingWorkflowApplications`  
  
## <a name="see-also"></a><span data-ttu-id="a9a9a-153">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a9a9a-153">See Also</span></span>