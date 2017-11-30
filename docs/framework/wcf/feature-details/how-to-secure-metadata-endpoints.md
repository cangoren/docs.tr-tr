---
title: "Nasıl yapılır: Meta Veri Uç Noktalarını Güvenli Hale Getirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 9f71b6ae-737c-4382-8d89-0a7b1c7e182b
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e28b4dec851cc4115c2688540ebee151c91e4cd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-secure-metadata-endpoints"></a><span data-ttu-id="75abe-102">Nasıl yapılır: Meta Veri Uç Noktalarını Güvenli Hale Getirme</span><span class="sxs-lookup"><span data-stu-id="75abe-102">How to: Secure Metadata Endpoints</span></span>
<span data-ttu-id="75abe-103">Bir hizmet için meta verileri, kötü niyetli bir kullanıcının yararlanabilirsiniz uygulamanız ile ilgili gizli bilgiler içerebilir.</span><span class="sxs-lookup"><span data-stu-id="75abe-103">Metadata for a service can contain sensitive information about your application that a malicious user can leverage.</span></span> <span data-ttu-id="75abe-104">Hizmetinizin Tüketiciler, hizmetiniz hakkındaki meta verileri almak için güvenli bir mekanizma de gerektirebilir.</span><span class="sxs-lookup"><span data-stu-id="75abe-104">Consumers of your service may also require a secure mechanism for obtaining metadata about your service.</span></span> <span data-ttu-id="75abe-105">Bu nedenle, bazen kullanarak güvenli bir uç noktası, meta verilerini yayımlamak gereklidir.</span><span class="sxs-lookup"><span data-stu-id="75abe-105">Therefore, it is sometimes necessary to publish your metadata using a secure endpoint.</span></span>  
  
 <span data-ttu-id="75abe-106">Meta veri uç noktaları genellikle güvenli tanımlanan standart güvenlik mekanizmalarını kullanarak [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uygulama uç noktalarını güvenli hale getirmek için.</span><span class="sxs-lookup"><span data-stu-id="75abe-106">Metadata endpoints are generally secured using the standard security mechanisms defined in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] for securing application endpoints.</span></span> <span data-ttu-id="75abe-107">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Güvenliğine genel bakış](../../../../docs/framework/wcf/feature-details/security-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="75abe-107">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Security Overview](../../../../docs/framework/wcf/feature-details/security-overview.md).)</span></span>  
  
 <span data-ttu-id="75abe-108">Bu konuda bir Güvenli Yuva Katmanı (SSL) sertifikası veya bir HTTPS uç noktası tarafından diğer bir deyişle, güvenli bir uç nokta oluşturmak için adım adım anlatılmaktadır.</span><span class="sxs-lookup"><span data-stu-id="75abe-108">This topic walks through the steps to create an endpoint secured by a Secure Sockets Layer (SSL) certificate or, in other words, an HTTPS endpoint.</span></span>  
  
### <a name="to-create-a-secure-https-get-metadata-endpoint-in-code"></a><span data-ttu-id="75abe-109">Güvenli bir HTTPS alma meta veri uç kodu oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="75abe-109">To create a secure HTTPS GET metadata endpoint in code</span></span>  
  
1.  <span data-ttu-id="75abe-110">Bir bağlantı noktası uygun bir X.509 sertifikası ile yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="75abe-110">Configure a port with an appropriate X.509 certificate.</span></span> <span data-ttu-id="75abe-111">Sertifika güvenilir bir yetkiliden gelmesi gerekir ve bir kullanım amacı "Hizmetinin yetkilendirmesi" olması gerekir</span><span class="sxs-lookup"><span data-stu-id="75abe-111">The certificate must come from a trusted authority, and it must have an intended use of "Service Authorization."</span></span> <span data-ttu-id="75abe-112">Bağlantı noktasına sertifika eklemek için HttpCfg.exe aracını kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="75abe-112">You must use the HttpCfg.exe tool to attach the certificate to the port.</span></span> <span data-ttu-id="75abe-113">Bkz: [nasıl yapılır: bir SSL sertifikası ile bir bağlantı noktası yapılandırın](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="75abe-113">See [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="75abe-114">Sertifika veya kendi etki alanı adı sistemi (DNS) bilgisayarın adı eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="75abe-114">The subject of the certificate or its Domain Name System (DNS) must match the name of the computer.</span></span> <span data-ttu-id="75abe-115">Sertifika için aynı Tekdüzen Kaynak Tanımlayıcısı (URI) bağlı çağrılır adresi olarak verilmeden denetlemek için HTTPS mekanizması gerçekleştirir ilk adımlarından biri olduğu için bu önemlidir.</span><span class="sxs-lookup"><span data-stu-id="75abe-115">This is essential because one of the first steps the HTTPS mechanism performs is to check that the certificate is issued to the same Uniform Resource Identifier (URI) as the address upon which it is invoked.</span></span>  
  
2.  <span data-ttu-id="75abe-116">Yeni bir örneğini oluşturmak <xref:System.ServiceModel.Description.ServiceMetadataBehavior> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="75abe-116">Create a new instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class.</span></span>  
  
3.  <span data-ttu-id="75abe-117">Ayarlama <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> özelliği <xref:System.ServiceModel.Description.ServiceMetadataBehavior> sınıfının `true`.</span><span class="sxs-lookup"><span data-stu-id="75abe-117">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> property of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class to `true`.</span></span>  
  
4.  <span data-ttu-id="75abe-118">Ayarlama <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> uygun bir URL'ye özelliği.</span><span class="sxs-lookup"><span data-stu-id="75abe-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> property to an appropriate URL.</span></span> <span data-ttu-id="75abe-119">Mutlak bir adres belirtirseniz, URL şeması "https://" ile başlamalıdır unutmayın.</span><span class="sxs-lookup"><span data-stu-id="75abe-119">Note that if you specify an absolute address, the URL must begin with the scheme "https://".</span></span> <span data-ttu-id="75abe-120">Göreli bir adresi belirtirseniz, hizmet konağınız için bir HTTPS temel adresi girmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="75abe-120">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="75abe-121">Bu özellik ayarlanmamışsa varsayılan adresidir "", veya doğrudan hizmeti için HTTPS temel adres.</span><span class="sxs-lookup"><span data-stu-id="75abe-121">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>  
  
5.  <span data-ttu-id="75abe-122">Örnek davranışları koleksiyona eklemek, <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> özelliği <xref:System.ServiceModel.Description.ServiceDescription> aşağıdaki kodda gösterildiği gibi sınıf döndürür.</span><span class="sxs-lookup"><span data-stu-id="75abe-122">Add the instance to the behaviors collection that the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property of the <xref:System.ServiceModel.Description.ServiceDescription> class returns, as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowToSecureEndpoint#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#1)]
     [!code-vb[c_HowToSecureEndpoint#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#1)]  
  
### <a name="to-create-a-secure-https-get-metadata-endpoint-in-configuration"></a><span data-ttu-id="75abe-123">Güvenli bir HTTPS alma meta veri uç yapılandırmasında oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="75abe-123">To create a secure HTTPS GET metadata endpoint in configuration</span></span>  
  
1.  <span data-ttu-id="75abe-124">Ekleme bir [ \<davranışları >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) öğesine [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) hizmetiniz için yapılandırma dosyası öğesi.</span><span class="sxs-lookup"><span data-stu-id="75abe-124">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element of the configuration file for your service.</span></span>  
  
2.  <span data-ttu-id="75abe-125">Ekleme bir [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) öğesine [ \<davranışları >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="75abe-125">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) element to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
3.  <span data-ttu-id="75abe-126">Ekleme bir [ \<davranışı >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) öğesine `<serviceBehaviors>` öğesi.</span><span class="sxs-lookup"><span data-stu-id="75abe-126">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element to the `<serviceBehaviors>` element.</span></span>  
  
4.  <span data-ttu-id="75abe-127">Ayarlama `name` özniteliği `<behavior>` uygun bir değere öğesi.</span><span class="sxs-lookup"><span data-stu-id="75abe-127">Set the `name` attribute of the `<behavior>` element to an appropriate value.</span></span> <span data-ttu-id="75abe-128">`name` Özniteliği gereklidir.</span><span class="sxs-lookup"><span data-stu-id="75abe-128">The `name` attribute is required.</span></span> <span data-ttu-id="75abe-129">Aşağıdaki örnek değeri kullanır `mySvcBehavior`.</span><span class="sxs-lookup"><span data-stu-id="75abe-129">The example below uses the value `mySvcBehavior`.</span></span>  
  
5.  <span data-ttu-id="75abe-130">Ekleme bir [ \<serviceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) için `<behavior>` öğesi.</span><span class="sxs-lookup"><span data-stu-id="75abe-130">Add a [\<serviceMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) to the `<behavior>` element.</span></span>  
  
6.  <span data-ttu-id="75abe-131">Ayarlama `httpsGetEnabled` özniteliği `<serviceMetadata>` öğesine `true`.</span><span class="sxs-lookup"><span data-stu-id="75abe-131">Set the `httpsGetEnabled` attribute of the `<serviceMetadata>` element to `true`.</span></span>  
  
7.  <span data-ttu-id="75abe-132">Ayarlama `httpsGetUrl` özniteliği `<serviceMetadata>` uygun bir değere öğesi.</span><span class="sxs-lookup"><span data-stu-id="75abe-132">Set the `httpsGetUrl` attribute of the `<serviceMetadata>` element to an appropriate value.</span></span> <span data-ttu-id="75abe-133">Mutlak bir adres belirtirseniz, URL şeması "https://" ile başlamalıdır unutmayın.</span><span class="sxs-lookup"><span data-stu-id="75abe-133">Note that if you specify an absolute address, the URL must begin with the scheme "https://".</span></span> <span data-ttu-id="75abe-134">Göreli bir adresi belirtirseniz, hizmet konağınız için bir HTTPS temel adresi girmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="75abe-134">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="75abe-135">Bu özellik ayarlanmamışsa varsayılan adresidir "", veya doğrudan hizmeti için HTTPS temel adres.</span><span class="sxs-lookup"><span data-stu-id="75abe-135">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>  
  
8.  <span data-ttu-id="75abe-136">Bir hizmetle davranışı kullanmak üzere ayarlanmış `behaviorConfiguration` özniteliği [ \<hizmet >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) davranışı öğesinin ad özniteliği değeri öğesine.</span><span class="sxs-lookup"><span data-stu-id="75abe-136">To use the behavior with a service, set the `behaviorConfiguration` attribute of the [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) element to the value of the name attribute of the behavior element.</span></span> <span data-ttu-id="75abe-137">Aşağıdaki yapılandırma kodunu tam bir örnek gösterilir.</span><span class="sxs-lookup"><span data-stu-id="75abe-137">The following configuration code shows a complete example.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="mySvcBehavior">  
         <serviceMetadata httpsGetEnabled="true"   
              httpsGetUrl="https://localhost:8036/calcMetadata" />  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
     <services>  
      <service behaviorConfiguration="mySvcBehavior"   
            name="Microsoft.Security.Samples.Calculator">  
       <endpoint address="http://localhost:8037/ServiceModelSamples/calculator"  
       binding="wsHttpBinding" bindingConfiguration=""     
       contract="Microsoft.Security.Samples.ICalculator" />  
      </service>  
     </services>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
## <a name="example"></a><span data-ttu-id="75abe-138">Örnek</span><span class="sxs-lookup"><span data-stu-id="75abe-138">Example</span></span>  
 <span data-ttu-id="75abe-139">Aşağıdaki örnek, bir örneğini oluşturur. bir <xref:System.ServiceModel.ServiceHost> sınıfı ve bir uç nokta ekler.</span><span class="sxs-lookup"><span data-stu-id="75abe-139">The following example creates an instance of a <xref:System.ServiceModel.ServiceHost> class and adds an endpoint.</span></span> <span data-ttu-id="75abe-140">Kod sonra bir örneğini oluşturur <xref:System.ServiceModel.Description.ServiceMetadataBehavior> sınıfı ve bir güvenli meta verileri exchange noktası oluşturmak için özellikleri ayarlar.</span><span class="sxs-lookup"><span data-stu-id="75abe-140">The code then creates an instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class and sets the properties to create a secure metadata exchange point.</span></span>  
  
 [!code-csharp[c_HowToSecureEndpoint#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#0)]
 [!code-vb[c_HowToSecureEndpoint#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="75abe-141">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="75abe-141">Compiling the Code</span></span>  
 <span data-ttu-id="75abe-142">Kod örneği, şu ad alanlarından kullanır:</span><span class="sxs-lookup"><span data-stu-id="75abe-142">The code example uses the following namespaces:</span></span>  
  
-   <xref:System.ServiceModel?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Description?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="75abe-143">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="75abe-143">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>  
 [<span data-ttu-id="75abe-144">Nasıl yapılır: bir SSL sertifikası ile bir bağlantı noktası yapılandırın</span><span class="sxs-lookup"><span data-stu-id="75abe-144">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [<span data-ttu-id="75abe-145">Sertifikalar ile çalışma</span><span class="sxs-lookup"><span data-stu-id="75abe-145">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="75abe-146">Meta veriler hakkında güvenlik konuları</span><span class="sxs-lookup"><span data-stu-id="75abe-146">Security Considerations with Metadata</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)  
 [<span data-ttu-id="75abe-147">Hizmetler ve istemcileri güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="75abe-147">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)