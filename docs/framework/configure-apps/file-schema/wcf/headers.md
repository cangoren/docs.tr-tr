---
title: "&lt;üstbilgileri&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bcc81c0dd0628a6c5cab93841665b416f18a5bff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltheadersgt"></a><span data-ttu-id="5b679-102">&lt;üstbilgileri&gt;</span><span class="sxs-lookup"><span data-stu-id="5b679-102">&lt;headers&gt;</span></span>
<span data-ttu-id="5b679-103">Bir uç nokta temel URI'sini yanı sıra bir veya daha fazla SOAP üstbilgileri çözülebilir.</span><span class="sxs-lookup"><span data-stu-id="5b679-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="5b679-104">Bu faydalı olduğu senaryolar bir dizi, burada bir uç nokta aracılar hedeflenen SOAP üstbilgileri dahil etmek Bu uç noktanın gerektirir. istemciler SOAP Ara senaryoları kümesidir.</span><span class="sxs-lookup"><span data-stu-id="5b679-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="5b679-105">Bu yapılandırma öğesi, bu tür özel adres üstbilgileri tanımlamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="5b679-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="5b679-106">Uç nokta üstbilgi koleksiyonu girişleri, kullanıcı tanımlı XML öğelerdir.</span><span class="sxs-lookup"><span data-stu-id="5b679-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="5b679-107">Doğru biçimlendirilmiş olması her öğeye sahip XML.</span><span class="sxs-lookup"><span data-stu-id="5b679-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="5b679-108">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5b679-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="5b679-109">\<İstemci ></span><span class="sxs-lookup"><span data-stu-id="5b679-109">\<client></span></span>  
<span data-ttu-id="5b679-110">\<uç noktası ></span><span class="sxs-lookup"><span data-stu-id="5b679-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b679-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="5b679-111">Syntax</span></span>  
  
```xml  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b679-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="5b679-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5b679-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="5b679-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b679-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="5b679-114">Attributes</span></span>  
 <span data-ttu-id="5b679-115">Yok.</span><span class="sxs-lookup"><span data-stu-id="5b679-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5b679-116">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="5b679-116">Child Elements</span></span>  
  
|<span data-ttu-id="5b679-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="5b679-117">Element</span></span>|<span data-ttu-id="5b679-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="5b679-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b679-119">Bölge</span><span class="sxs-lookup"><span data-stu-id="5b679-119">Region</span></span>||  
|<span data-ttu-id="5b679-120">Üye</span><span class="sxs-lookup"><span data-stu-id="5b679-120">Member</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="5b679-121">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="5b679-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5b679-122">Öğe</span><span class="sxs-lookup"><span data-stu-id="5b679-122">Element</span></span>|<span data-ttu-id="5b679-123">Açıklama</span><span class="sxs-lookup"><span data-stu-id="5b679-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b679-124">\<uç noktası ></span><span class="sxs-lookup"><span data-stu-id="5b679-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="5b679-125">Farklı türde uç noktalar yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="5b679-125">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b679-126">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5b679-126">Remarks</span></span>  
 <span data-ttu-id="5b679-127">İsteğe bağlı üstbilgi tanımlamak veya uç noktasıyla etkileşim için adresleme daha ayrıntılı bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="5b679-127">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="5b679-128">Örneğin, üstbilgileri gelen iletiyi işlemeye nasıl, burada uç nokta bir yanıt iletisi göndermesi gerekir veya birden çok örneği kullanılamadığında belirli bir kullanıcıdan gelen iletiyi işlemek için kullanılacak bir hizmetin hangi örneğinin gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="5b679-128">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b679-129">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5b679-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [<span data-ttu-id="5b679-130">Uç noktalar: Adresler, bağlamalar ve sözleşmeler</span><span class="sxs-lookup"><span data-stu-id="5b679-130">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)