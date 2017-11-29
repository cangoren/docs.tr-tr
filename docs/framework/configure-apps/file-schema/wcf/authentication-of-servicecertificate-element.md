---
title: "&lt;serviceCertificate&gt; Öğesi &lt;kimlik doğrulama&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 163a035c667c25be4f780daf85c50d96816bd0f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltauthenticationgt-of-ltservicecertificategt-element"></a><span data-ttu-id="01525-102">&lt;serviceCertificate&gt; Öğesi &lt;kimlik doğrulama&gt;</span><span class="sxs-lookup"><span data-stu-id="01525-102">&lt;authentication&gt; of &lt;serviceCertificate&gt; Element</span></span>
<span data-ttu-id="01525-103">SSL/TLS anlaşması kullanılarak elde edilen hizmet sertifikaların kimliğini doğrulamak için istemci Ara sunucusu tarafından kullanılan ayarları belirtir.</span><span class="sxs-lookup"><span data-stu-id="01525-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
 <span data-ttu-id="01525-104">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="01525-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="01525-105">\<davranışları ></span><span class="sxs-lookup"><span data-stu-id="01525-105">\<behaviors></span></span>  
<span data-ttu-id="01525-106">endpointBehaviors bölümü</span><span class="sxs-lookup"><span data-stu-id="01525-106">endpointBehaviors section</span></span>  
<span data-ttu-id="01525-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="01525-107">\<behavior></span></span>  
<span data-ttu-id="01525-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="01525-108">\<clientCredentials></span></span>  
<span data-ttu-id="01525-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="01525-109">\<serviceCertificate></span></span>  
<span data-ttu-id="01525-110">\<kimlik doğrulama ></span><span class="sxs-lookup"><span data-stu-id="01525-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01525-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="01525-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String" certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"   
trustedStoreLocation="LocalMachine/CurrentUser" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01525-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="01525-112">Attributes and Elements</span></span>  
 <span data-ttu-id="01525-113">Öznitelikler, alt öğelerini ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır</span><span class="sxs-lookup"><span data-stu-id="01525-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01525-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="01525-114">Attributes</span></span>  
  
|<span data-ttu-id="01525-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="01525-115">Attribute</span></span>|<span data-ttu-id="01525-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="01525-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01525-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="01525-117">customCertificateValidatorType</span></span>|<span data-ttu-id="01525-118">Dize.</span><span class="sxs-lookup"><span data-stu-id="01525-118">String.</span></span> <span data-ttu-id="01525-119">Tür ve bir özel tür doğrulamak için kullanılan derleme.</span><span class="sxs-lookup"><span data-stu-id="01525-119">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="01525-120">certificateValidationMode değerini</span><span class="sxs-lookup"><span data-stu-id="01525-120">certificateValidationMode</span></span>|<span data-ttu-id="01525-121">Kimlik bilgilerini doğrulamak için kullanılan üç modlarından birini belirtir.</span><span class="sxs-lookup"><span data-stu-id="01525-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="01525-122">Varsa kümesine `Custom`, sonra da bir customCertificateValidator de sağlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="01525-122">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="01525-123">Varsayılan, `ChainTrust` değeridir.</span><span class="sxs-lookup"><span data-stu-id="01525-123">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="01525-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="01525-124">revocationMode</span></span>|<span data-ttu-id="01525-125">İptal edilen sertifika (CRL) listeler denetlemek için kullanılan modlarından birini.</span><span class="sxs-lookup"><span data-stu-id="01525-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="01525-126">Varsayılan, `Online` değeridir.</span><span class="sxs-lookup"><span data-stu-id="01525-126">The default is `Online`.</span></span>|  
|<span data-ttu-id="01525-127">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="01525-127">trustedStoreLocation</span></span>|<span data-ttu-id="01525-128">İki sistem deposu konumlardan birini: `LocalMachine` veya `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="01525-128">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="01525-129">Bu değer, bir hizmet sertifikası istemciye anlaşıldığında kullanılır.</span><span class="sxs-lookup"><span data-stu-id="01525-129">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="01525-130">Doğrulama işlemi gerçekleştirildiğinde karşı **güvenilir kişiler** belirtilen depo konumda saklayın.</span><span class="sxs-lookup"><span data-stu-id="01525-130">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="01525-131">Varsayılan, `CurrentUser` değeridir.</span><span class="sxs-lookup"><span data-stu-id="01525-131">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="01525-132">customCertificateValidator özniteliği</span><span class="sxs-lookup"><span data-stu-id="01525-132">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="01525-133">Değer</span><span class="sxs-lookup"><span data-stu-id="01525-133">Value</span></span>|<span data-ttu-id="01525-134">Açıklama</span><span class="sxs-lookup"><span data-stu-id="01525-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="01525-135">Dize</span><span class="sxs-lookup"><span data-stu-id="01525-135">String</span></span>|<span data-ttu-id="01525-136">Tür adı ve derleme ve diğer veri türü bulmak için kullanılan belirtir.</span><span class="sxs-lookup"><span data-stu-id="01525-136">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="01525-137">certificateValidationMode değerini özniteliği</span><span class="sxs-lookup"><span data-stu-id="01525-137">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="01525-138">Değer</span><span class="sxs-lookup"><span data-stu-id="01525-138">Value</span></span>|<span data-ttu-id="01525-139">Açıklama</span><span class="sxs-lookup"><span data-stu-id="01525-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="01525-140">Sabit Listesi</span><span class="sxs-lookup"><span data-stu-id="01525-140">Enumeration</span></span>|<span data-ttu-id="01525-141">Aşağıdaki değerlerden biri: None, PeerTrust, ChainTrust, PeerOrChainTrust, özel.</span><span class="sxs-lookup"><span data-stu-id="01525-141">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="01525-142">Daha fazla bilgi için bkz: [sertifikalarla çalışma](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="01525-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="01525-143">revocationMode özniteliği</span><span class="sxs-lookup"><span data-stu-id="01525-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="01525-144">Değer</span><span class="sxs-lookup"><span data-stu-id="01525-144">Value</span></span>|<span data-ttu-id="01525-145">Açıklama</span><span class="sxs-lookup"><span data-stu-id="01525-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="01525-146">Sabit Listesi</span><span class="sxs-lookup"><span data-stu-id="01525-146">Enumeration</span></span>|<span data-ttu-id="01525-147">Aşağıdaki değerlerden birini: NoCheck, çevrimiçi, çevrimdışı.</span><span class="sxs-lookup"><span data-stu-id="01525-147">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="01525-148">Daha fazla bilgi için bkz: [sertifikalarla çalışma](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="01525-148">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="01525-149">trustedStoreLocation özniteliği</span><span class="sxs-lookup"><span data-stu-id="01525-149">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="01525-150">Değer</span><span class="sxs-lookup"><span data-stu-id="01525-150">Value</span></span>|<span data-ttu-id="01525-151">Açıklama</span><span class="sxs-lookup"><span data-stu-id="01525-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="01525-152">Sabit Listesi</span><span class="sxs-lookup"><span data-stu-id="01525-152">Enumeration</span></span>|<span data-ttu-id="01525-153">Aşağıdaki değerlerden birini: LocalMachine veya Currentuser'a.</span><span class="sxs-lookup"><span data-stu-id="01525-153">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="01525-154">Currentuser'a varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="01525-154">The default is CurrentUser.</span></span> <span data-ttu-id="01525-155">Sonra sertifika, genellikle istemci uygulamasının sistem hesabı altında çalışıyorsa, LocalMachine altında içindir.</span><span class="sxs-lookup"><span data-stu-id="01525-155">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="01525-156">İstemci uygulama bir kullanıcı hesabı altında çalışıyorsa, sertifika genellikle Currentuser'a içinde yok.</span><span class="sxs-lookup"><span data-stu-id="01525-156">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01525-157">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="01525-157">Child Elements</span></span>  
 <span data-ttu-id="01525-158">Yok.</span><span class="sxs-lookup"><span data-stu-id="01525-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01525-159">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="01525-159">Parent Elements</span></span>  
  
|<span data-ttu-id="01525-160">Öğe</span><span class="sxs-lookup"><span data-stu-id="01525-160">Element</span></span>|<span data-ttu-id="01525-161">Açıklama</span><span class="sxs-lookup"><span data-stu-id="01525-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01525-162">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="01525-162">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="01525-163">İstemci bir hizmete kimlik doğrulanırken kullanılacak bir sertifika belirtir.</span><span class="sxs-lookup"><span data-stu-id="01525-163">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01525-164">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="01525-164">Remarks</span></span>  
 <span data-ttu-id="01525-165">`certificateValidationMode` Bu yapılandırma öğesinin özniteliği sertifikaların kimliğini doğrulamak için kullanılan güven düzeyini belirtir.</span><span class="sxs-lookup"><span data-stu-id="01525-165">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="01525-166">Varsayılan olarak, düzeyini ayarlamak `ChainTrust`, belirten her sertifika zinciri üstündeki bir güvenilen sertifika yetkilisi biten sertifikaların bir hiyerarşideki bulunması gerekir.</span><span class="sxs-lookup"><span data-stu-id="01525-166">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="01525-167">Bu en güvenli bir moddur.</span><span class="sxs-lookup"><span data-stu-id="01525-167">This is the most secure mode.</span></span> <span data-ttu-id="01525-168">De değer ayarlayabilirsiniz `PeerOrChainTrust`, kendi kendine verilen sertifikaların (eş güven) güvenilen zincirinde sertifikaları yanı sıra kabul edileceğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="01525-168">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="01525-169">Bu değer, geliştirme ve kendi kendine verilen sertifikaların güvenilir bir yetkiliden satın alınması değil çünkü hata ayıklama istemcileri ve Hizmetleri zaman kullanılır.</span><span class="sxs-lookup"><span data-stu-id="01525-169">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="01525-170">Bir istemci dağıtımı sırasında kullanmak `ChainTrust` yerine değer.</span><span class="sxs-lookup"><span data-stu-id="01525-170">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="01525-171">De değer ayarlayabilirsiniz `Custom` veya `None`.</span><span class="sxs-lookup"><span data-stu-id="01525-171">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="01525-172">Kullanılacak `Custom` değeri de ayarlamanız gerekir `customCertificateValidator` özniteliği bir derleme ve sertifikayı doğrulamak için kullanılan türü.</span><span class="sxs-lookup"><span data-stu-id="01525-172">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="01525-173">Kendi özel Doğrulayıcısı oluşturmak için Özet X509CertificateValidator sınıfından devralınan gerekir.</span><span class="sxs-lookup"><span data-stu-id="01525-173">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="01525-174">Daha fazla bilgi için bkz: [nasıl yapılır: özel bir sertifika Doğrulayıcı kullanan bir hizmet oluşturma](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="01525-174">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="01525-175">`revocationMode` Özniteliği belirtir sertifika iptali için nasıl denetlenir.</span><span class="sxs-lookup"><span data-stu-id="01525-175">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="01525-176">Varsayılan değer `online` belirten sertifikaları iptal edilmek üzere otomatik olarak denetlenir.</span><span class="sxs-lookup"><span data-stu-id="01525-176">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="01525-177">Daha fazla bilgi için bkz: [sertifikalarla çalışma](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="01525-177">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01525-178">Örnek</span><span class="sxs-lookup"><span data-stu-id="01525-178">Example</span></span>  
 <span data-ttu-id="01525-179">Aşağıdaki örnekte, iki görevi yapar.</span><span class="sxs-lookup"><span data-stu-id="01525-179">The following example does two tasks.</span></span> <span data-ttu-id="01525-180">Öncelikle, istemcinin etki alanı adı uç ile iletişim kurmasını www.contoso.com HTTP protokolü üzerinden olduğunda kullanması bir hizmet sertifikası belirtir.</span><span class="sxs-lookup"><span data-stu-id="01525-180">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is www.contoso.com over the HTTP protocol.</span></span> <span data-ttu-id="01525-181">İkinci olarak, kimlik doğrulaması sırasında kullanılan iptal modu ve depolama konumunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="01525-181">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
```xml  
<serviceCertificate>  
  <defaultCertificate findValue="www.contoso.com"   
                      storeLocation="LocalMachine"  
                      storeName="TrustedPeople"   
                      x509FindType="FindByIssuerDistinguishedName" />  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
  <authentication revocationMode="Online"   
   trustedStoreLocation="LocalMachine" />  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01525-182">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="01525-182">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>  
 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>  
 [<span data-ttu-id="01525-183">Güvenlik davranışları</span><span class="sxs-lookup"><span data-stu-id="01525-183">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="01525-184">Sertifikalar ile çalışma</span><span class="sxs-lookup"><span data-stu-id="01525-184">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="01525-185">Nasıl yapılır: özel bir sertifika Doğrulayıcı kullanan bir hizmet oluşturma</span><span class="sxs-lookup"><span data-stu-id="01525-185">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="01525-186">\<kimlik doğrulama ></span><span class="sxs-lookup"><span data-stu-id="01525-186">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="01525-187">İstemcilerinin güvenliğini sağlama</span><span class="sxs-lookup"><span data-stu-id="01525-187">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="01525-188">Hizmetler ve istemcileri güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="01525-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)