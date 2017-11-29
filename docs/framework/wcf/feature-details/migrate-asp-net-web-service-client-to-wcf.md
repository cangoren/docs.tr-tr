---
title: "Nasıl yapılır: ASP.NET Web Hizmeti İstemci Kodunu Windows Communication Foundation'a Taşıma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d77e07cca938b67f5b79416ac4d8fdef96739ed2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a><span data-ttu-id="e4cfe-102">Nasıl yapılır: ASP.NET Web Hizmeti İstemci Kodunu Windows Communication Foundation'a Taşıma</span><span class="sxs-lookup"><span data-stu-id="e4cfe-102">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="e4cfe-103">ASP.NET Web hizmeti istemci kodunu geçirmek için izlenmesi gereken genel adımlar aşağıdaki yordamda açıklanmıştır [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4cfe-103">The following procedure describes the broad steps that need to be followed to migrate ASP.NET Web Service client code to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="e4cfe-104">Yordam</span><span class="sxs-lookup"><span data-stu-id="e4cfe-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a><span data-ttu-id="e4cfe-105">WCF için ASP.NET Web hizmeti istemci kodunu geçirmek için</span><span class="sxs-lookup"><span data-stu-id="e4cfe-105">To migrate ASP.NET Web Service client code to WCF</span></span>  
  
1.  <span data-ttu-id="e4cfe-106">Kapsamlı bir emin testleri kümesini istemci için mevcut.</span><span class="sxs-lookup"><span data-stu-id="e4cfe-106">Ensure that a comprehensive set of tests exist for the client.</span></span>  
  
2.  <span data-ttu-id="e4cfe-107">.NET 2.0 istemci uygulamaya yükseltmek için Visual Studio 2005 kullanın.</span><span class="sxs-lookup"><span data-stu-id="e4cfe-107">Use Visual Studio 2005 to upgrade the client application to .NET 2.0.</span></span> <span data-ttu-id="e4cfe-108">Test kümesini çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="e4cfe-108">Run the set of tests.</span></span>  
  
3.  <span data-ttu-id="e4cfe-109">ASP.NET istemci kodu istemci projeden kaldırın.</span><span class="sxs-lookup"><span data-stu-id="e4cfe-109">Remove ASP.NET client code from the client project.</span></span> <span data-ttu-id="e4cfe-110">Kod modülleri WSDL.exe aracı kullanılarak oluşturulan olduğunu.</span><span class="sxs-lookup"><span data-stu-id="e4cfe-110">That code is in modules generated using the WSDL.exe tool.</span></span>  
  
4.  <span data-ttu-id="e4cfe-111">Oluştur [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] istemci kodu kullanarak [ServiceModel meta veri yardımcı Programracı (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e4cfe-111">Generate [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client code using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="e4cfe-112">Bu kod istemci projenize ekleyin ve istemcinin var olan yapılandırma dosyasına yapılandırma çıktısını birleştirin.</span><span class="sxs-lookup"><span data-stu-id="e4cfe-112">Add that code to the client project and merge the configuration output into the client’s existing configuration file.</span></span>  
  
5.  <span data-ttu-id="e4cfe-113">Uygulamayı derleyin.</span><span class="sxs-lookup"><span data-stu-id="e4cfe-113">Compile the application.</span></span> <span data-ttu-id="e4cfe-114">Yeni başvuruları eski ASP.NET istemci tür başvuruları değiştirerek derleme hataları onarmak [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] istemci türü.</span><span class="sxs-lookup"><span data-stu-id="e4cfe-114">Repair the compilation errors by replacing references to the former ASP.NET client types with references to the new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client types.</span></span>  
  
6.  <span data-ttu-id="e4cfe-115">Test kümesini çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="e4cfe-115">Run the set of tests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4cfe-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e4cfe-116">See Also</span></span>  
 [<span data-ttu-id="e4cfe-117">Nasıl yapılır: ASP.NET Web hizmeti kodunu Windows Communication Foundation'a taşıma</span><span class="sxs-lookup"><span data-stu-id="e4cfe-117">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)