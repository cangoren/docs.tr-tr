---
title: "x:Static İşaretleme Uzantısı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
caps.latest.revision: "25"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d006c8d0937a454dcbe092dcc3e35c4644088e59
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="149de-102">x:Static İşaretleme Uzantısı</span><span class="sxs-lookup"><span data-stu-id="149de-102">x:Static Markup Extension</span></span>
<span data-ttu-id="149de-103">Tanımlanan herhangi bir statik değer tarafından kod varlığa başvuruda bulunan bir [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]– uyumlu yolu.</span><span class="sxs-lookup"><span data-stu-id="149de-103">References any static by-value code entity that is defined in a [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]–compliant way.</span></span> <span data-ttu-id="149de-104">Başvurulan statik özellik XAML'de özelliğinin değeri sağlamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="149de-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="149de-105">XAML Öznitelik Kullanımı</span><span class="sxs-lookup"><span data-stu-id="149de-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="149de-106">XAML Değerleri</span><span class="sxs-lookup"><span data-stu-id="149de-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="149de-107">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="149de-107">Optional.</span></span> <span data-ttu-id="149de-108">Eşlenen, varsayılan olmayan XAML ad alanına başvuruyor öneki.</span><span class="sxs-lookup"><span data-stu-id="149de-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="149de-109">`prefix`Varsayılan XAML ad alanından gelen statik özellikler nadiren aldığından açıkça kullanımı gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="149de-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="149de-110">Açıklamalar bakın.</span><span class="sxs-lookup"><span data-stu-id="149de-110">See Remarks.</span></span>|  
|`typeName`|<span data-ttu-id="149de-111">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="149de-111">Required.</span></span> <span data-ttu-id="149de-112">İstenen statik üyenin tanımlayan tür adı.</span><span class="sxs-lookup"><span data-stu-id="149de-112">The name of the type that defines the desired static member.</span></span>|  
|`staticMemberName`|<span data-ttu-id="149de-113">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="149de-113">Required.</span></span> <span data-ttu-id="149de-114">İstenen statik değere üyesi (sabit bir değer, bir statik özellik, bir alan veya bir numaralandırma değeri) adı.</span><span class="sxs-lookup"><span data-stu-id="149de-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="149de-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="149de-115">Remarks</span></span>  
 <span data-ttu-id="149de-116">Başvurulan kod varlık aşağıdakilerden biri olması gerekir:</span><span class="sxs-lookup"><span data-stu-id="149de-116">The code entity that is referenced must be one of the following:</span></span>  
  
-   <span data-ttu-id="149de-117">Bir sabiti</span><span class="sxs-lookup"><span data-stu-id="149de-117">A constant</span></span>  
  
-   <span data-ttu-id="149de-118">Bir statik özellik</span><span class="sxs-lookup"><span data-stu-id="149de-118">A static property</span></span>  
  
-   <span data-ttu-id="149de-119">Bir alan</span><span class="sxs-lookup"><span data-stu-id="149de-119">A field</span></span>  
  
-   <span data-ttu-id="149de-120">Bir numaralandırma değeri</span><span class="sxs-lookup"><span data-stu-id="149de-120">An enumeration value</span></span>  
  
 <span data-ttu-id="149de-121">XAML biçimlendirme derlenirken biçimlendirme veya bir XAML yükleme zamanı ayrıştırma özel durumu ise herhangi diğer kod varlığı, statik olmayan bir özellik gibi belirten bir derleme zamanı hatasına neden olur.</span><span class="sxs-lookup"><span data-stu-id="149de-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>  
  
 <span data-ttu-id="149de-122">Yapabileceğiniz `x:Static` statik alanları veya geçerli XAML belgenin; varsayılan XAML ad uzayı bulunmayan özellikleri başvurular ancak, bu önek eşleştirme gerektirir.</span><span class="sxs-lookup"><span data-stu-id="149de-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="149de-123">XAML ad uzayları neredeyse her zaman XAML belgenin kök öğesinin tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="149de-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>  
  
 <span data-ttu-id="149de-124">Varsayılan XAML şema içeriği ile çalışırken statik özellikleri için arama işlemleri .NET Framework XAML hizmetlerinde ve XAML okuyucuları ve XAML yazarlar tarafından gerçekleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="149de-124">The lookup operations for static properties can be performed by .NET Framework XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="149de-125">Bu XAML şema içeriği CLR yansıma Nesne grafiği oluşturması için gerekli statik değerlerini sağlamak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="149de-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="149de-126">`typeName` Belirttiğiniz gerçekte bir XAML türü adı, bir CLR türü adı değil, bunlar varsayılan XAML şema içeriği kullanırken ya da tüm mevcut CLR tabanlı XAML-uygulama çerçeveleri kullanırken temelde aynı adı olmasına rağmen.</span><span class="sxs-lookup"><span data-stu-id="149de-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>  
  
 <span data-ttu-id="149de-127">Yaptığınızda dikkatli `x:Static` doğrudan bir özelliğin değerini türünde olmayan başvuruları.</span><span class="sxs-lookup"><span data-stu-id="149de-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="149de-128">XAML biçimlendirme uzantısı değerlerinden sağlanan sırası işleme çağrılamadı ek değeri dönüştürme.</span><span class="sxs-lookup"><span data-stu-id="149de-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="149de-129">Bu durum geçerlidir olsa bile, `x:Static` başvuru bir metin dizesi oluşturur ve bu belirli üye veya herhangi bir üye değeri dönüş türü değeri dönüştürme metin dizesine genellikle dayalı öznitelik değerleri için oluşur.</span><span class="sxs-lookup"><span data-stu-id="149de-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>  
  
 <span data-ttu-id="149de-130">Öznitelik sözdizimi, bu işaretleme uzantısı ile kullanılan en yaygın sözdizimidir.</span><span class="sxs-lookup"><span data-stu-id="149de-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="149de-131">Sonra sağlanan dize belirteci `x:Static` kimlik dizesi olarak atandığı <xref:System.Windows.Markup.StaticExtension.Member%2A> temel değer <xref:System.Windows.Markup.StaticExtension> uzantısı sınıfı.</span><span class="sxs-lookup"><span data-stu-id="149de-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>  
  
 <span data-ttu-id="149de-132">Teknik olarak mümkün başka iki XAML kullanımı vardır.</span><span class="sxs-lookup"><span data-stu-id="149de-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="149de-133">Ancak, gereksiz yere ayrıntılı olduğundan bu kullanımları daha az yaygın olan:</span><span class="sxs-lookup"><span data-stu-id="149de-133">However, these usages are less common because they are unnecessarily verbose:</span></span>  
  
 <span data-ttu-id="149de-134">**Nesne öğesi sözdizimi:** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName``" .../>`</span><span class="sxs-lookup"><span data-stu-id="149de-134">**Object element syntax:** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName` `" .../>`</span></span>  
  
 <span data-ttu-id="149de-135">**Öznitelik başlatma dizesi için açık üye özelliğiyle sözdizimi:** `<` `object`  ``  `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName``}" .../>`</span><span class="sxs-lookup"><span data-stu-id="149de-135">**Attribute syntax with explicit Member property for initialization string:** `<` `object` `` `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName` `}" .../>`</span></span>  
  
 <span data-ttu-id="149de-136">.NET Framework XAML hizmetlerinde uygulamasında bu biçimlendirme uzantısı işlenmesi tarafından tanımlanan <xref:System.Windows.Markup.StaticExtension> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="149de-136">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>  
  
 <span data-ttu-id="149de-137">`x:Static`bir biçimlendirme uzantısıdır.</span><span class="sxs-lookup"><span data-stu-id="149de-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="149de-138">XAML Kullanımdaki tüm biçimlendirme uzantıları `{` ve `}` olarak XAML işlemci tanıdığı biçimlendirme uzantısı bir değer girmelisiniz kuralı kendi öznitelik sözdiziminde karakterler.</span><span class="sxs-lookup"><span data-stu-id="149de-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="149de-139">Biçimlendirme uzantıları hakkında daha fazla bilgi için bkz: [işaretleme uzantılarına genel bakış XAML](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="149de-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="149de-140">WPF kullanım notları</span><span class="sxs-lookup"><span data-stu-id="149de-140">WPF Usage Notes</span></span>  
 <span data-ttu-id="149de-141">WPF programlama için kullandığınız varsayılan XAML ad uzayı pek çok yararlı statik özellikleri içermiyor ve yararlı statik özelliklerinin çoğu sahip gerek kalmadan kullanım kolaylaştırmak tür dönüştürücüleri gibi destek `{x:Static}` .</span><span class="sxs-lookup"><span data-stu-id="149de-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="149de-142">Statik özellikler için aşağıdakilerden biri doğruysa bir XAML ad alanı için bir önek eşlemeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="149de-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>  
  
-   <span data-ttu-id="149de-143">WPF içinde var, ancak WPF için varsayılan XAML ad uzayı parçası olmayan bir tür başvurma ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="149de-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span></span> <span data-ttu-id="149de-144">Kullanmak için oldukça yaygın bir senaryo budur `x:Static`.</span><span class="sxs-lookup"><span data-stu-id="149de-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="149de-145">Örneğin, kullanabileceğinize bir `x:Static` başvuru için XAML ad alanı eşlemesi ile <xref:System> statik özelliklerini başvurmak için CLR ad alanı ve mscorlib derlemesi <xref:System.Environment> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="149de-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>  
  
-   <span data-ttu-id="149de-146">Bir tür özel derlemesinden başvuruda bulunuyor.</span><span class="sxs-lookup"><span data-stu-id="149de-146">You are referencing a type from a custom assembly.</span></span>  
  
-   <span data-ttu-id="149de-147">Ancak bu tür WPF varsayılan XAML ad uzayı parçası olarak eşlenmedi CLR ad alanı içinde değil bir WPF derlemesinde varolan bir türü başvuruda bulunuyor.</span><span class="sxs-lookup"><span data-stu-id="149de-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="149de-148">Eşleme CLR ad alanlarının varsayılan XAML ad uzayı WPF için çeşitli WPF derlemelerde tanımları tarafından gerçekleştirilen (bu kavram hakkında daha fazla bilgi için bkz: [XAML ad uzayları ve WPF XAML için Namespace eşleme](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span><span class="sxs-lookup"><span data-stu-id="149de-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="149de-149">CLR ad alanları olmayan eşlenen çoğunlukla XAML için genellikle gibi amaçlanmamıştır sınıf tanımları CLR ad oluşuyorsa varolabilir <xref:System.Windows.Threading>.</span><span class="sxs-lookup"><span data-stu-id="149de-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>  
  
 <span data-ttu-id="149de-150">Önekleri ve XAML ad uzayları WPF için nasıl kullanılacağı hakkında daha fazla bilgi için bkz: [XAML ad uzayları ve WPF XAML Namespace eşleme](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="149de-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="149de-151">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="149de-151">See Also</span></span>  
 [<span data-ttu-id="149de-152">x: Type işaretleme uzantısı</span><span class="sxs-lookup"><span data-stu-id="149de-152">x:Type Markup Extension</span></span>](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [<span data-ttu-id="149de-153">WPF'den System.xaml'e geçirilen türler</span><span class="sxs-lookup"><span data-stu-id="149de-153">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)