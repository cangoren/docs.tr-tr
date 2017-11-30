---
title: "Windows Communication Foundation Bağlamaları Genel Bakış"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bindings [WCF], overview
ms.assetid: cfb5842f-e0f9-4c56-a015-f2b33f258232
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a131574e0e3de8507a91807d5de2899238c14628
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="windows-communication-foundation-bindings-overview"></a><span data-ttu-id="35755-102">Windows Communication Foundation Bağlamaları Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="35755-102">Windows Communication Foundation Bindings Overview</span></span>
<span data-ttu-id="35755-103">Bağlamaları değil uç noktasına bağlanmak için gereken iletişim ayrıntılarını belirtmek için kullanılan nesneleri bir [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] hizmet.</span><span class="sxs-lookup"><span data-stu-id="35755-103">Bindings are objects that are used to specify the communication details that are required to connect to the endpoint of a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service.</span></span> <span data-ttu-id="35755-104">İçindeki her bir uç nokta bir [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hizmet bağlama iyi belirtilen olmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="35755-104">Each endpoint in a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service requires a binding to be well-specified.</span></span> <span data-ttu-id="35755-105">Bu konu bağlamaları tanımlamak, iletişim ayrıntılarını hangi bağlamaları içinde yer alan bir bağlama öğelerini türlerini özetler [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], ve bir bağlama için bir uç nokta nasıl belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="35755-105">This topic outlines the types of communication details that the bindings define, the elements of a binding, what bindings are included in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], and how a binding can be specified for an endpoint.</span></span>  
  
## <a name="what-a-binding-defines"></a><span data-ttu-id="35755-106">Hangi bağlama tanımlar</span><span class="sxs-lookup"><span data-stu-id="35755-106">What a Binding Defines</span></span>  
 <span data-ttu-id="35755-107">Bağlama bilgileri çok basit ya da çok karmaşık olabilir.</span><span class="sxs-lookup"><span data-stu-id="35755-107">The information in a binding can be very basic, or very complex.</span></span> <span data-ttu-id="35755-108">En temel bağlama bitiş noktasına bağlanmak için kullanılması gereken Aktarım Protokolü (HTTP gibi) belirtir.</span><span class="sxs-lookup"><span data-stu-id="35755-108">The most basic binding specifies only the transport protocol (such as HTTP) that must be used to connect to the endpoint.</span></span> <span data-ttu-id="35755-109">Daha fazla genel olarak, bir bağlama içeren bir uç noktasını bağlamak hakkında bilgi aşağıdaki kategoriden döner.</span><span class="sxs-lookup"><span data-stu-id="35755-109">More generally, the information a binding contains about how to connect to an endpoint falls into one of the following categories.</span></span>  
  
 <span data-ttu-id="35755-110">protokolleri</span><span class="sxs-lookup"><span data-stu-id="35755-110">Protocols</span></span>  
 <span data-ttu-id="35755-111">Kullanılan güvenlik mekanizması belirler: güvenilir Mesajlaşma özellik veya işlem bağlamı akış ayarları.</span><span class="sxs-lookup"><span data-stu-id="35755-111">Determines the security mechanism being used: either reliable messaging capability or transaction context flow settings.</span></span>  
  
 <span data-ttu-id="35755-112">Kodlama</span><span class="sxs-lookup"><span data-stu-id="35755-112">Encoding</span></span>  
 <span data-ttu-id="35755-113">İleti (örneğin, metin veya ikili) kodlamasını belirler.</span><span class="sxs-lookup"><span data-stu-id="35755-113">Determines the message encoding (for example, text or binary).</span></span>  
  
 <span data-ttu-id="35755-114">Taşıma</span><span class="sxs-lookup"><span data-stu-id="35755-114">Transport</span></span>  
 <span data-ttu-id="35755-115">(Örneğin, TCP veya HTTP) kullanmak için temel Aktarım Protokolü belirler.</span><span class="sxs-lookup"><span data-stu-id="35755-115">Determines the underlying transport protocol to use (for example, TCP or HTTP).</span></span>  
  
## <a name="the-elements-of-a-binding"></a><span data-ttu-id="35755-116">Bağlama öğeleri</span><span class="sxs-lookup"><span data-stu-id="35755-116">The Elements of a Binding</span></span>  
 <span data-ttu-id="35755-117">Bir bağlama neredeyse her biri bir hizmet uç noktasına bağlanmak için gereken iletişim bilgilerini parçası belirtir bağlama öğelerinin, bir sıralı yığın oluşur.</span><span class="sxs-lookup"><span data-stu-id="35755-117">A binding basically consists of an ordered stack of binding elements, each of which specifies part of the communication information required to connect to a service endpoint.</span></span> <span data-ttu-id="35755-118">Her ikisi de yığınında iki en düşük katman olan gerekli.</span><span class="sxs-lookup"><span data-stu-id="35755-118">The two lowest layers in the stack are both required.</span></span> <span data-ttu-id="35755-119">Yığın tabanına aktarım bağlama öğe ve yalnızca bu belirtimleri kodlama iletisini içeren bir öğedir.</span><span class="sxs-lookup"><span data-stu-id="35755-119">At the base of the stack is the transport binding element and just above this is the element that contains the message encoding specifications.</span></span> <span data-ttu-id="35755-120">Bir iletişim protokolü belirtmek isteğe bağlı bağlama öğeleri bu iki gerekli öğeler üzerinde katmanlanmış.</span><span class="sxs-lookup"><span data-stu-id="35755-120">The optional binding elements that specify the other communication protocols are layered above these two required elements.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="35755-121">Bu bağlama öğeleri ve bunların doğru sipariş, bkz: [özel bağlamaları](../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="35755-121"> these binding elements and their correct ordering, see [Custom Bindings](../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="system-provided-bindings"></a><span data-ttu-id="35755-122">Sistem Tarafından Sağlanan Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="35755-122">System-Provided Bindings</span></span>  
 <span data-ttu-id="35755-123">Bağlama bilgileri karmaşık olabilir ve bazı ayarları başkalarıyla uyumlu olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="35755-123">The information in a binding can be complex, and some settings may not be compatible with others.</span></span> <span data-ttu-id="35755-124">Bu nedenle, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sistem tarafından sağlanan bağlamalar kümesi içerir.</span><span class="sxs-lookup"><span data-stu-id="35755-124">For this reason, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] includes a set of system-provided bindings.</span></span> <span data-ttu-id="35755-125">Bu bağlamaların çoğu uygulama gereksinimlerini karşılamak üzere tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="35755-125">These bindings are designed to cover most application requirements.</span></span> <span data-ttu-id="35755-126">Aşağıdaki sınıflar sistem tarafından sağlanan bağlamalar bazı örnekleri temsil eder:</span><span class="sxs-lookup"><span data-stu-id="35755-126">The following classes represent some examples of system-provided bindings:</span></span>  
  
-   <span data-ttu-id="35755-127"><xref:System.ServiceModel.BasicHttpBinding>: WS uyumlu Web hizmetlerine bağlanmak için uygun bağlama bir HTTP protokolü-ı temel profil belirtimi (örneğin, ASP.NET Web Hizmetleri tabanlı hizmetler).</span><span class="sxs-lookup"><span data-stu-id="35755-127"><xref:System.ServiceModel.BasicHttpBinding>: An HTTP protocol binding suitable for connecting to Web services that conforms to the WS-I Basic Profile specification (for example, ASP.NET Web services-based services).</span></span>  
  
-   <span data-ttu-id="35755-128"><xref:System.ServiceModel.WSHttpBinding>: WS - için uygun Uç noktalara bağlanmak için uygun birlikte çalışabilir bir bağlama * protokoller.</span><span class="sxs-lookup"><span data-stu-id="35755-128"><xref:System.ServiceModel.WSHttpBinding>: An interoperable binding suitable for connecting to endpoints that conform to the WS-* protocols.</span></span>  
  
-   <span data-ttu-id="35755-129"><xref:System.ServiceModel.NetNamedPipeBinding>: Kullanır [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] diğer bağlanmak için [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bitiş noktaları aynı makine üzerindeki.</span><span class="sxs-lookup"><span data-stu-id="35755-129"><xref:System.ServiceModel.NetNamedPipeBinding>: Uses the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] to connect to other [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] endpoints on the same machine.</span></span>  
  
-   <span data-ttu-id="35755-130"><xref:System.ServiceModel.NetMsmqBinding>: Kullanır [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] diğer sıraya alınan ileti bağlantıları oluşturmak için [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] uç noktaları.</span><span class="sxs-lookup"><span data-stu-id="35755-130"><xref:System.ServiceModel.NetMsmqBinding>: Uses the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] to create queued message connections with other [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] endpoints.</span></span>  
  
 <span data-ttu-id="35755-131">Tüm açıklamalarını tam bir listesi için [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-bağlamaları, bkz: sağlanan [System-Provided bağlamaları](../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="35755-131">For a complete list, with descriptions, of all the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-provided bindings, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
## <a name="using-your-own-bindings"></a><span data-ttu-id="35755-132">Kendi bağlamaları kullanma</span><span class="sxs-lookup"><span data-stu-id="35755-132">Using Your Own Bindings</span></span>  
 <span data-ttu-id="35755-133">Dahil edilen sistem tarafından sağlanan bağlamalar hiçbiri bir hizmet uygulaması gerektiren özellikleri doğru bileşimini varsa, kendi bağlama oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35755-133">If none of the system-provided bindings included has the right combination of features that a service application requires, you can create your own binding.</span></span> <span data-ttu-id="35755-134">Bunu yapmanın iki yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="35755-134">There are two ways to do this.</span></span> <span data-ttu-id="35755-135">Oluşturabilir ya da yeni bir bağlama kullanarak bağlama öğeleri önceden varolan bir <xref:System.ServiceModel.Channels.CustomBinding> nesne veya oluşturabilir tamamen kullanıcı tanımlı bir bağlama türetme tarafından <xref:System.ServiceModel.Channels.Binding> bağlama.</span><span class="sxs-lookup"><span data-stu-id="35755-135">You can either create a new binding from pre-existing binding elements using a <xref:System.ServiceModel.Channels.CustomBinding> object or you can create a completely user-defined binding by deriving from the <xref:System.ServiceModel.Channels.Binding> binding.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="35755-136">Bu iki yaklaşım kullanarak bağlama bkz kendi oluşturma [özel bağlamaları](../../../docs/framework/wcf/extending/custom-bindings.md) ve [Creating User-Defined bağlamaları](../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="35755-136"> creating your own binding using these two approaches, see [Custom Bindings](../../../docs/framework/wcf/extending/custom-bindings.md) and [Creating User-Defined Bindings](../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).</span></span>  
  
## <a name="using-bindings"></a><span data-ttu-id="35755-137">Bağlamaları kullanma</span><span class="sxs-lookup"><span data-stu-id="35755-137">Using Bindings</span></span>  
 <span data-ttu-id="35755-138">Bağlamalar kullanılarak iki temel adımları kapsar:</span><span class="sxs-lookup"><span data-stu-id="35755-138">Using bindings entails two basic steps:</span></span>  
  
1.  <span data-ttu-id="35755-139">Seçin veya bir bağlama tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="35755-139">Select or define a binding.</span></span> <span data-ttu-id="35755-140">İle birlikte gelen sistem tarafından sağlanan bağlamalar birini seçmek için kolay yöntemdir [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ve varsayılan ayarlarıyla kullanın.</span><span class="sxs-lookup"><span data-stu-id="35755-140">The easiest method is to choose one of the system-provided bindings included with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] and use it with its default settings.</span></span> <span data-ttu-id="35755-141">Ayrıca, sistem tarafından sağlanan bir bağlamayı seçin ve gereksinimlerinize uyacak şekilde özellik değerlerini sıfırlayın.</span><span class="sxs-lookup"><span data-stu-id="35755-141">You can also choose a system-provided binding and reset its property values to suit your requirements.</span></span> <span data-ttu-id="35755-142">Alternatif olarak, Denetim ve özelleştirme yüksek derece özel bağlama veya kullanıcı tanımlı bir bağlama oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35755-142">Alternatively, you can create a custom binding or a user-defined binding to have higher degrees of control and customization.</span></span>  
  
2.  <span data-ttu-id="35755-143">Seçili veya tanımlı bağlama kullanan bir uç nokta oluşturun.</span><span class="sxs-lookup"><span data-stu-id="35755-143">Create an endpoint that uses the binding selected or defined.</span></span>  
  
## <a name="code-and-configuration"></a><span data-ttu-id="35755-144">Kod ve yapılandırma</span><span class="sxs-lookup"><span data-stu-id="35755-144">Code and Configuration</span></span>  
 <span data-ttu-id="35755-145">İki yolla bağlamaları tanımlayabilirsiniz: kod veya yapılandırma aracılığıyla.</span><span class="sxs-lookup"><span data-stu-id="35755-145">You can define bindings in two ways: through code or through configuration.</span></span> <span data-ttu-id="35755-146">Bu iki yaklaşım, sistem tarafından sağlanan bir bağlamayı veya özel bağlama kullanma üzerinde güvenmeyin.</span><span class="sxs-lookup"><span data-stu-id="35755-146">These two approaches do not depend on whether you are using a system-provided binding or a custom binding.</span></span> <span data-ttu-id="35755-147">Genel olarak, kod kullanarak bir bağlama tasarım zamanında tanımı üzerinde tam denetim verir.</span><span class="sxs-lookup"><span data-stu-id="35755-147">In general, using code gives you complete control over the definition of a binding at design time.</span></span> <span data-ttu-id="35755-148">Yapılandırma, diğer yandan kullanarak sağlayan bir sistem yöneticisi veya kullanıcısı bir [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hizmet veya hizmet uygulamayı yeniden derlemenize gerek kalmadan bağlaması parametreleri değiştirmek için istemci.</span><span class="sxs-lookup"><span data-stu-id="35755-148">Using configuration, on the other hand, allows a system administrator or the user of a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service or client to change the parameters of a binding without having to recompile the service application.</span></span> <span data-ttu-id="35755-149">Bu esneklik çoğunlukla, belirli bir makine gereksinimlerini tahmin etmenin hiçbir yolu olduğundan tercih edilir. bir [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] uygulamasıdır dağıtılacak.</span><span class="sxs-lookup"><span data-stu-id="35755-149">This flexibility is often desirable because there is no way to predict specific machine requirements on which a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] application is to be deployed.</span></span> <span data-ttu-id="35755-150">Bağlama (ve adresleme) tutma bilgileri kodu dışında gerektirmeden yeniden derlenmek veya uygulama çözümünüzün yeniden dağıtımını değiştirmek için bunları sağlar.</span><span class="sxs-lookup"><span data-stu-id="35755-150">Keeping the binding (and the addressing) information out of the code allows them to change without requiring recompilation or redeployment of the application.</span></span> <span data-ttu-id="35755-151">Kod içinde tanımlanan bağlamaları sonra yapılandırma dosyasında belirtilen bağlamaları herhangi bir yapılandırma tanımlanmış bağlamaları üzerine yazmak kod tanımlı bağlamalar izin vererek oluşturulduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="35755-151">Note that bindings defined in code are created after bindings specified in configuration, allowing the code-defined bindings to overwrite any configuration-defined bindings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35755-152">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="35755-152">See Also</span></span>  
 [<span data-ttu-id="35755-153">Hizmetler ve istemcileri yapılandırmak için bağlamaları kullanma</span><span class="sxs-lookup"><span data-stu-id="35755-153">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)