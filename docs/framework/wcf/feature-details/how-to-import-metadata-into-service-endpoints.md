---
title: "Nasıl yapılır: Hizmet Uç Noktalarına Meta Verileri İçe Aktarma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b69dbe20-92a1-4911-89d8-ffbc3dad4663
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ca59de38ddb37260de5106a65419ebdc46f73151
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-import-metadata-into-service-endpoints"></a><span data-ttu-id="8940c-102">Nasıl yapılır: Hizmet Uç Noktalarına Meta Verileri İçe Aktarma</span><span class="sxs-lookup"><span data-stu-id="8940c-102">How to: Import Metadata into Service Endpoints</span></span>
<span data-ttu-id="8940c-103">Bu konu hizmet uç noktaları koleksiyona meta verileri alma ve içinde tanımlanan Hizmeti'yle açıklanmaktadır [Başlarken](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="8940c-103">This topic explains how to import metadata into a collection of service endpoints and use the service defined in the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="8940c-104">Bu konu hizmet ve çağrıları sonra meta verileri içe aktaran bir istemci uygulaması oluşturmak nasıl Göster `Add` hizmette yöntemi.</span><span class="sxs-lookup"><span data-stu-id="8940c-104">This topic show how to create a client application that imports metadata from the service and then calls the `Add` method on the service.</span></span>  
  
### <a name="to-import-metadata-into-service-endpoints"></a><span data-ttu-id="8940c-105">Hizmet uç noktalarına meta verileri içe aktarmak için</span><span class="sxs-lookup"><span data-stu-id="8940c-105">To import metadata into service endpoints</span></span>  
  
1.  <span data-ttu-id="8940c-106">Bildirme bir <xref:System.ServiceModel.EndpointAddress> nesne ve ile Tekdüzen Kaynak Tanımlayıcısı (URI) hizmeti meta veri değişimi (MEX) adresi için başlatılamıyor.</span><span class="sxs-lookup"><span data-stu-id="8940c-106">Declare an <xref:System.ServiceModel.EndpointAddress> object and initialize it with the Uniform Resource Identifier (URI) for the metadata exchange (MEX) address of the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#0)]  
  
2.  <span data-ttu-id="8940c-107">Oluşturma bir <xref:System.ServiceModel.Description.MetadataExchangeClient>, MEX adresi ve çağrı geçen <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="8940c-107">Create a <xref:System.ServiceModel.Description.MetadataExchangeClient>, passing in the MEX address, and call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span></span> <span data-ttu-id="8940c-108">Bu hizmeti meta verilerini alır.</span><span class="sxs-lookup"><span data-stu-id="8940c-108">This retrieves the metadata from the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#1)]  
  
3.  <span data-ttu-id="8940c-109">Oluşturma bir <xref:System.ServiceModel.Description.WsdlImporter>, daha önce listelene meta verileri ve çağrı geçen <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span><span class="sxs-lookup"><span data-stu-id="8940c-109">Create a <xref:System.ServiceModel.Description.WsdlImporter>, passing in the metadata previously retrieved, and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span></span> <span data-ttu-id="8940c-110">Bu koleksiyonu oluşturur <xref:System.ServiceModel.Description.ContractDescription> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="8940c-110">This generates a collection of <xref:System.ServiceModel.Description.ContractDescription> objects.</span></span> <span data-ttu-id="8940c-111">Ayrıca çağırabilirsiniz <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> veya <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, gereksinimlerinize bağlı.</span><span class="sxs-lookup"><span data-stu-id="8940c-111">You could also call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> or <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, depending upon your needs.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#2)]  
  
    > [!NOTE]
    >  <span data-ttu-id="8940c-112">Meta verileri içe aktardıktan sonra istemci kanal oluşturmak veya meta verilerini dışa aktarmak mümkün olmaz.</span><span class="sxs-lookup"><span data-stu-id="8940c-112">After you have imported the metadata, you will not be able to create a client channel or export the metadata.</span></span> <span data-ttu-id="8940c-113">Hiçbir tür bilgiler bu noktada kullanılamaz olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="8940c-113">This is because no type information is available at this point.</span></span> <span data-ttu-id="8940c-114">Tür bilgileri gerçekte hizmetiyle etkileşim veya meta verilerini dışa aktarmak için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="8940c-114">Type information is required to actually interact with the service or export metadata.</span></span> <span data-ttu-id="8940c-115">Tür bilgileri oluşturmak için adım 4 ve 5 gösterilen kodu oluşturmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="8940c-115">To generate the type information, you need to generate code, shown in steps 4 and 5.</span></span> <span data-ttu-id="8940c-116">Alternatif olarak, kullanabileceğinizi <xref:System.ServiceModel.Description.MetadataResolver> yardımcı sınıfı.</span><span class="sxs-lookup"><span data-stu-id="8940c-116">Alternatively, you could use the <xref:System.ServiceModel.Description.MetadataResolver> helper class.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="8940c-117">[Nasıl yapılır: bağlama meta verilerini dinamik olarak almak için MetadataResolver kullanma](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="8940c-117"> [How to: Use MetadataResolver to Obtain Binding Metadata Dynamically](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span></span>  
  
4.  <span data-ttu-id="8940c-118">Her sözleşme için tür bilgisi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="8940c-118">Generate type information for each contract.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#3)]  
  
5.  <span data-ttu-id="8940c-119">Artık bu bilgileri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8940c-119">Now you can use this information.</span></span> <span data-ttu-id="8940c-120">Aşağıdaki örnek, C# kaynak kodu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="8940c-120">The following sample generates C# source code.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8940c-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8940c-121">See Also</span></span>  
 [<span data-ttu-id="8940c-122">Meta veriler</span><span class="sxs-lookup"><span data-stu-id="8940c-122">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="8940c-123">Başlarken</span><span class="sxs-lookup"><span data-stu-id="8940c-123">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)