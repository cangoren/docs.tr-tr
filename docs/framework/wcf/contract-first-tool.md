---
title: "Önce Anlaşma Aracı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a880690-f460-4475-a5f4-9f91ce08fcc6
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ea0821d9dd6073c1e652d36c71b817647b8710c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="contract-first-tool"></a><span data-ttu-id="33390-102">Önce Anlaşma Aracı</span><span class="sxs-lookup"><span data-stu-id="33390-102">Contract-First Tool</span></span>
<span data-ttu-id="33390-103">Hizmet sözleşmeleri genellikle varolan Hizmetleri'nden oluşturulması gerekir.</span><span class="sxs-lookup"><span data-stu-id="33390-103">Service contracts often need to be created from existing services.</span></span> <span data-ttu-id="33390-104">İçinde [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], veri sözleşmesi sınıfları oluşturulabilir otomatik olarak önce anlaşma aracı kullanarak mevcut Hizmetleri'nden.</span><span class="sxs-lookup"><span data-stu-id="33390-104">In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], data contract classes can be created automatically from existing services using the contract-first tool.</span></span> <span data-ttu-id="33390-105">Önce anlaşma aracı kullanmak için XML şeması tanım dosyası (XSD) yerel olarak yüklenmelidir; Aracı, HTTP üzerinden uzak veri sözleşmeleri içeri aktarılamıyor.</span><span class="sxs-lookup"><span data-stu-id="33390-105">To use the contract-first tool, the XML schema definition file (XSD) must be downloaded locally; the tool cannot import remote data contracts via HTTP.</span></span>  
  
 <span data-ttu-id="33390-106">Önce anlaşma aracı tümleştirilmiş [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] derleme görevi olarak.</span><span class="sxs-lookup"><span data-stu-id="33390-106">The contract-first tool is integrated into [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] as a build task.</span></span> <span data-ttu-id="33390-107">Böylece proje kolayca temel alınan hizmet sözleşmesini değişiklikleri benimseyebilirsiniz derleme görevi tarafından oluşturulan kod dosyaları proje yerleşik olarak bulunan her zaman oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="33390-107">The code files generated by the build task are created every time the project is built, so that the project can easily adopt changes in the underlying service contract.</span></span>  
  
 <span data-ttu-id="33390-108">Önce anlaşma aracı alabilir şema türleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="33390-108">Schema types that the contract-first tool can import include the following:</span></span>  
  
```xml  
<xsd:complexType>  
<xsd:simpleType>  
```  
  
 <span data-ttu-id="33390-109">Basit türler, değil temelleri gibi olmaları durumunda oluşturulmayacak `Int16` veya `String`; karmaşık türleri, değil türünde iseler oluşturulmayacak `Collection`.</span><span class="sxs-lookup"><span data-stu-id="33390-109">Simple types will not be generated if they are primitives such as `Int16` or `String`; complex types will not be generated if they are of type `Collection`.</span></span> <span data-ttu-id="33390-110">Türleri de olmayan oluşturulmayacak başka bir parçası ise `xsd:complexType`.</span><span class="sxs-lookup"><span data-stu-id="33390-110">Types will also not be generated if they are part of another `xsd:complexType`.</span></span> <span data-ttu-id="33390-111">Bu durumlarda, türleri projedeki mevcut türleri için bunun yerine başvurulacak.</span><span class="sxs-lookup"><span data-stu-id="33390-111">In all these cases, the types will be referenced to existing types in the project instead.</span></span>  
  
## <a name="adding-a-data-contract-to-a-project"></a><span data-ttu-id="33390-112">Projeye bir veri sözleşmesi ekleme</span><span class="sxs-lookup"><span data-stu-id="33390-112">Adding a data contract to a project</span></span>  
 <span data-ttu-id="33390-113">Önce anlaşma Aracı'nı kullanmadan önce hizmet sözleşmesi (XSD) projeye eklenmelidir.</span><span class="sxs-lookup"><span data-stu-id="33390-113">Before the contract-first tool can be used, the service contract (XSD) must be added to the project.</span></span> <span data-ttu-id="33390-114">Bu genel bakışta amaçları doğrultusunda, aşağıdaki Sözleşme Sözleşme ilk işlevleri göstermek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="33390-114">For the purposes of this overview, the following contract will be used to illustrate contract-first functions.</span></span> <span data-ttu-id="33390-115">Bu hizmet tanımı Bing'ın arama API tarafından kullanılan hizmet sözleşmesini küçük bir alt kümesidir.</span><span class="sxs-lookup"><span data-stu-id="33390-115">This service definition is a small subset of the service contract used by Bing’s search API.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="ServiceSchema"  
    targetNamespace="http://tempuri.org/ServiceSchema.xsd"  
    elementFormDefault="qualified"  
    xmlns="http://tempuri.org/ServiceSchema.xsd"  
    xmlns:mstns="http://tempuri.org/ServiceSchema.xsd"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema"  
>  
  <xs:complexType name="SearchRequest">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="1" name="Version" type="xs:string" default="2.2" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Market" type="xs:string" />  
      <xs:element minOccurs="0" maxOccurs="1" name="UILanguage" type="xs:string" />  
      <xs:element minOccurs="1" maxOccurs="1" name="Query" type="xs:string" />  
      <xs:element minOccurs="1" maxOccurs="1" name="AppId" type="xs:string" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Latitude" type="xs:double" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Longitude" type="xs:double" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Radius" type="xs:double" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:simpleType name="WebSearchOption">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="DisableHostCollapsing" />  
      <xs:enumeration value="DisableQueryAlterations" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
 <span data-ttu-id="33390-116">Yukarıdaki hizmet sözleşmesini projeye eklemek için projesine sağ tıklatın ve **yeni Ekle...** .</span><span class="sxs-lookup"><span data-stu-id="33390-116">To add the above service contract to the project, right-click the project and select **Add New…**.</span></span> <span data-ttu-id="33390-117">Şema tanımı Şablonları iletişim WCF bölmesinden seçin ve SampleContract.xsd yeni dosya adı.</span><span class="sxs-lookup"><span data-stu-id="33390-117">Select Schema Definition from the WCF pane of the Templates dialog, and name the new file SampleContract.xsd.</span></span> <span data-ttu-id="33390-118">Yukarıdaki kodu kopyalayıp yeni dosya kodu görünüme yapıştırın.</span><span class="sxs-lookup"><span data-stu-id="33390-118">Copy and paste the above code into the code view of the new file.</span></span>  
  
## <a name="configuring-contract-first-options"></a><span data-ttu-id="33390-119">Önce anlaşma seçeneklerini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="33390-119">Configuring contract-first options</span></span>  
 <span data-ttu-id="33390-120">Önce anlaşma seçenekleri özellikler menüsünde yapılandırılabilir bir [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] projesi.</span><span class="sxs-lookup"><span data-stu-id="33390-120">Contract-first options can be configured in the Properties menu of a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] project.</span></span> <span data-ttu-id="33390-121">Önce anlaşma geliştirme etkinleştirmek için seçin **etkinleştirmek XSD türü tanım dili olarak** onay kutusunu proje penceresinin WCF sayfasındaki.</span><span class="sxs-lookup"><span data-stu-id="33390-121">To enable contract-first development, select the **Enable XSD as Type Definition Language** check box in the WCF page of the project properties window.</span></span>  
  
 <span data-ttu-id="33390-122">![WCF proje sözleşme &#45;gösteren seçenekleri; ilk](../../../docs/framework/wcf/media/contractfirstoptions.png "ContractFirstOptions")</span><span class="sxs-lookup"><span data-stu-id="33390-122">![WCF Project Options showing contract&#45;first](../../../docs/framework/wcf/media/contractfirstoptions.png "ContractFirstOptions")</span></span>  
  
 <span data-ttu-id="33390-123">Gelişmiş özelliklerini yapılandırmak için Gelişmiş düğmesini tıklatın.</span><span class="sxs-lookup"><span data-stu-id="33390-123">To configure advanced properties, click the Advanced button.</span></span>  
  
 <span data-ttu-id="33390-124">![Gelişmiş sözleşme &#45; İlk özellikleri](../../../docs/framework/wcf/media/contractfirstadvanced.png "ContractFirstAdvanced")</span><span class="sxs-lookup"><span data-stu-id="33390-124">![Advanced Contract&#45;First Properties](../../../docs/framework/wcf/media/contractfirstadvanced.png "ContractFirstAdvanced")</span></span>  
  
 <span data-ttu-id="33390-125">Gelişmiş ayarlar aşağıdaki sözleşmeleri kod oluşturma için yapılandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="33390-125">The following advanced settings can be configured for code generation from contracts.</span></span> <span data-ttu-id="33390-126">Ayarları, yalnızca tüm projedeki dosyaları için yapılandırılabilir; ayarları için tek tek dosyalar şu anda yapılandırılamaz.</span><span class="sxs-lookup"><span data-stu-id="33390-126">Settings can only be configured for all of the files in the project; settings cannot be configured for individual files at this time.</span></span>  
  
-   <span data-ttu-id="33390-127">**Seri hale getirici modu**: Bu ayarı, hangi seri hale getirici hizmet sözleşmesi dosyaları okumak için kullanılan belirler.</span><span class="sxs-lookup"><span data-stu-id="33390-127">**Serializer Mode**: This setting determines which serializer is used for reading service contract files.</span></span> <span data-ttu-id="33390-128">Zaman **XML serileştiriciyi** seçili **koleksiyon türleri** ve **yeniden türleri** seçenekleri devre dışı bırakılır.</span><span class="sxs-lookup"><span data-stu-id="33390-128">When **XML Serializer** is selected, the **Collection Types** and **Reuse Types** options are disabled.</span></span> <span data-ttu-id="33390-129">Bu seçenekler yalnızca geçerli **veri sözleşmesi seri hale getirici**.</span><span class="sxs-lookup"><span data-stu-id="33390-129">These options only apply to the **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="33390-130">**Türleri yeniden**: Bu ayar, hangi kitaplıkların türü yeniden kullanılmak üzere kullanılan belirtir.</span><span class="sxs-lookup"><span data-stu-id="33390-130">**Reuse Types**: This setting specifies which libraries are used for type reuse.</span></span> <span data-ttu-id="33390-131">Bu ayar yalnızca geçerlidir **seri hale getirici modu** ayarlanır **veri sözleşmesi seri hale getirici**.</span><span class="sxs-lookup"><span data-stu-id="33390-131">This setting only applies if **Serializer Mode** is set to **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="33390-132">**Koleksiyon türü**: Bu ayar, koleksiyon veri türü için kullanılacak tam veya bütünleştirilmiş kod tam türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="33390-132">**Collection Type**: This setting specifies the fully-qualified or assembly-qualified type to be used for the collection data type.</span></span> <span data-ttu-id="33390-133">Bu ayar yalnızca geçerlidir **seri hale getirici modu** ayarlanır **veri sözleşmesi seri hale getirici**.</span><span class="sxs-lookup"><span data-stu-id="33390-133">This setting only applies if **Serializer Mode** is set to **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="33390-134">**Sözlük türü**: Bu ayar, sözlük veri türü için kullanılacak tam veya bütünleştirilmiş kod tam türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="33390-134">**Dictionary Type**: This setting specifies the fully-qualified or assembly-qualified type to be used for the dictionary data type.</span></span>  
  
-   <span data-ttu-id="33390-135">**EnableDataBinding**: uygulamak bu ayarı belirtir <xref:System.ComponentModel.INotifyPropertyChanged> veri bağlama uygulamak için tüm veri türleri arabirimi.</span><span class="sxs-lookup"><span data-stu-id="33390-135">**EnableDataBinding**: This setting specifies whether to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface on all data types to implement data binding.</span></span>  
  
-   <span data-ttu-id="33390-136">**ExcludedTypes**: Bu ayar, başvurulan derlemelerden çıkarılacak tam veya bütünleştirilmiş kod tam türlerinin bir listesini belirtir.</span><span class="sxs-lookup"><span data-stu-id="33390-136">**ExcludedTypes**:This setting specifies the list of fully-qualified or assembly-qualified types to be excluded from the referenced assemblies.</span></span> <span data-ttu-id="33390-137">Bu ayar yalnızca geçerlidir **seri hale getirici modu** ayarlanır **veri sözleşmesi seri hale getirici**.</span><span class="sxs-lookup"><span data-stu-id="33390-137">This setting only applies if **Serializer Mode** is set to **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="33390-138">**GenerateInternalTypes**: Bu ayarı olarak iç işaretlenmiş sınıfları oluşturulup oluşturulmayacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="33390-138">**GenerateInternalTypes**: This setting specifies whether to generate classes that are marked as internal.</span></span> <span data-ttu-id="33390-139">Bu ayar yalnızca geçerlidir **seri hale getirici modu** ayarlanır **veri sözleşmesi seri hale getirici**.</span><span class="sxs-lookup"><span data-stu-id="33390-139">This setting only applies if **Serializer Mode** is set to **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="33390-140">**GenerateSerializableTypes**: Bu ayar sınıflarıyla oluşturulup oluşturulmayacağını belirtir <xref:System.SerializableAttribute> özniteliği.</span><span class="sxs-lookup"><span data-stu-id="33390-140">**GenerateSerializableTypes**: This setting specifies whether to generate classes with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="33390-141">Bu ayar yalnızca geçerlidir **seri hale getirici modu** ayarlanır **veri sözleşmesi seri hale getirici**.</span><span class="sxs-lookup"><span data-stu-id="33390-141">This setting only applies if **Serializer Mode** is set to **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="33390-142">**ImportXMLTypes**: Bu ayarı uygulamak için veri sözleşmesi seri hale getirici yapılandırılıp yapılandırılmayacağını belirtir <xref:System.SerializableAttribute> olmadan sınıflarını özniteliğini <xref:System.Runtime.Serialization.DataContractAttribute> özniteliği.</span><span class="sxs-lookup"><span data-stu-id="33390-142">**ImportXMLTypes**: This setting specifies whether to configure the data contract serializer to apply the <xref:System.SerializableAttribute> attribute to classes without the <xref:System.Runtime.Serialization.DataContractAttribute> attribute.</span></span>  <span data-ttu-id="33390-143">Bu ayar yalnızca geçerlidir **seri hale getirici modu** ayarlanır **veri sözleşmesi seri hale getirici**.</span><span class="sxs-lookup"><span data-stu-id="33390-143">This setting only applies if **Serializer Mode** is set to **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="33390-144">**SupportFx35TypedDataSets**: Bu ayar için .net oluşturulan yazılan veri kümeleri için ek işlevler sağlamasına belirtir Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="33390-144">**SupportFx35TypedDataSets**: This setting specifies whether to provide additional functionality for typed data sets created for .Net Framework 3.5.</span></span> <span data-ttu-id="33390-145">Zaman **seri hale getirici modu** ayarlanır **XML serileştiriciyi**, <xref:System.Data.Design.TypedDataSetSchemaImporterExtensionFx35> uzantı bu değeri True olarak ayarlandığında için XML Şeması içeri Aktarıcı eklenir.</span><span class="sxs-lookup"><span data-stu-id="33390-145">When  **Serializer Mode** is set to **XML Serializer**, the <xref:System.Data.Design.TypedDataSetSchemaImporterExtensionFx35> extension will be added to the XML schema importer when this value is set to True.</span></span> <span data-ttu-id="33390-146">Zaman **seri hale getirici modu** ayarlanır **veri sözleşmesi seri hale getirici**, türü <xref:System.DateTimeOffset> bu değeri False olarak ayarlandığında başvurularından dışlanıp böylece bir <xref:System.DateTimeOffset> her zaman oluşturulur eski framework sürümleri için.</span><span class="sxs-lookup"><span data-stu-id="33390-146">When  **Serializer Mode** is set to **Data Contract Serializer**, the type <xref:System.DateTimeOffset> will be excluded from the References when this value is set to False, so that a <xref:System.DateTimeOffset> is always generated for older framework versions.</span></span>  
  
-   <span data-ttu-id="33390-147">**InputXsdFiles**: Bu ayar giriş dosyaların listesini belirtir.</span><span class="sxs-lookup"><span data-stu-id="33390-147">**InputXsdFiles**: This setting specifies the list of input files.</span></span> <span data-ttu-id="33390-148">Her bir dosyanın geçerli bir XML Şeması içermesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="33390-148">Each file must contain a valid XML schema.</span></span>  
  
-   <span data-ttu-id="33390-149">**Dil**: Bu ayar, oluşturulan sözleşme kod dilini belirtir.</span><span class="sxs-lookup"><span data-stu-id="33390-149">**Language**: This setting specifies the language of the generated contract code.</span></span> <span data-ttu-id="33390-150">Bu ayar tarafından tanınan olmalıdır <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="33390-150">The setting must be recognizable by <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>  
  
-   <span data-ttu-id="33390-151">**NamespaceMappings**: XSD hedef ad eşlemelerini CLR ad alanları için bu ayarı belirtir.</span><span class="sxs-lookup"><span data-stu-id="33390-151">**NamespaceMappings**: This setting specifies the mappings from the XSD Target Namespaces to CLR namespaces.</span></span> <span data-ttu-id="33390-152">Her eşleme aşağıdaki biçimi kullanmalıdır:</span><span class="sxs-lookup"><span data-stu-id="33390-152">Each mapping should use the following format:</span></span>  
  
    ```xml  
    "<Schema Namespace>, <CLR Namespace>"  
    ```  
  
     <span data-ttu-id="33390-153">XML serileştiriciyi yalnızca şu biçimdeki bir eşleme kabul eder:</span><span class="sxs-lookup"><span data-stu-id="33390-153">The XML Serializer only accepts one mapping in the following format:</span></span>  
  
    ```xml  
    "*, <CLR Namespace>"  
    ```  
  
-   <span data-ttu-id="33390-154">**Çıktıdizini**: Bu ayar, kod dosyaları oluşturulmayacak dizini belirtir.</span><span class="sxs-lookup"><span data-stu-id="33390-154">**OutputDirectory**: This setting specifies the directory where the code files will be generated.</span></span>  
  
 <span data-ttu-id="33390-155">Ayarları, proje yapılandırıldığında hizmet sözleşmesi dosyalarından hizmet sözleşme türleri oluşturmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="33390-155">The settings will be used to generate service contract types from the service contract files when the project is built.</span></span>  
  
## <a name="using-contract-first-development"></a><span data-ttu-id="33390-156">Önce anlaşma geliştirme kullanma</span><span class="sxs-lookup"><span data-stu-id="33390-156">Using contract-first development</span></span>  
 <span data-ttu-id="33390-157">Hizmet sözleşmesi projeye ekleme ve yapılandırma ayarlarını onaylama yapı sonra projeyi tuşlarına basarak **F6**.</span><span class="sxs-lookup"><span data-stu-id="33390-157">After adding the service contract to the project and confirming the build settings, build the project by pressing **F6**.</span></span> <span data-ttu-id="33390-158">Hizmet sözleşmesinde tanımlanan türler sonra projede kullanılmak üzere kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="33390-158">The types defined in the service contract will then be available for use in the project.</span></span>  
  
 <span data-ttu-id="33390-159">Hizmet sözleşmesinde tanımlanan türlerden birisini kullanmak için bir başvuru ekleyin `ContractTypes` geçerli ad alanı altında:</span><span class="sxs-lookup"><span data-stu-id="33390-159">To use the types defined in the service contract, add a reference to `ContractTypes` under the current namespace:</span></span>  
  
```csharp  
using MyProjectNamespace.ContractTypes;  
```  
  
 <span data-ttu-id="33390-160">Hizmet sözleşmesinde tanımlanan türler sonra aşağıda gösterildiği gibi projede çözümlenebilir olacaktır.</span><span class="sxs-lookup"><span data-stu-id="33390-160">The types defined in the service contract will then be resolvable in the project, as shown below.</span></span>  
  
 <span data-ttu-id="33390-161">![Bir hizmet sözleşmesi türetilmiş türler kullanarak](../../../docs/framework/wcf/media/contractfirsttypes.png "ContractFirstTypes")</span><span class="sxs-lookup"><span data-stu-id="33390-161">![Using types derived from a service contract](../../../docs/framework/wcf/media/contractfirsttypes.png "ContractFirstTypes")</span></span>  
  
 <span data-ttu-id="33390-162">Aracı tarafından oluşturulan türleri GeneratedXSDTypes.cs dosyasında oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="33390-162">The types generated by the tool are created in the GeneratedXSDTypes.cs file.</span></span> <span data-ttu-id="33390-163">Dosya oluşturulur \<proje dizini > /obj/\<yapı yapılandırması > Varsayılan olarak /XSDGeneratedCode/ dizin.</span><span class="sxs-lookup"><span data-stu-id="33390-163">The file is created in the \<project directory>/obj/\<build configuration>/XSDGeneratedCode/ directory by default.</span></span> <span data-ttu-id="33390-164">Bu konunun başındaki örnek şema gibi dönüştürülür:</span><span class="sxs-lookup"><span data-stu-id="33390-164">The sample schema at the beginning of this topic is converted as follows:</span></span>  
  
```csharp
//------------------------------------------------------------------------------  
// <auto-generated>  
//     This code was generated by a tool.  
//     Runtime Version:4.0.30319.17330  
//  
//     Changes to this file may cause incorrect behavior and will be lost if  
//     the code is regenerated.  
// </auto-generated>  
//------------------------------------------------------------------------------  
  
namespace TestXSD3.ContractTypes  
{  
    using System.Xml.Serialization;  
  
    /// <remarks/>  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]  
    [System.SerializableAttribute()]  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.ComponentModel.DesignerCategoryAttribute("code")]  
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]  
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=true)]  
    public partial class SearchRequest  
    {  
  
        private string versionField;  
  
        private string marketField;  
  
        private string uILanguageField;  
  
        private string queryField;  
  
        private string appIdField;  
  
        private double latitudeField;  
  
        private bool latitudeFieldSpecified;  
  
        private double longitudeField;  
  
        private bool longitudeFieldSpecified;  
  
        private double radiusField;  
  
        private bool radiusFieldSpecified;  
  
        public SearchRequest()  
        {  
            this.versionField = "2.2";  
        }  
  
        /// <remarks/>  
        [System.ComponentModel.DefaultValueAttribute("2.2")]  
        public string Version  
        {  
            get  
            {  
                return this.versionField;  
            }  
            set  
            {  
                this.versionField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string Market  
        {  
            get  
            {  
                return this.marketField;  
            }  
            set  
            {  
                this.marketField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string UILanguage  
        {  
            get  
            {  
                return this.uILanguageField;  
            }  
            set  
            {  
                this.uILanguageField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string Query  
        {  
            get  
            {  
                return this.queryField;  
            }  
            set  
            {  
                this.queryField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string AppId  
        {  
            get  
            {  
                return this.appIdField;  
            }  
            set  
            {  
                this.appIdField = value;  
            }  
        }  
  
        /// <remarks/>  
        public double Latitude  
        {  
            get  
            {  
                return this.latitudeField;  
            }  
            set  
            {  
                this.latitudeField = value;  
            }  
        }  
  
        /// <remarks/>  
        [System.Xml.Serialization.XmlIgnoreAttribute()]  
        public bool LatitudeSpecified  
        {  
            get  
            {  
                return this.latitudeFieldSpecified;  
            }  
            set  
            {  
                this.latitudeFieldSpecified = value;  
            }  
        }  
  
        /// <remarks/>  
        public double Longitude  
        {  
            get  
            {  
                return this.longitudeField;  
            }  
            set  
            {  
                this.longitudeField = value;  
            }  
        }  
  
        /// <remarks/>  
        [System.Xml.Serialization.XmlIgnoreAttribute()]  
        public bool LongitudeSpecified  
        {  
            get  
            {  
                return this.longitudeFieldSpecified;  
            }  
            set  
            {  
                this.longitudeFieldSpecified = value;  
            }  
        }  
  
        /// <remarks/>  
        public double Radius  
        {  
            get  
            {  
                return this.radiusField;  
            }  
            set  
            {  
                this.radiusField = value;  
            }  
        }  
  
        /// <remarks/>  
        [System.Xml.Serialization.XmlIgnoreAttribute()]  
        public bool RadiusSpecified  
        {  
            get  
            {  
                return this.radiusFieldSpecified;  
            }  
            set  
            {  
                this.radiusFieldSpecified = value;  
            }  
        }  
    }  
  
    /// <remarks/>  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]  
    [System.SerializableAttribute()]  
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]  
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=false)]  
    public enum WebSearchOption  
    {  
  
        /// <remarks/>  
        DisableHostCollapsing,  
  
        /// <remarks/>  
        DisableQueryAlterations,  
    }  
}  
```  
  
## <a name="errors-and-warnings"></a><span data-ttu-id="33390-165">Hatalar ve uyarılar</span><span class="sxs-lookup"><span data-stu-id="33390-165">Errors and warnings</span></span>  
 <span data-ttu-id="33390-166">Hataları ve Uyarıları XSD şema ayrıştırma karşılaşılan hataları ve Uyarıları oluşturmak gibi görünür.</span><span class="sxs-lookup"><span data-stu-id="33390-166">Errors and warnings encountered in parsing the XSD schema will appear as build errors and warnings.</span></span>  
  
## <a name="interface-inheritance"></a><span data-ttu-id="33390-167">Arabirim devralma</span><span class="sxs-lookup"><span data-stu-id="33390-167">Interface Inheritance</span></span>  
 <span data-ttu-id="33390-168">Önce anlaşma geliştirme ile arabirimi devralma kullanmak mümkün değildir; Bu, diğer işlemlerini arabirimleri davranmasına yol tutarlıdır.</span><span class="sxs-lookup"><span data-stu-id="33390-168">It is not possible to use interface inheritance with contract-first development; this is consistent with the way interfaces behave in other operations.</span></span> <span data-ttu-id="33390-169">Temel arabirim devralan bir arabirim kullanmak için iki ayrı uç nokta kullanın.</span><span class="sxs-lookup"><span data-stu-id="33390-169">In order to use an interface that inherits a base interface, use two separate endpoints.</span></span> <span data-ttu-id="33390-170">Birinci uç nokta devralınan sözleşme kullanan ve ikinci uç nokta temel arabirimi uygular.</span><span class="sxs-lookup"><span data-stu-id="33390-170">The first endpoint uses the inherited contract, and the second endpoint implements the base interface.</span></span>