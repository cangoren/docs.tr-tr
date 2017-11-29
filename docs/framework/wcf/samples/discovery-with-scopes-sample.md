---
title: "Kapsam ile Keşif Örneği"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a37a754-6b8c-4ebe-bdf2-d4f0520271d5
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 97bf047f26b95cdd4ac4a40e6b2284ec170442bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="discovery-with-scopes-sample"></a><span data-ttu-id="00ae7-102">Kapsam ile Keşif Örneği</span><span class="sxs-lookup"><span data-stu-id="00ae7-102">Discovery with Scopes Sample</span></span>
<span data-ttu-id="00ae7-103">Bu örnek kapsamları bulunabilirlik uç noktaları iyi nasıl kullanılacağını olarak kategorilere ayırmak için nasıl kullanılacağını göstermektedir <xref:System.ServiceModel.Discovery.DiscoveryClient> uç noktalar için zaman uyumsuz bir arama yapmak üzere.</span><span class="sxs-lookup"><span data-stu-id="00ae7-103">This sample shows how to use scopes to categorize discoverable endpoints as well how to use <xref:System.ServiceModel.Discovery.DiscoveryClient> to perform an asynchronous search for endpoints.</span></span> <span data-ttu-id="00ae7-104">Hizmette Bu örnek bulma her uç nokta için bir uç nokta bulma davranışını ekleme ve uç nokta için bir kapsam eklemek için kullanarak yanı sıra uç noktanın bulunabilirliği denetleme özelleştirme gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="00ae7-104">On the service, this sample shows how to customize discovery for each endpoint by adding an endpoint discovery behavior and using it to add a scope to the endpoint as well as controlling the endpoint’s discoverability.</span></span> <span data-ttu-id="00ae7-105">İstemcilerin nasıl oluşturabileceğinizi üzerinden örnek istemcide, giden bir <xref:System.ServiceModel.Discovery.DiscoveryClient> ve kapsamları ekleyerek kapsamları eklenecek parametreleri arama ince ayar <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="00ae7-105">On the client, the sample goes over how clients can create a <xref:System.ServiceModel.Discovery.DiscoveryClient> and fine tune search parameters to include scopes by adding scopes to the <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span> <span data-ttu-id="00ae7-106">Bu örnek ayrıca bir sonlandırma ölçüt ekleyerek istemcileri yanıtları nasıl kısıtlayabilirsiniz gösterir.</span><span class="sxs-lookup"><span data-stu-id="00ae7-106">This sample also shows how clients can restrict responses by adding a termination criterion.</span></span>  
  
## <a name="service-features"></a><span data-ttu-id="00ae7-107">Hizmet Özellikleri</span><span class="sxs-lookup"><span data-stu-id="00ae7-107">Service Features</span></span>  
 <span data-ttu-id="00ae7-108">Bu proje için eklenmekte olan iki hizmet uç noktaları gösterir bir <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="00ae7-108">This project shows two service endpoints being added to a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="00ae7-109">Her bitiş noktasının bir <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> kendisiyle ilişkilendirilmiş.</span><span class="sxs-lookup"><span data-stu-id="00ae7-109">Each endpoint has a <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> associated with it.</span></span> <span data-ttu-id="00ae7-110">Bu davranış, her iki uç noktaları için URI kapsamı eklemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="00ae7-110">This behavior is used to add URI scopes for both endpoints.</span></span> <span data-ttu-id="00ae7-111">Kapsamları, böylece istemciler arama yapılandırarak ince ayar her Bu uç noktalar ayırt etmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="00ae7-111">Scopes are used to distinguish each of these endpoints so that the clients can fine tune the search.</span></span> <span data-ttu-id="00ae7-112">İkinci uç nokta için bulunabilirliği ayarlayarak devre dışı bırakılabilir <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A> özelliğine `false`.</span><span class="sxs-lookup"><span data-stu-id="00ae7-112">For the second endpoint, the discoverability can be disabled by setting the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A> property to `false`.</span></span> <span data-ttu-id="00ae7-113">Bu, herhangi bir bulma iletisinin bir parçası olarak bu uç noktasıyla ilişkili bulma meta veri gönderilmez sağlar.</span><span class="sxs-lookup"><span data-stu-id="00ae7-113">This ensures that the discovery metadata associated with this endpoint is not sent as part of any discovery messages.</span></span>  
  
## <a name="client-features"></a><span data-ttu-id="00ae7-114">İstemci özellikleri</span><span class="sxs-lookup"><span data-stu-id="00ae7-114">Client Features</span></span>  
 <span data-ttu-id="00ae7-115">`FindCalculatorServiceAddress()` Yönteminin nasıl kullanılacağını gösterir bir <xref:System.ServiceModel.Discovery.DiscoveryClient> ve geçirin bir <xref:System.ServiceModel.Discovery.FindCriteria> iki kısıtlamalarla.</span><span class="sxs-lookup"><span data-stu-id="00ae7-115">The `FindCalculatorServiceAddress()` method shows how to use a <xref:System.ServiceModel.Discovery.DiscoveryClient> and pass in a <xref:System.ServiceModel.Discovery.FindCriteria> with two restrictions.</span></span> <span data-ttu-id="00ae7-116">Bir kapsam ölçüte eklenir ve <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> özelliğini 1 olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="00ae7-116">A scope is added to the criteria and the <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> property is set to 1.</span></span> <span data-ttu-id="00ae7-117">Kapsam yalnızca aynı kapsamı yayımlama hizmetlerine sonuçlarını sınırlandırır.</span><span class="sxs-lookup"><span data-stu-id="00ae7-117">The scope limits the results to only the services that publish the same scope.</span></span> <span data-ttu-id="00ae7-118">Ayarı <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> 1 yanıtları sınırlar <xref:System.ServiceModel.Discovery.DiscoveryClient> için en fazla 1 uç nokta bekler.</span><span class="sxs-lookup"><span data-stu-id="00ae7-118">Setting <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> to 1 limits the responses the <xref:System.ServiceModel.Discovery.DiscoveryClient> waits for to, at most, 1 endpoint.</span></span> <span data-ttu-id="00ae7-119"><xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> Çağrıdır zaman aşımı sınıra veya bir uç nokta bulundu kadar iş parçacığı engellenir eşzamanlı bir işlem.</span><span class="sxs-lookup"><span data-stu-id="00ae7-119">The <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> call is a synchronous operation that blocks the thread until a timeout is reached or one endpoint is found.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="00ae7-120">Bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="00ae7-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="00ae7-121">Bu örnek HTTP uç noktaları kullanır ve bu örneği çalıştırmak için doğru URL ACL eklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="00ae7-121">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="00ae7-122">Bkz: [yapılandırma HTTP ve HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) Ayrıntılar için.</span><span class="sxs-lookup"><span data-stu-id="00ae7-122">See [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details.</span></span> <span data-ttu-id="00ae7-123">Aşağıdaki komutu yükseltilmiş ayrıcalık yürütme uygun ACL'ler eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="00ae7-123">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="00ae7-124">Komut olduğu gibi çalışmazsa, etki alanı ve kullanıcı adı şu bağımsız değişkenleri yerine isteyebilirsiniz:`netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`</span><span class="sxs-lookup"><span data-stu-id="00ae7-124">You may want to substitute your Domain and Username for the following arguments if the command does not work as is: `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`</span></span>  
  
2.  <span data-ttu-id="00ae7-125">Çözümü oluşturun.</span><span class="sxs-lookup"><span data-stu-id="00ae7-125">Build the solution.</span></span>  
  
3.  <span data-ttu-id="00ae7-126">Hizmeti yürütülebilir dosyası derleme dizininden çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="00ae7-126">Run the service executable from the build directory.</span></span>  
  
4.  <span data-ttu-id="00ae7-127">İstemci yürütülebilir çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="00ae7-127">Run the client executable.</span></span> <span data-ttu-id="00ae7-128">İstemci hizmetini bulun mümkün olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="00ae7-128">Note that the client is able to locate the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="00ae7-129">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="00ae7-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="00ae7-130">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="00ae7-130">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="00ae7-131">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="00ae7-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="00ae7-132">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="00ae7-132">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryWithScopes`  
  
## <a name="see-also"></a><span data-ttu-id="00ae7-133">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="00ae7-133">See Also</span></span>