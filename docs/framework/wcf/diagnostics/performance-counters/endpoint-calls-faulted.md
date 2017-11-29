---
title: "Uç Noktası: Hatalı Çağrılar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 271e6284-9c4b-465f-b619-069e1555a5e4
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d62eb1ad10c7112696d8fa2a358db4c88ee86cb3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-calls-faulted"></a><span data-ttu-id="a77b0-102">Uç Noktası: Hatalı Çağrılar</span><span class="sxs-lookup"><span data-stu-id="a77b0-102">Endpoint: Calls Faulted</span></span>
<span data-ttu-id="a77b0-103">Sayaç adı: Hatalı çağrılar.</span><span class="sxs-lookup"><span data-stu-id="a77b0-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a77b0-104">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a77b0-104">Description</span></span>  
 <span data-ttu-id="a77b0-105">Bu uç noktaya döndürmüş çağrı sayısı.</span><span class="sxs-lookup"><span data-stu-id="a77b0-105">Number of calls to this endpoint that have returned faults.</span></span> <span data-ttu-id="a77b0-106">İçinde [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] uygulamalar, hizmet yöntemleri iletişim SOAP hata iletileri kullanarak hata bilgilerini işleme.</span><span class="sxs-lookup"><span data-stu-id="a77b0-106">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="a77b0-107">SOAP, bir hizmet işlemi için meta verileri içinde yer alan ve bu nedenle istemcilerin kendi yürütme daha sağlam veya etkileşimli yapmak için kullanabileceği bir hataya sözleşmesi oluşturma ileti türlerini hatalarıdır.</span><span class="sxs-lookup"><span data-stu-id="a77b0-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="a77b0-108">XML formundaki istemcilere SOAP hataları ifade olduğundan, yüksek oranda birlikte çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="a77b0-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a77b0-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a77b0-109">See Also</span></span>  
 [<span data-ttu-id="a77b0-110">Belirtme ve sözleşme ve hizmetlerde hataları işleme</span><span class="sxs-lookup"><span data-stu-id="a77b0-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)