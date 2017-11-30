---
title: "Service Fabric Windows kapsayıcıları dağıtma zamanı"
description: "Kapsayıcılı .NET uygulamaları için .NET mikro mimarisi | Service Fabric Windows kapsayıcıları dağıtma zamanı"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 21b6c348991e07dac7dbc9d327b63fa88a588ba4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-deploy-windows-containers-to-service-fabric"></a><span data-ttu-id="28c09-103">Service Fabric Windows kapsayıcıları dağıtma zamanı</span><span class="sxs-lookup"><span data-stu-id="28c09-103">When to deploy Windows Containers to Service Fabric</span></span>

<span data-ttu-id="28c09-104">Windows kapsayıcılarında tabanlı uygulamaları hızlı bir şekilde daha uzakta Iaas Vm'lerden taşıma platformları kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="28c09-104">Applications that are based on Windows Containers will quickly need to use platforms that move even further away from IaaS VMs.</span></span> <span data-ttu-id="28c09-105">Bu geliştirilmiş otomatik ölçeklenebilirlik ve yüksek ölçeklenebilirlik içindir ve tam yönetim deneyiminde dağıtımlar için önemli geliştirmeler kazanmak için yükseltir, sürüm oluşturma, alma ve sistem durumu izleme.</span><span class="sxs-lookup"><span data-stu-id="28c09-105">This is for improved automated scalability and high scalability, and to gain significant improvements in a complete management experience for deployments, upgrades, versioning, rollbacks, and health monitoring.</span></span> <span data-ttu-id="28c09-106">Azure Service Fabric, Microsoft Azure bulut, aynı zamanda şirket içi veya başka bir bulutta bile kullanılabilir orchestrator ile bu hedefleri elde edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="28c09-106">You can achieve these goals with the orchestrator Azure Service Fabric, available in the Microsoft Azure cloud, but also on-premises, or even in another cloud.</span></span>

<span data-ttu-id="28c09-107">Birçok kuruluş kaldırma ve iki nedenden dolayı kapsayıcılara tek yapılı uygulamalarınız kaydırma:</span><span class="sxs-lookup"><span data-stu-id="28c09-107">Many organizations are lifting and shifting existing monolithic applications to containers for two reasons:</span></span>

-   <span data-ttu-id="28c09-108">Maliyet düşürülmesi, ya da birleştirme ve temizleme mevcut donanım veya yüksek yoğunluk çalışan uygulamalar nedeniyle.</span><span class="sxs-lookup"><span data-stu-id="28c09-108">Cost reductions, either due to consolidation and removal of existing hardware, or from running applications at a higher density.</span></span>

-   <span data-ttu-id="28c09-109">Geliştirme ve işlemler arasında tutarlı bir dağıtım sözleşme.</span><span class="sxs-lookup"><span data-stu-id="28c09-109">A consistent deployment contract between development and operations.</span></span>

<span data-ttu-id="28c09-110">Maliyet azaltması sürdürdüğünü anlaşılabilir ve tüm organizasyonlar bu hedefe birleştirme olasıdır.</span><span class="sxs-lookup"><span data-stu-id="28c09-110">Pursuing cost reductions is understandable, and it's likely that all organizations are chasing that goal.</span></span> <span data-ttu-id="28c09-111">Tutarlı bir dağıtım, değerlendirilecek daha zor, ancak aynı derecede önemli olarak gelir.</span><span class="sxs-lookup"><span data-stu-id="28c09-111">Consistent deployment is harder to evaluate, but it's equally as important.</span></span> <span data-ttu-id="28c09-112">Tutarlı bir dağıtım sözleşme geliştiriciler bunları uygun teknolojiyi kullanmak üzere seçmek ücretsiz ve işlemler ekibinin uygulamaları dağıtmak ve yönetmek için tek bir yolu alır söyler.</span><span class="sxs-lookup"><span data-stu-id="28c09-112">A consistent deployment contract says that developers are free to choose to use the technology that suits them, and the operations team gets a single way to deploy and manage applications.</span></span> <span data-ttu-id="28c09-113">Bu anlaşma birçok farklı teknolojiler karmaşıklık ile ilgili işlemleri olması ya da yalnızca belirli teknolojileri ile geliştiricilerin zorlama sorunları azaltır.</span><span class="sxs-lookup"><span data-stu-id="28c09-113">This agreement alleviates the pain of having operations deal with the complexity of many different technologies, or forcing developers to work only with certain technologies.</span></span> <span data-ttu-id="28c09-114">Esas olarak, her uygulamanın kendi içinde bulunan yansıması kapsayıcılı.</span><span class="sxs-lookup"><span data-stu-id="28c09-114">Essentially, each application is containerized in a self-contained deployment image.</span></span>

<span data-ttu-id="28c09-115">Bazı kuruluşlar, mikro (bulut optimize ve bulut-yerel uygulamalar) ekleyerek modernizing devam eder.</span><span class="sxs-lookup"><span data-stu-id="28c09-115">Some organizations will continue modernizing by adding microservices (Cloud-Optimized and cloud-native applications).</span></span> <span data-ttu-id="28c09-116">Birçok kuruluş, burada (bulut DevOps hazır) durdurur.</span><span class="sxs-lookup"><span data-stu-id="28c09-116">Many organizations will stop here (Cloud DevOps-Ready).</span></span> <span data-ttu-id="28c09-117">İçin gerekmeyebilir çünkü Şekil 4-8'de gösterildiği gibi bu kuruluşların mikro mimarileri taşınmaz.</span><span class="sxs-lookup"><span data-stu-id="28c09-117">As shown in Figure 4-8, these organizations won't move to microservices architectures because they might not need to.</span></span> <span data-ttu-id="28c09-118">Herhangi bir durumda, bunlar zaten kapsayıcıları artı Service Fabric kullanarak, dağıtım, içeren sağlayan bir tam yönetim deneyimi yükseltmeleri avantajları, sürüm oluşturma, alma ve sistem durumu izleme alın.</span><span class="sxs-lookup"><span data-stu-id="28c09-118">In any case, they already get the benefits that using containers plus Service Fabric provides-a complete management experience that includes deployment, upgrades, versioning, rollbacks, and health monitoring.</span></span>

> ![Kaldırın ve Service Fabric uygulama kaydırma](./media/image8.png)
>
> <span data-ttu-id="28c09-120">**Şekil 4-8.**</span><span class="sxs-lookup"><span data-stu-id="28c09-120">**Figure 4-8.**</span></span> <span data-ttu-id="28c09-121">Kaldırın ve Service Fabric uygulama kaydırma</span><span class="sxs-lookup"><span data-stu-id="28c09-121">Lift and shift an application to Service Fabric</span></span>

<span data-ttu-id="28c09-122">Bir anahtar Service Fabric için var olan kodu yeniden kullanma ve yalnızca kaldırın ve shift yaklaşımdır.</span><span class="sxs-lookup"><span data-stu-id="28c09-122">A key approach to Service Fabric is to reuse existing code and simply lift and shift.</span></span> <span data-ttu-id="28c09-123">Bu nedenle, geçerli .NET Framework uygulamalarınızın Windows kapsayıcıları kullanarak geçirmek ve bunları Service Fabric dağıtabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="28c09-123">Therefore, you can migrate your current .NET Framework applications, by using Windows Containers, and deploy them to Service Fabric.</span></span> <span data-ttu-id="28c09-124">Bu, sonuç olarak, yeni mikro ekleyerek modernizing giderek tutmak daha kolay olacaktır.</span><span class="sxs-lookup"><span data-stu-id="28c09-124">It will be easier to keep going modernizing, eventually, by adding new microservices.</span></span>

<span data-ttu-id="28c09-125">Service Fabric diğer orchestrators karşılaştırıldığında, Service Fabric Windows tabanlı uygulamalar ve hizmetler çalıştıran en çok olgun vurgulamak önemlidir.</span><span class="sxs-lookup"><span data-stu-id="28c09-125">When comparing Service Fabric to other orchestrators, it's important to highlight that Service Fabric is very mature at running Windows-based applications and services.</span></span> <span data-ttu-id="28c09-126">Service Fabric, Windows tabanlı hizmetler ve uygulamalar, Microsoft, Katman 1, kritik ürünlerinden yıldır dahil olmak üzere çalıştığı.</span><span class="sxs-lookup"><span data-stu-id="28c09-126">Service Fabric has been running Windows-based services and applications, including Tier-1, mission-critical products from Microsoft, for years.</span></span> <span data-ttu-id="28c09-127">Windows kapsayıcıları (Mayıs 2017) için genel kullanılabilirlik sağlamak için ilk orchestrator oluştu.</span><span class="sxs-lookup"><span data-stu-id="28c09-127">It was the first orchestrator to have general availability for Windows Containers (May 2017).</span></span> <span data-ttu-id="28c09-128">Diğer, Kubernetes, DC/OS ve Docker Swarm, gibi Linux içinde daha da olgun için Service Fabric Windows tabanlı uygulamalar ve Windows kapsayıcıları daha az olgun ancak kapsayıcılardır.</span><span class="sxs-lookup"><span data-stu-id="28c09-128">Other containers, like Kubernetes, DC/OS, and Docker Swarm, are more mature in Linux, but less mature than Service Fabric for Windows-based applications and Windows Containers.</span></span>

<span data-ttu-id="28c09-129">Service Fabric nihai amacı bir mikro yaklaşım kullanarak uygulamaları oluşturma karmaşıklıkları azaltmaktır.</span><span class="sxs-lookup"><span data-stu-id="28c09-129">The ultimate goal of Service Fabric is to reduce the complexities of building applications by using a microservices approach.</span></span> <span data-ttu-id="28c09-130">Sonunda maliyetli redesigns önlemek için uygulama türlerini belirli olmasını istediğiniz budur.</span><span class="sxs-lookup"><span data-stu-id="28c09-130">This is where you eventually want to be for certain types of applications, to avoid costly redesigns.</span></span> <span data-ttu-id="28c09-131">Küçük başlayın, gerektiğinde ölçeklendirme, hizmetleri Kaldır, yeni hizmet ekleme ve müşteri ile uygulamanızı geliştirin.</span><span class="sxs-lookup"><span data-stu-id="28c09-131">You can start small, scale when needed, deprecate services, add new services, and evolve your application with customer use.</span></span> <span data-ttu-id="28c09-132">Mikro çoğu geliştiriciler için daha erişilebilir yapma çözülecek henüz olan diğer birçok sorunlar olduğunu biliyoruz.</span><span class="sxs-lookup"><span data-stu-id="28c09-132">We know that there are many other problems that are yet to be solved to make microservices more approachable for most developers.</span></span> <span data-ttu-id="28c09-133">Şu anda yalnızca kaldırma ve çalıştığınız uygulamanın Windows kapsayıcılarla kaydırma, ancak gelecekte kapsayıcılarında tabanlı mikro ekleme hakkında düşünüyorum, Service Fabric Lezzetli nokta olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="28c09-133">If you currently are just lifting and shifting an application with Windows Containers, but you are thinking about adding microservices based on containers in the future, that is the Service Fabric sweet spot.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="28c09-134">[Önceki](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[sonraki](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="28c09-134">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span></span>