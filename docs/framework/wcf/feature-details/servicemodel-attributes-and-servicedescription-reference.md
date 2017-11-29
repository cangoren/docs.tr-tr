---
title: "ServiceModel Öznitelikleri ve ServiceDescription Başvurusu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ab86b17-eab9-4846-a881-0099f9a7cc64
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ba41bd63f1dc23441cc7f265a8b1339d0b1194d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="servicemodel-attributes-and-servicedescription-reference"></a><span data-ttu-id="0c862-102">ServiceModel Öznitelikleri ve ServiceDescription Başvurusu</span><span class="sxs-lookup"><span data-stu-id="0c862-102">ServiceModel Attributes and ServiceDescription Reference</span></span>
<span data-ttu-id="0c862-103">*Açıklama ağaç* türleri hiyerarşisidir (ile başlayan <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> sınıfı), bir hizmetin her açıdan birlikte açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="0c862-103">The *description tree* is the hierarchy of types (starting with the <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> class) that together describe every aspect of a service.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="0c862-104">Web Hizmetleri Açıklama Dili (WSDL), XML Şeması Tanım Dili (XSD) ve ilke onaylamalarını (meta verileri) ve istemcilerin bağlanmak ve hizmeti kullanmak için kullandığı hizmet hakkında yayımlamak için geçerli bir hizmet çalışma zamanı oluşturmak için kullandığı bir açıklama ağacı çeşitli kod ve yapılandırma dosyası gösterimlerini açıklama ağaç değerleri oluşturur.</span><span class="sxs-lookup"><span data-stu-id="0c862-104"> uses a description tree to build a valid service runtime, to publish Web Services Description Language (WSDL), XML Schema definition language (XSD), and policy assertions (metadata) about the service that clients can use to connect to and use the service, and to generate various code and configuration file representations of the description tree values.</span></span>  
  
 <span data-ttu-id="0c862-105">Bu konuda, nasıl sözleşme ilgili özellikler açıklanmaktadır. hizmet sözleşmesi ve nasıl uygulanan ve açıklama ağacına eklenen elde edilir.</span><span class="sxs-lookup"><span data-stu-id="0c862-105">This topic describes how contract-related properties are obtained from the service contract, and how they are implemented and added to the description tree.</span></span> <span data-ttu-id="0c862-106">Bazı durumlarda, öznitelik değerleri davranış özelliklerine dönüştürülür ve davranışı ardından açıklama ağacına eklenir.</span><span class="sxs-lookup"><span data-stu-id="0c862-106">In some cases, attribute values are converted into behavior properties and behavior is then inserted into the description tree.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0c862-107">Açıklama ağaç değerler meta verileri dönüştürülür bkz [ServiceDescription ve WSDL başvurusu](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).</span><span class="sxs-lookup"><span data-stu-id="0c862-107"> how the description tree values are converted into metadata, see [ServiceDescription and WSDL Reference](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).</span></span>  
  
## <a name="mapping-operations-to-the-description-tree"></a><span data-ttu-id="0c862-108">Açıklama ağacına işlemleri eşleme</span><span class="sxs-lookup"><span data-stu-id="0c862-108">Mapping Operations to the Description Tree</span></span>  
 <span data-ttu-id="0c862-109">İçinde [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uygulamalar, hizmet sözleşmelerini Modellenen arabirimlerine (veya sınıflar), öznitelikler arabirimi veya sınıf ve yöntemlerinden işlemleri gruplandırması olarak işaretlemek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="0c862-109">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications, service contracts are modeled by interfaces (or classes) that use attributes to mark the interface or class and its methods as a grouping of operations.</span></span> <span data-ttu-id="0c862-110">Zaman bir <xref:System.ServiceModel.ServiceHost> sınıfı açıldığında, hizmet sözleşmeleri ve uygulamaları üzerinden yansıtılır ve yapılandırma bilgilerini bir açıklama ağacında birleştirilen.</span><span class="sxs-lookup"><span data-stu-id="0c862-110">When a <xref:System.ServiceModel.ServiceHost> class is opened, any service contracts and implementations are reflected over and merged with configuration information into a description tree.</span></span>  
  
 <span data-ttu-id="0c862-111">İşlem modelleri iki tür vardır: *parametresi* modeli ve *ileti sözleşmesi* modeli.</span><span class="sxs-lookup"><span data-stu-id="0c862-111">There are two types of operation models: the *parameter* model and the *message contract* model.</span></span> <span data-ttu-id="0c862-112">Bir parametre veya tarafından işaretlenen dönüş değeri türü olmayan yönetilen yöntemleri parametresi modelini kullanan <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="0c862-112">The parameter model uses managed methods that do not have a parameter or return value type that is marked by the <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="0c862-113">Bu model, geliştiriciler, parametreleri serileştirmek denetlemek ve dönüş değerleri, ancak [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmeti ve sözleşmesi için açıklama ağacı doldurmak için kullanılan değerleri oluşturur.</span><span class="sxs-lookup"><span data-stu-id="0c862-113">In this model, developers control the serialization of parameters and return values, but [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the values that are used to populate the description tree for the service and its contract.</span></span>  
  
 <span data-ttu-id="0c862-114">Yapılandırma dosyalarında belirtilen bağlamaları yüklenirler doğrudan <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A?displayProperty=nameWithType> özelliği.</span><span class="sxs-lookup"><span data-stu-id="0c862-114">Bindings specified in configuration files are loaded directly into the <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A?displayProperty=nameWithType> property.</span></span>  
  
|<span data-ttu-id="0c862-115">ServiceBehaviorAttribute özelliği</span><span class="sxs-lookup"><span data-stu-id="0c862-115">ServiceBehaviorAttribute Property</span></span>|<span data-ttu-id="0c862-116">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-116">Description Tree Value Affected</span></span>|  
|---------------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-117">Ad</span><span class="sxs-lookup"><span data-stu-id="0c862-117">Name</span></span>|<xref:System.ServiceModel.Description.ServiceDescription.Name%2A>|  
|<span data-ttu-id="0c862-118">Ad Alanı</span><span class="sxs-lookup"><span data-stu-id="0c862-118">Namespace</span></span>|<xref:System.ServiceModel.Description.ServiceDescription.Namespace%2A>|  
|<span data-ttu-id="0c862-119">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="0c862-119">ConfigurationName</span></span>|<xref:System.ServiceModel.Description.ServiceDescription.ConfigurationName%2A>|  
|<span data-ttu-id="0c862-120">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="0c862-120">IgnoreExtensionDataObject</span></span>|<span data-ttu-id="0c862-121">Ayarlar <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.IgnoreExtensionDataObject%2A> özelliği tüm işlemler için.</span><span class="sxs-lookup"><span data-stu-id="0c862-121">Sets the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.IgnoreExtensionDataObject%2A> property for all operations.</span></span>|  
|<span data-ttu-id="0c862-122">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="0c862-122">MaxItemsInObjectGraph</span></span>|<span data-ttu-id="0c862-123">Ayarlar <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> özelliği tüm işlemler için.</span><span class="sxs-lookup"><span data-stu-id="0c862-123">Sets the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> property for all operations.</span></span>|  
  
|<span data-ttu-id="0c862-124">ServiceContractAttribute özelliği</span><span class="sxs-lookup"><span data-stu-id="0c862-124">ServiceContractAttribute Property</span></span>|<span data-ttu-id="0c862-125">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-125">Description Tree Value Affected</span></span>|  
|---------------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-126">CallbackContract</span><span class="sxs-lookup"><span data-stu-id="0c862-126">CallbackContract</span></span>|<span data-ttu-id="0c862-127"><xref:System.ServiceModel.Description.ContractDescription.CallbackContractType%2A>, <xref:System.ServiceModel.Description.MessageDescription> tüm işlemler için eklenen <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c862-127"><xref:System.ServiceModel.Description.ContractDescription.CallbackContractType%2A>, <xref:System.ServiceModel.Description.MessageDescription> added to all operations <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>.</span></span>|  
|<span data-ttu-id="0c862-128">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="0c862-128">ConfigurationName</span></span>|<xref:System.ServiceModel.Description.ContractDescription.ConfigurationName%2A>|  
|<span data-ttu-id="0c862-129">ProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="0c862-129">ProtectionLevel</span></span>|<span data-ttu-id="0c862-130"><xref:System.ServiceModel.Description.ContractDescription.ProtectionLevel%2A>ve büyük olasılıkla alt koruma düzeyleri.</span><span class="sxs-lookup"><span data-stu-id="0c862-130"><xref:System.ServiceModel.Description.ContractDescription.ProtectionLevel%2A> and possibly child protection levels.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0c862-131">koruma düzeyi hiyerarşi bkz [anlama koruma düzeyi](../../../../docs/framework/wcf/understanding-protection-level.md).</span><span class="sxs-lookup"><span data-stu-id="0c862-131"> the protection-level hierarchy, see [Understanding Protection Level](../../../../docs/framework/wcf/understanding-protection-level.md).</span></span>|  
|<span data-ttu-id="0c862-132">SessionMode</span><span class="sxs-lookup"><span data-stu-id="0c862-132">SessionMode</span></span>|<xref:System.ServiceModel.Description.ContractDescription.SessionMode%2A>|  
  
|<span data-ttu-id="0c862-133">ServiceKnownTypesAttribute değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-133">ServiceKnownTypesAttribute Value</span></span>|<span data-ttu-id="0c862-134">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-134">Description Tree Value Affected</span></span>|  
|--------------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-135">MethodName</span><span class="sxs-lookup"><span data-stu-id="0c862-135">MethodName</span></span>|<xref:System.ServiceModel.Description.OperationDescription.KnownTypes%2A>|  
  
|<span data-ttu-id="0c862-136">OperationContractAttribute değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-136">OperationContractAttribute Value</span></span>|<span data-ttu-id="0c862-137">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-137">Description Tree Value Affected</span></span>|  
|--------------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-138">Eylem</span><span class="sxs-lookup"><span data-stu-id="0c862-138">Action</span></span>|<span data-ttu-id="0c862-139"><xref:System.ServiceModel.Description.MessageDescription.Action%2A>çıktı iletisi veya sözleşme/geri çağırma sözleşme bağlı olarak giriş iletisi için.</span><span class="sxs-lookup"><span data-stu-id="0c862-139"><xref:System.ServiceModel.Description.MessageDescription.Action%2A> for the output message or input message, depending upon contract/callback contract.</span></span>|  
|<span data-ttu-id="0c862-140">Başlatıcıda</span><span class="sxs-lookup"><span data-stu-id="0c862-140">AsyncPattern</span></span>|<span data-ttu-id="0c862-141">TRUE ise, <xref:System.ServiceModel.Description.OperationDescription.BeginMethod%2A> ve<xref:System.ServiceModel.Description.OperationDescription.EndMethod%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-141">If true, <xref:System.ServiceModel.Description.OperationDescription.BeginMethod%2A> and <xref:System.ServiceModel.Description.OperationDescription.EndMethod%2A></span></span>|  
|<span data-ttu-id="0c862-142">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="0c862-142">IsOneWay</span></span>|<span data-ttu-id="0c862-143">Tek bir eşlenir <xref:System.ServiceModel.Description.MessageDescription> içinde<xref:System.ServiceModel.Description.OperationDescription.Messages%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-143">Maps to a single <xref:System.ServiceModel.Description.MessageDescription> in <xref:System.ServiceModel.Description.OperationDescription.Messages%2A></span></span>|  
|<span data-ttu-id="0c862-144">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="0c862-144">IsInitiating</span></span>|<xref:System.ServiceModel.Description.OperationDescription.IsInitiating%2A>|  
|<span data-ttu-id="0c862-145">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="0c862-145">IsTerminating</span></span>|<xref:System.ServiceModel.Description.OperationDescription.IsTerminating%2A>|  
|<span data-ttu-id="0c862-146">Ad</span><span class="sxs-lookup"><span data-stu-id="0c862-146">Name</span></span>|<xref:System.ServiceModel.Description.OperationDescription.Name%2A>|  
|<span data-ttu-id="0c862-147">ProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="0c862-147">ProtectionLevel</span></span>|<span data-ttu-id="0c862-148"><xref:System.ServiceModel.Description.OperationDescription.ProtectionLevel%2A>ve büyük olasılıkla alt koruma düzeyleri.</span><span class="sxs-lookup"><span data-stu-id="0c862-148"><xref:System.ServiceModel.Description.OperationDescription.ProtectionLevel%2A> and possibly child protection levels.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0c862-149">koruma düzeyi hiyerarşi bkz [anlama koruma düzeyi](../../../../docs/framework/wcf/understanding-protection-level.md).</span><span class="sxs-lookup"><span data-stu-id="0c862-149"> the protection-level hierarchy, see [Understanding Protection Level](../../../../docs/framework/wcf/understanding-protection-level.md).</span></span>|  
|<span data-ttu-id="0c862-150">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="0c862-150">ReplyAction</span></span>|<span data-ttu-id="0c862-151"><xref:System.ServiceModel.Description.MessageDescription.Action%2A>çıktı iletisi veya sözleşme/geri çağırma sözleşme bağlı olarak giriş iletisi için.</span><span class="sxs-lookup"><span data-stu-id="0c862-151"><xref:System.ServiceModel.Description.MessageDescription.Action%2A> for the output message or input message, depending upon contract/callback contract.</span></span>|  
  
|<span data-ttu-id="0c862-152">FaultContractAttribute değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-152">FaultContractAttribute Value</span></span>|<span data-ttu-id="0c862-153">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-153">Description Tree Value Affected</span></span>|  
|----------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-154">Eylem</span><span class="sxs-lookup"><span data-stu-id="0c862-154">Action</span></span>|<span data-ttu-id="0c862-155"><xref:System.ServiceModel.Description.FaultDescription.Action%2A>Sözleşme/geri çağırma sözleşme bağlı olarak.</span><span class="sxs-lookup"><span data-stu-id="0c862-155"><xref:System.ServiceModel.Description.FaultDescription.Action%2A> depending upon contract/callback contract.</span></span>|  
|<span data-ttu-id="0c862-156">DetailType</span><span class="sxs-lookup"><span data-stu-id="0c862-156">DetailType</span></span>|<xref:System.ServiceModel.Description.FaultDescription.DetailType%2A>|  
|<span data-ttu-id="0c862-157">Ad</span><span class="sxs-lookup"><span data-stu-id="0c862-157">Name</span></span>|<xref:System.ServiceModel.Description.FaultDescription.Name%2A>|  
|<span data-ttu-id="0c862-158">Ad Alanı</span><span class="sxs-lookup"><span data-stu-id="0c862-158">Namespace</span></span>|<xref:System.ServiceModel.Description.FaultDescription.Namespace%2A>|  
|<span data-ttu-id="0c862-159">ProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="0c862-159">ProtectionLevel</span></span>|<xref:System.ServiceModel.Description.FaultDescription.ProtectionLevel%2A>|  
  
|<span data-ttu-id="0c862-160">DataContractFormatAttribute değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-160">DataContractFormatAttribute Value</span></span>|<span data-ttu-id="0c862-161">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-161">Description Tree Value Affected</span></span>|  
|---------------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-162">Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında</span><span class="sxs-lookup"><span data-stu-id="0c862-162">Use</span></span>|<span data-ttu-id="0c862-163"><xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> Değeri ayarı <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> işlemi için.</span><span class="sxs-lookup"><span data-stu-id="0c862-163">The <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> value is set on the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> for the operation.</span></span>|  
  
|<span data-ttu-id="0c862-164">XmlSerializerFormatAttribute değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-164">XmlSerializerFormatAttribute Value</span></span>|<span data-ttu-id="0c862-165">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-165">Description Tree Value Affected</span></span>|  
|----------------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-166">Stil</span><span class="sxs-lookup"><span data-stu-id="0c862-166">Style</span></span>|<span data-ttu-id="0c862-167">Bu <xref:System.ServiceModel.XmlSerializerFormatAttribute> özelliği ayarlanmış <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> işlemi için.</span><span class="sxs-lookup"><span data-stu-id="0c862-167">This <xref:System.ServiceModel.XmlSerializerFormatAttribute> property is set on the <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> for the operation.</span></span>|  
|<span data-ttu-id="0c862-168">Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında</span><span class="sxs-lookup"><span data-stu-id="0c862-168">Use</span></span>|<span data-ttu-id="0c862-169"><xref:System.ServiceModel.XmlSerializerFormatAttribute> Ayarlanan <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> işlemi için.</span><span class="sxs-lookup"><span data-stu-id="0c862-169">The <xref:System.ServiceModel.XmlSerializerFormatAttribute> is set on the <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> for the operation.</span></span>|  
  
|<span data-ttu-id="0c862-170">TransactionFlowAttribute değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-170">TransactionFlowAttribute Value</span></span>|<span data-ttu-id="0c862-171">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-171">Description Tree Value Affected</span></span>|  
|------------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-172">TransactionFlowOption</span><span class="sxs-lookup"><span data-stu-id="0c862-172">TransactionFlowOption</span></span>|<span data-ttu-id="0c862-173"><xref:System.ServiceModel.TransactionFlowAttribute> Bir işlemi davranışı eklenen <xref:System.ServiceModel.Description.OperationDescription.Behaviors%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="0c862-173">The <xref:System.ServiceModel.TransactionFlowAttribute> is added as an operation behavior to the <xref:System.ServiceModel.Description.OperationDescription.Behaviors%2A> property.</span></span>|  
  
|<span data-ttu-id="0c862-174">MessageContractAttribute değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-174">MessageContractAttribute Value</span></span>|<span data-ttu-id="0c862-175">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-175">Description Tree Value Affected</span></span>|  
|------------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-176">ProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="0c862-176">ProtectionLevel</span></span>|<xref:System.ServiceModel.Description.MessageDescription.ProtectionLevel%2A>|  
|<span data-ttu-id="0c862-177">WrapperName</span><span class="sxs-lookup"><span data-stu-id="0c862-177">WrapperName</span></span>|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperName%2A>|  
|<span data-ttu-id="0c862-178">WrapperNamespace</span><span class="sxs-lookup"><span data-stu-id="0c862-178">WrapperNamespace</span></span>|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperNamespace%2A>|  
  
|<span data-ttu-id="0c862-179">MessageHeaderAttribute değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-179">MessageHeaderAttribute Value</span></span>|<span data-ttu-id="0c862-180">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-180">Description Tree Value Affected</span></span>|  
|----------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-181">Aktör</span><span class="sxs-lookup"><span data-stu-id="0c862-181">Actor</span></span>|<span data-ttu-id="0c862-182"><xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>karşılık gelen üst bilgi için<xref:System.ServiceModel.Description.MessageDescription.Headers%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-182"><xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A> for the corresponding header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A></span></span>|  
|<span data-ttu-id="0c862-183">MustUnderstand</span><span class="sxs-lookup"><span data-stu-id="0c862-183">MustUnderstand</span></span>|<span data-ttu-id="0c862-184"><xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>karşılık gelen üst bilgi için<xref:System.ServiceModel.Description.MessageDescription.Headers%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-184"><xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A> for the corresponding header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A></span></span>|  
|<span data-ttu-id="0c862-185">Ad</span><span class="sxs-lookup"><span data-stu-id="0c862-185">Name</span></span>|<span data-ttu-id="0c862-186"><xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>karşılık gelen üst bilgi için<xref:System.ServiceModel.Description.MessageDescription.Headers%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-186"><xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> for the corresponding header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A></span></span>|  
|<span data-ttu-id="0c862-187">Ad Alanı</span><span class="sxs-lookup"><span data-stu-id="0c862-187">Namespace</span></span>|<span data-ttu-id="0c862-188"><xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>karşılık gelen üst bilgi için<xref:System.ServiceModel.Description.MessageDescription.Headers%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-188"><xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> for the corresponding header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A></span></span>|  
|<span data-ttu-id="0c862-189">ProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="0c862-189">ProtectionLevel</span></span>|<span data-ttu-id="0c862-190"><xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>karşılık gelen üst bilgi için<xref:System.ServiceModel.Description.MessageDescription.Headers%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-190"><xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> for the corresponding header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A></span></span>|  
|<span data-ttu-id="0c862-191">Geçiş</span><span class="sxs-lookup"><span data-stu-id="0c862-191">Relay</span></span>|<span data-ttu-id="0c862-192"><xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>karşılık gelen üst bilgi için<xref:System.ServiceModel.Description.MessageDescription.Headers%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-192"><xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A> for the corresponding header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A></span></span>|  
  
|<span data-ttu-id="0c862-193">MessageBodyMemberAttribute değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-193">MessageBodyMemberAttribute Value</span></span>|<span data-ttu-id="0c862-194">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-194">Description Tree Value Affected</span></span>|  
|--------------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-195">Ad</span><span class="sxs-lookup"><span data-stu-id="0c862-195">Name</span></span>|<span data-ttu-id="0c862-196"><xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>karşılık gelen bir parçası<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-196"><xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> for the corresponding part in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A></span></span>|  
|<span data-ttu-id="0c862-197">Ad Alanı</span><span class="sxs-lookup"><span data-stu-id="0c862-197">Namespace</span></span>|<span data-ttu-id="0c862-198"><xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>karşılık gelen bir parçası<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-198"><xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> for the corresponding part in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A></span></span>|  
|<span data-ttu-id="0c862-199">Sırası</span><span class="sxs-lookup"><span data-stu-id="0c862-199">Order</span></span>|<span data-ttu-id="0c862-200"><xref:System.ServiceModel.Description.MessagePartDescription.Index%2A>karşılık gelen bir parçası<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-200"><xref:System.ServiceModel.Description.MessagePartDescription.Index%2A> for the corresponding part in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A></span></span>|  
|<span data-ttu-id="0c862-201">ProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="0c862-201">ProtectionLevel</span></span>|<span data-ttu-id="0c862-202"><xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>karşılık gelen bir parçası<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-202"><xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> for the corresponding part in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A></span></span>|  
  
|<span data-ttu-id="0c862-203">MessageHeaderArrayAttribute değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-203">MessageHeaderArrayAttribute Value</span></span>|<span data-ttu-id="0c862-204">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-204">Description Tree Value Affected</span></span>|  
|---------------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-205">Aktör</span><span class="sxs-lookup"><span data-stu-id="0c862-205">Actor</span></span>|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>|  
|<span data-ttu-id="0c862-206">MustUnderstand</span><span class="sxs-lookup"><span data-stu-id="0c862-206">MustUnderstand</span></span>|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>|  
|<span data-ttu-id="0c862-207">Ad</span><span class="sxs-lookup"><span data-stu-id="0c862-207">Name</span></span>|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
|<span data-ttu-id="0c862-208">Ad Alanı</span><span class="sxs-lookup"><span data-stu-id="0c862-208">Namespace</span></span>|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>|  
|<span data-ttu-id="0c862-209">ProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="0c862-209">ProtectionLevel</span></span>|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>|  
|<span data-ttu-id="0c862-210">Geçiş</span><span class="sxs-lookup"><span data-stu-id="0c862-210">Relay</span></span>|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>|  
  
|<span data-ttu-id="0c862-211">MessagePropertyAttribute değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-211">MessagePropertyAttribute Value</span></span>|<span data-ttu-id="0c862-212">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-212">Description Tree Value Affected</span></span>|  
|------------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-213">Ad</span><span class="sxs-lookup"><span data-stu-id="0c862-213">Name</span></span>|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
  
|<span data-ttu-id="0c862-214">MessageParameterAttribute değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-214">MessageParameterAttribute Value</span></span>|<span data-ttu-id="0c862-215">Etkilenen açıklama ağaç değeri</span><span class="sxs-lookup"><span data-stu-id="0c862-215">Description Tree Value Affected</span></span>|  
|-------------------------------------|-------------------------------------|  
|<span data-ttu-id="0c862-216">Ad</span><span class="sxs-lookup"><span data-stu-id="0c862-216">Name</span></span>|<span data-ttu-id="0c862-217"><xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>karşılık gelen bir parçası<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A></span><span class="sxs-lookup"><span data-stu-id="0c862-217"><xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> for the corresponding part in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A></span></span>|  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0c862-218">Açıklama ağaç değerler meta verileri dönüştürülür bkz [ServiceDescription ve WSDL başvurusu](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).</span><span class="sxs-lookup"><span data-stu-id="0c862-218"> how the description tree values are converted into metadata, see [ServiceDescription and WSDL Reference](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c862-219">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0c862-219">See Also</span></span>  
 [<span data-ttu-id="0c862-220">ServiceDescription ve WSDL başvurusu</span><span class="sxs-lookup"><span data-stu-id="0c862-220">ServiceDescription and WSDL Reference</span></span>](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md)