---
title: "&lt;System.codeDom&gt; öğesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8b223ab6ab742c5b7d3b3d2f5640e99835afe268
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsystemcodedomgt-element"></a><span data-ttu-id="517d5-102">&lt;System.codeDom&gt; öğesi</span><span class="sxs-lookup"><span data-stu-id="517d5-102">&lt;system.codedom&gt; Element</span></span>
<span data-ttu-id="517d5-103">Kullanılabilir dil sağlayıcıları için derleyici yapılandırma ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="517d5-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
 <span data-ttu-id="517d5-104">\<Yapılandırma > öğesi</span><span class="sxs-lookup"><span data-stu-id="517d5-104">\<configuration> Element</span></span>  
<span data-ttu-id="517d5-105">\<System.codeDom > öğesi</span><span class="sxs-lookup"><span data-stu-id="517d5-105">\<system.codedom> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="517d5-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="517d5-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="517d5-107">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="517d5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="517d5-108">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="517d5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="517d5-109">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="517d5-109">Attributes</span></span>  
 <span data-ttu-id="517d5-110">Yok.</span><span class="sxs-lookup"><span data-stu-id="517d5-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="517d5-111">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="517d5-111">Child Elements</span></span>  
  
|<span data-ttu-id="517d5-112">Öğe</span><span class="sxs-lookup"><span data-stu-id="517d5-112">Element</span></span>|<span data-ttu-id="517d5-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="517d5-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="517d5-114">\<derleyicileri ></span><span class="sxs-lookup"><span data-stu-id="517d5-114">\<compilers></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="517d5-115">Compiler configuration öğeleri için kapsayıcı; sıfır veya daha fazla bilgi içeren [ \<derleyici >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) öğeleri.</span><span class="sxs-lookup"><span data-stu-id="517d5-115">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="517d5-116">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="517d5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="517d5-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="517d5-117">Element</span></span>|<span data-ttu-id="517d5-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="517d5-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="517d5-119">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="517d5-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="517d5-120">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="517d5-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="517d5-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="517d5-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="517d5-122">.NET framework sürüm 2.0</span><span class="sxs-lookup"><span data-stu-id="517d5-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="517d5-123">[ \<System.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) öğesi .NET Framework ile gibi yüklenen varsayılan sağlayıcıları yanı sıra bir bilgisayarda yüklü olan dil sağlayıcıları için derleyici yapılandırma ayarlarını içerir <xref:Microsoft.CSharp.CSharpCodeProvider> ve <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="517d5-123">The [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="517d5-124">[ \<Derleyicileri >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) sıfır veya daha fazla öğe içeriyor [ \<derleyici >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) öğeleri.</span><span class="sxs-lookup"><span data-stu-id="517d5-124">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span> <span data-ttu-id="517d5-125">Her [ \<derleyici >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) öğesi için özgün dil sağlayıcısı compiler configuration öznitelikleri belirtir.</span><span class="sxs-lookup"><span data-stu-id="517d5-125">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="517d5-126">Geliştiriciler ve derleyici satıcılar ekleyebilirsiniz yapılandırma ayarlarını makine yapılandırma dosyası (Machine.config) yeni bir <xref:System.CodeDom.Compiler.CodeDomProvider> uygulaması.</span><span class="sxs-lookup"><span data-stu-id="517d5-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="517d5-127">Kullanım <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> varsayılan dil sağlayıcısı ve derleyici yapılandırma ayarları bir bilgisayarda tarafından tanımlanan dil sağlayıcısı program aracılığıyla listeleme yöntemi.</span><span class="sxs-lookup"><span data-stu-id="517d5-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="517d5-128">.NET Framework sürüm 1.0 ve 1.1, .NET Framework tarafından sağlanan sağlayıcıları tanımlanır varsayılan dil [ \<derleyicileri >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="517d5-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element.</span></span> <span data-ttu-id="517d5-129">.NET Framework sürüm 2. 0'da, varsayılan dil sağlayıcısı içinde tanımlanmamış [ \<derleyicileri >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) öğesi, ancak kullanarak numaralandırılan <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="517d5-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="517d5-130">.NET framework sürüm 1.0 ve 1.1</span><span class="sxs-lookup"><span data-stu-id="517d5-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="517d5-131">[ \<System.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) öğesi bir bilgisayar üzerinde dil sağlayıcıları için derleyici yapılandırma ayarlarını içerir.</span><span class="sxs-lookup"><span data-stu-id="517d5-131">The [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="517d5-132">[ \<Derleyicileri >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) sıfır veya daha fazla öğe içeriyor [ \<derleyici >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) öğeleri.</span><span class="sxs-lookup"><span data-stu-id="517d5-132">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span> <span data-ttu-id="517d5-133">Her [ \<derleyici >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) öğesi için özgün dil sağlayıcısı compiler configuration öznitelikleri belirtir.</span><span class="sxs-lookup"><span data-stu-id="517d5-133">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="517d5-134">.NET Framework makine yapılandırma dosyasındaki (Machine.config) ilk derleyici ayarları tanımlar.</span><span class="sxs-lookup"><span data-stu-id="517d5-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="517d5-135">Geliştiriciler ve derleyici satıcılar ekleyebilirsiniz yapılandırma ayarları için yeni bir <xref:System.CodeDom.Compiler.CodeDomProvider> uygulaması.</span><span class="sxs-lookup"><span data-stu-id="517d5-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="517d5-136">Kullanım <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> dil sağlayıcısı ve derleyici yapılandırma ayarları bir bilgisayarda program aracılığıyla listeleme yöntemi.</span><span class="sxs-lookup"><span data-stu-id="517d5-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="517d5-137">Yapılandırma Dosyası</span><span class="sxs-lookup"><span data-stu-id="517d5-137">Configuration File</span></span>  
 <span data-ttu-id="517d5-138">Bu öğe makine yapılandırma dosyası ve uygulama yapılandırma dosyasında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="517d5-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="517d5-139">Örnek</span><span class="sxs-lookup"><span data-stu-id="517d5-139">Example</span></span>  
 <span data-ttu-id="517d5-140">Aşağıdaki örnek tipik derleyici yapılandırma gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="517d5-140">The following example illustrates a typical compiler configuration.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="517d5-141">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="517d5-141">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="517d5-142">Yapılandırma dosyası şeması</span><span class="sxs-lookup"><span data-stu-id="517d5-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="517d5-143">Derleyici ve dil sağlayıcısı Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="517d5-143">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 [<span data-ttu-id="517d5-144">\<Derleyici > öğesi</span><span class="sxs-lookup"><span data-stu-id="517d5-144">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)