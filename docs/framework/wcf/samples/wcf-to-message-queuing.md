---
title: "Windows Communication Foundation'dan İleti Kuyruğuna"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78d0d0c9-648e-4d4a-8f0a-14d9cafeead9
caps.latest.revision: "32"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6800db4e5f8dc1a0d571be3eed556503b907e16e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="windows-communication-foundation-to-message-queuing"></a><span data-ttu-id="f8592-102">Windows Communication Foundation'dan İleti Kuyruğuna</span><span class="sxs-lookup"><span data-stu-id="f8592-102">Windows Communication Foundation to Message Queuing</span></span>
<span data-ttu-id="f8592-103">Bu örnek gösterilmektedir nasıl bir [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uygulama bir Message Queuing (MSMQ) uygulamaya bir ileti gönderebilir.</span><span class="sxs-lookup"><span data-stu-id="f8592-103">This sample demonstrates how a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application can send a message to a Message Queuing (MSMQ) application.</span></span> <span data-ttu-id="f8592-104">Hizmeti, sıraya alınan iletileri alma hizmeti izlemek etkinleştirmek için bir kendi kendini barındıran konsol uygulamasıdır.</span><span class="sxs-lookup"><span data-stu-id="f8592-104">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span> <span data-ttu-id="f8592-105">Hizmet ve istemci aynı anda çalışıyor olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="f8592-105">The service and client do not have to be running at the same time.</span></span>  
  
 <span data-ttu-id="f8592-106">Hizmet kuyruktan iletileri alır ve siparişleri işler.</span><span class="sxs-lookup"><span data-stu-id="f8592-106">The service receives messages from the queue and processes orders.</span></span> <span data-ttu-id="f8592-107">Hizmet işlem bir sıra oluşturur ve bir ileti alındı ileti işleyicisini, aşağıdaki örnek kodda gösterildiği gibi ayarlar.</span><span class="sxs-lookup"><span data-stu-id="f8592-107">The service creates a transactional queue and sets up a message received message handler, as shown in the following sample code.</span></span>  
  
```  
static void Main(string[] args)  
{  
    if (!MessageQueue.Exists(  
              ConfigurationManager.AppSettings["queueName"]))  
       MessageQueue.Create(  
           ConfigurationManager.AppSettings["queueName"], true);  
        //Connect to the queue  
        MessageQueue Queue = new   
    MessageQueue(ConfigurationManager.AppSettings["queueName"]);  
    Queue.ReceiveCompleted +=   
                 new ReceiveCompletedEventHandler(ProcessOrder);  
    Queue.BeginReceive();  
    Console.WriteLine("Order Service is running");  
    Console.ReadLine();  
}  
```  
  
 <span data-ttu-id="f8592-108">Ne zaman bir ileti alındığında sırası, ileti işleyicisi `ProcessOrder` çağrılır.</span><span class="sxs-lookup"><span data-stu-id="f8592-108">When a message is received in the queue, the message handler `ProcessOrder` is invoked.</span></span>  
  
```  
public static void ProcessOrder(Object source,  
    ReceiveCompletedEventArgs asyncResult)  
{  
    try  
    {  
        // Connect to the queue.  
        MessageQueue Queue = (MessageQueue)source;  
        // End the asynchronous receive operation.  
        System.Messaging.Message msg =   
                     Queue.EndReceive(asyncResult.AsyncResult);  
        msg.Formatter = new System.Messaging.XmlMessageFormatter(  
                                new Type[] { typeof(PurchaseOrder) });  
        PurchaseOrder po = (PurchaseOrder) msg.Body;  
        Random statusIndexer = new Random();  
        po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];  
        Console.WriteLine("Processing {0} ", po);  
        Queue.BeginReceive();  
    }  
    catch (System.Exception ex)  
    {  
        Console.WriteLine(ex.Message);  
    }  
  
}  
```  
  
 <span data-ttu-id="f8592-109">Hizmet ayıklar `ProcessOrder` MSMQ İleti gövdesi ve sırasını işler.</span><span class="sxs-lookup"><span data-stu-id="f8592-109">The service extracts the `ProcessOrder` from the MSMQ message body, and processes the order.</span></span>  
  
 <span data-ttu-id="f8592-110">MSMQ kuyruk adı, aşağıdaki örnek yapılandırmada gösterildiği gibi bir yapılandırma dosyasının appSettings bölümünde belirtilir.</span><span class="sxs-lookup"><span data-stu-id="f8592-110">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>  
  
```xml  
<appSettings>  
    <add key="orderQueueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="f8592-111">Kuyruk adı, ters eğik çizgi ayırıcıları yolundaki ve yerel bilgisayar için bir nokta (.) kullanır.</span><span class="sxs-lookup"><span data-stu-id="f8592-111">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span>  
  
 <span data-ttu-id="f8592-112">İstemci bir satın alma siparişi oluşturur ve aşağıdaki örnek kodda gösterildiği gibi bir işlem kapsamı içinde satın alma siparişi gönderir.</span><span class="sxs-lookup"><span data-stu-id="f8592-112">The client creates a purchase order and submits the purchase order within the scope of a transaction, as shown in the following sample code.</span></span>  
  
```  
// Create the purchase order  
PurchaseOrder po = new PurchaseOrder();  
// Fill in the details  
...  
  
OrderProcessorClient client = new OrderProcessorClient("OrderResponseEndpoint");  
  
MsmqMessage<PurchaseOrder> ordermsg = new MsmqMessage<PurchaseOrder>(po);  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
    client.SubmitPurchaseOrder(ordermsg);  
    scope.Complete();  
}  
Console.WriteLine("Order has been submitted:{0}", po);  
  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
 <span data-ttu-id="f8592-113">İstemci bir özel istemci sıralı MSMQ ileti kuyruğuna göndermek için kullanır.</span><span class="sxs-lookup"><span data-stu-id="f8592-113">The client uses a custom client in-order to send the MSMQ message to the queue.</span></span> <span data-ttu-id="f8592-114">Alan ve iletiyi işleyen bir uygulama bir MSMQ uygulaması olduğundan ve bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uygulama, iki uygulama hiçbir örtük hizmet sözleşmesini yoktur.</span><span class="sxs-lookup"><span data-stu-id="f8592-114">Because the application that receives and processes the message is an MSMQ application and not a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, there is no implicit service contract between the two applications.</span></span> <span data-ttu-id="f8592-115">Bu nedenle, bu senaryoda Svcutil.exe aracını kullanarak bir proxy oluşturamıyoruz.</span><span class="sxs-lookup"><span data-stu-id="f8592-115">So, we cannot create a proxy using the Svcutil.exe tool in this scenario.</span></span>  
  
 <span data-ttu-id="f8592-116">Özel istemci temelde tüm aynıdır [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kullanan uygulamalar `MsmqIntegration` iletileri göndermek için bağlama.</span><span class="sxs-lookup"><span data-stu-id="f8592-116">The custom client is essentially the same for all [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications that use the `MsmqIntegration` binding to send messages.</span></span> <span data-ttu-id="f8592-117">Diğer istemcilerden farklı olarak, bir dizi hizmet işlemleri içermeyecek.</span><span class="sxs-lookup"><span data-stu-id="f8592-117">Unlike other clients, it does not include a range of service operations.</span></span> <span data-ttu-id="f8592-118">Bir Gönder ileti yalnızca işlemdir.</span><span class="sxs-lookup"><span data-stu-id="f8592-118">It is a submit message operation only.</span></span>  
  
```  
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Action = "*")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
}  
  
public partial class OrderProcessorClient : System.ServiceModel.ClientBase<IOrderProcessor>, IOrderProcessor  
{  
    public OrderProcessorClient(){}  
  
    public OrderProcessorClient(string configurationName)  
        : base(configurationName)  
    { }  
  
    public OrderProcessorClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)  
        : base(binding, address)  
    { }  
  
    public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
    {  
        base.Channel.SubmitPurchaseOrder(msg);  
    }  
}  
```  
  
 <span data-ttu-id="f8592-119">Örneği çalıştırdığınızda, istemci ve hizmet etkinlikleri hem hizmet hem de istemci konsol pencerelerinde görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="f8592-119">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="f8592-120">İstemci hizmeti alma iletileri görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f8592-120">You can see the service receive messages from the client.</span></span> <span data-ttu-id="f8592-121">Her konsol penceresinde hizmet ve istemci kapatmak için ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="f8592-121">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="f8592-122">Queuing kullanımda olduğundan, istemci ve hizmet aynı anda açık ve çalışıyor olması sahip olmadığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="f8592-122">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="f8592-123">Örneğin, istemcisini çalıştıran, kapatmak ve hizmeti başlatın ve hala kendi ileti alacaksınız.</span><span class="sxs-lookup"><span data-stu-id="f8592-123">For example, you could run the client, shut it down, and then start up the service and it would still receive its messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8592-124">Bu örnek, Message Queuing yüklemesini gerektirir.</span><span class="sxs-lookup"><span data-stu-id="f8592-124">This sample requires the installation of Message Queuing.</span></span> <span data-ttu-id="f8592-125">' Ndaki yükleme yönergelerine bakın [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=94968).</span><span class="sxs-lookup"><span data-stu-id="f8592-125">See the installation instructions in [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=94968).</span></span>  
  
### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="f8592-126">Kurulum, yapı ve örneği çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="f8592-126">To setup, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f8592-127">Gerçekleştirmiş emin olun [kerelik Kurulum prosedürü Windows Communication Foundation örnekleri için](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f8592-127">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="f8592-128">Hizmetin ilk olarak çalışıyorsa, sıranın var olduğundan emin olmak için kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="f8592-128">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="f8592-129">Hizmet sırası mevcut değilse oluşturur.</span><span class="sxs-lookup"><span data-stu-id="f8592-129">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="f8592-130">İlk sırayı oluşturmak için hizmet çalıştırabilirsiniz veya bir MSMQ sıra Yöneticisi aracılığıyla oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f8592-130">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="f8592-131">Windows 2008'de bir kuyruk oluşturmak için aşağıdaki adımları izleyin.</span><span class="sxs-lookup"><span data-stu-id="f8592-131">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="f8592-132">Sunucu Yöneticisi'nde açın [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8592-132">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="f8592-133">Genişletme **özellikleri** sekmesi.</span><span class="sxs-lookup"><span data-stu-id="f8592-133">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="f8592-134">Sağ **özel ileti kuyrukları**seçip **yeni**, **özel sıra**.</span><span class="sxs-lookup"><span data-stu-id="f8592-134">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="f8592-135">Denetleme **işlem** kutusu.</span><span class="sxs-lookup"><span data-stu-id="f8592-135">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="f8592-136">Girin `ServiceModelSamplesTransacted` yeni kuyruk adından farklı.</span><span class="sxs-lookup"><span data-stu-id="f8592-136">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="f8592-137">Çözüm C# veya Visual Basic .NET sürümünü oluşturmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örnekleri derleme](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f8592-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="f8592-138">Tek bilgisayarlı yapılandırmada örneği çalıştırmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örneklerini çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f8592-138">To run the sample in a single-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="f8592-139">Bilgisayarlar arasında örneği çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="f8592-139">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="f8592-140">Hizmet program dosyalarını dile özgü klasörü altındaki \service\bin\ klasöründen hizmet bilgisayara kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="f8592-140">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2.  <span data-ttu-id="f8592-141">İstemci program dosyaları \client\bin\ klasöründen dile özgü klasörü altında istemci bilgisayara kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="f8592-141">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3.  <span data-ttu-id="f8592-142">Hizmet bilgisayar adı yerine belirtmek için istemci uç noktası adresi Client.exe.config dosyasında değiştirmek ".".</span><span class="sxs-lookup"><span data-stu-id="f8592-142">In the Client.exe.config file, change the client endpoint address to specify the service computer name instead of ".".</span></span>  
  
4.  <span data-ttu-id="f8592-143">Hizmet bilgisayarda bir komut isteminden Service.exe başlatın.</span><span class="sxs-lookup"><span data-stu-id="f8592-143">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
5.  <span data-ttu-id="f8592-144">İstemci bilgisayarda bir komut isteminden Client.exe başlatın.</span><span class="sxs-lookup"><span data-stu-id="f8592-144">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f8592-145">Örnekler, bilgisayarınızda yüklü.</span><span class="sxs-lookup"><span data-stu-id="f8592-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f8592-146">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="f8592-146">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f8592-147">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="f8592-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f8592-148">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="f8592-148">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\WcfToMsmq`  
  
## <a name="see-also"></a><span data-ttu-id="f8592-149">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f8592-149">See Also</span></span>  
 [<span data-ttu-id="f8592-150">Nasıl yapılır: WCF uç noktaları iletileri Exchange ve Message Queuing uygulamaları</span><span class="sxs-lookup"><span data-stu-id="f8592-150">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [<span data-ttu-id="f8592-151">Message Queuing</span><span class="sxs-lookup"><span data-stu-id="f8592-151">Message Queuing</span></span>](http://go.microsoft.com/fwlink/?LinkId=94968)