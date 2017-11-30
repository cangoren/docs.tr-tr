---
title: "&lt;peerAuthentication&gt; Öğesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3cc625f5fdb20505f2e36c5a2d37fca0676bbb37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltpeerauthenticationgt-element"></a><span data-ttu-id="ae5e2-102">&lt;peerAuthentication&gt; Öğesi</span><span class="sxs-lookup"><span data-stu-id="ae5e2-102">&lt;peerAuthentication&gt; Element</span></span>
<span data-ttu-id="ae5e2-103">Eşler arası istemciler için kimlik doğrulama seçeneklerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="ae5e2-104">eşler arası programlama, bkz: [eşler arası ağ](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="ae5e2-104"> peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="ae5e2-105">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ae5e2-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="ae5e2-106">\<davranışları ></span><span class="sxs-lookup"><span data-stu-id="ae5e2-106">\<behaviors></span></span>  
<span data-ttu-id="ae5e2-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ae5e2-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="ae5e2-108">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="ae5e2-108">\<behavior></span></span>  
<span data-ttu-id="ae5e2-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="ae5e2-109">\<clientCredentials></span></span>  
<span data-ttu-id="ae5e2-110">\<Eş ></span><span class="sxs-lookup"><span data-stu-id="ae5e2-110">\<peer></span></span>  
<span data-ttu-id="ae5e2-111">\<PeerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="ae5e2-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae5e2-112">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ae5e2-112">Syntax</span></span>  
  
```xml  
<peerAuthentication  
customCertificateValidatorType = "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae5e2-113">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="ae5e2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ae5e2-114">Öznitelikler, alt öğelerini ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır</span><span class="sxs-lookup"><span data-stu-id="ae5e2-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae5e2-115">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="ae5e2-115">Attributes</span></span>  
  
|<span data-ttu-id="ae5e2-116">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="ae5e2-116">Attribute</span></span>|<span data-ttu-id="ae5e2-117">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ae5e2-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="ae5e2-118">İsteğe bağlı dize.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-118">Optional string.</span></span> <span data-ttu-id="ae5e2-119">Tür ve bir özel tür doğrulamak için kullanılan derleme.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="ae5e2-120">Bu öznitelik ne zaman ayarlanmalıdır `certificateValidationMode` ayarlanır `Custom`.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certifcateValidationMode`|<span data-ttu-id="ae5e2-121">İsteğe bağlı numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-121">Optional enumeration.</span></span> <span data-ttu-id="ae5e2-122">Kimlik bilgilerini doğrulamak için kullanılan üç modlarından birini belirtir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="ae5e2-123">Varsa kümesine `Custom`, sonra bir `customCertificateValidator` de sağlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="ae5e2-124">Varsayılan, `ChainTrust` değeridir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="ae5e2-125">İsteğe bağlı numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-125">Optional enumeration.</span></span> <span data-ttu-id="ae5e2-126">İptal edilen sertifika (CRL) listeler denetlemek için kullanılan modlarından birini.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="ae5e2-127">Varsayılan, `Online` değeridir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="ae5e2-128">İsteğe bağlı numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-128">Optional enumeration.</span></span> <span data-ttu-id="ae5e2-129">İki sistem deposu konumlardan birini: `LocalMachine` veya `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="ae5e2-130">Bu değer, bir hizmet sertifikası istemciye anlaşıldığında kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="ae5e2-131">Doğrulama işlemi gerçekleştirildiğinde karşı **güvenilir kişiler** belirtilen depo konumda saklayın.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="ae5e2-132">Varsayılan, `CurrentUser` değeridir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="ae5e2-133">customCertificateValidatorType özniteliği</span><span class="sxs-lookup"><span data-stu-id="ae5e2-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="ae5e2-134">Değer</span><span class="sxs-lookup"><span data-stu-id="ae5e2-134">Value</span></span>|<span data-ttu-id="ae5e2-135">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ae5e2-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae5e2-136">Dize</span><span class="sxs-lookup"><span data-stu-id="ae5e2-136">String</span></span>|<span data-ttu-id="ae5e2-137">Tür adı ve derleme ve diğer veri türü bulmak için kullanılan belirtir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="ae5e2-138">En azından bir ad ve tür adı gereklidir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="ae5e2-139">İsteğe bağlı bilgileri içerir: derleme adı, sürüm numarası, kültür ve ortak anahtar belirteci.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="ae5e2-140">certificateValidationMode değerini özniteliği</span><span class="sxs-lookup"><span data-stu-id="ae5e2-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="ae5e2-141">Değer</span><span class="sxs-lookup"><span data-stu-id="ae5e2-141">Value</span></span>|<span data-ttu-id="ae5e2-142">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ae5e2-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae5e2-143">Sabit Listesi</span><span class="sxs-lookup"><span data-stu-id="ae5e2-143">Enumeration</span></span>|<span data-ttu-id="ae5e2-144">Aşağıdaki değerlerden birini: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="ae5e2-145">Varsayılan, `ChainTrust` değeridir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="ae5e2-146">Daha fazla bilgi için bkz: [sertifikalarla çalışma](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="ae5e2-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="ae5e2-147">revocationMode özniteliği</span><span class="sxs-lookup"><span data-stu-id="ae5e2-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="ae5e2-148">Değer</span><span class="sxs-lookup"><span data-stu-id="ae5e2-148">Value</span></span>|<span data-ttu-id="ae5e2-149">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ae5e2-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae5e2-150">Sabit Listesi</span><span class="sxs-lookup"><span data-stu-id="ae5e2-150">Enumeration</span></span>|<span data-ttu-id="ae5e2-151">Aşağıdaki değerlerden birini: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="ae5e2-152">Varsayılan, `Online` değeridir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="ae5e2-153">Daha fazla bilgi için bkz: [sertifikalarla çalışma](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="ae5e2-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="ae5e2-154">trustedStoreLocation özniteliği</span><span class="sxs-lookup"><span data-stu-id="ae5e2-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="ae5e2-155">Değer</span><span class="sxs-lookup"><span data-stu-id="ae5e2-155">Value</span></span>|<span data-ttu-id="ae5e2-156">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ae5e2-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae5e2-157">Sabit Listesi</span><span class="sxs-lookup"><span data-stu-id="ae5e2-157">Enumeration</span></span>|<span data-ttu-id="ae5e2-158">Aşağıdaki değerlerden birini: `LocalMachine` veya `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="ae5e2-159">Varsayılan, `CurrentUser` değeridir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="ae5e2-160">İstemci uygulaması bir sistem hesabı altında çalışan sonra sertifika genellikle altında olduğu `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="ae5e2-161">İstemci uygulama bir kullanıcı hesabı altında çalışan sonra sertifikayı genellikle kullanımda `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae5e2-162">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="ae5e2-162">Child Elements</span></span>  
 <span data-ttu-id="ae5e2-163">Yok.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae5e2-164">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="ae5e2-164">Parent Elements</span></span>  
  
|<span data-ttu-id="ae5e2-165">Öğe</span><span class="sxs-lookup"><span data-stu-id="ae5e2-165">Element</span></span>|<span data-ttu-id="ae5e2-166">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ae5e2-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae5e2-167">\<Eş ></span><span class="sxs-lookup"><span data-stu-id="ae5e2-167">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="ae5e2-168">İstemci bir eş hizmeti için kimlik doğrulaması için kullanılan kimlik bilgisini belirtir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae5e2-169">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ae5e2-169">Remarks</span></span>  
 <span data-ttu-id="ae5e2-170">`<authentication>` Öğesi karşılık gelen <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="ae5e2-171">Bu öğe kafes komşu komşu kimlik doğrulaması sırasında çağrılan bir doğrulayıcı belirtir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="ae5e2-172">Yeni bir eş komşu bağlantısı kurmaya çalıştığında, yanıt vermeyen eşler arası kendi kimlik bilgisi geçirir.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="ae5e2-173">Yanıtlayıcı Doğrulayıcı uzak taraf kimlik doğrulamak için çağrılır.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="ae5e2-174">Mesh bir eş bağlantı olduğunda, hem eş karşılıklı kimlik doğrulaması, iki ucunda anlamı doğrulayıcıları çağrılır.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae5e2-175">Örnek</span><span class="sxs-lookup"><span data-stu-id="ae5e2-175">Example</span></span>  
 <span data-ttu-id="ae5e2-176">Aşağıdaki kod sertifika doğrulama modunu ayarlar `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
     <peerAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
     <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae5e2-177">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ae5e2-177">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="ae5e2-178">Sertifikalar ile çalışma</span><span class="sxs-lookup"><span data-stu-id="ae5e2-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="ae5e2-179">Eşler arası ağ</span><span class="sxs-lookup"><span data-stu-id="ae5e2-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="ae5e2-180">Eş kanal ileti kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="ae5e2-180">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="ae5e2-181">Eş kanal özel kimlik doğrulama</span><span class="sxs-lookup"><span data-stu-id="ae5e2-181">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="ae5e2-182">Eş kanalı uygulamalarını güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="ae5e2-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)