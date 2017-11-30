---
title: "Nasıl yapılır: Bağımlılık Özelliği için Sahip Türü Ekleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 079f08e1c330b710748ea6bb1aab8ccfb7ae7016
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a><span data-ttu-id="92389-102">Nasıl yapılır: Bağımlılık Özelliği için Sahip Türü Ekleme</span><span class="sxs-lookup"><span data-stu-id="92389-102">How to: Add an Owner Type for a Dependency Property</span></span>
<span data-ttu-id="92389-103">Bu örnekte, farklı bir tür için kayıtlı bir bağımlılık özelliğinin sahibi olarak bir sınıf eklemek gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="92389-103">This example shows how to add a class as an owner of a dependency property registered for a different type.</span></span> <span data-ttu-id="92389-104">Bunu yaparak [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] okuyucu ve özellik sisteminin olan her ikisi de ek bir özellik sahibi olarak sınıfı tanıyabilir.</span><span class="sxs-lookup"><span data-stu-id="92389-104">By doing this, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader and property system are both able to recognize the class as an additional owner of the property.</span></span> <span data-ttu-id="92389-105">Sahibi olarak isteğe bağlı olarak ekleme, türe özgü meta verilerini sağlamak ekleme sınıfına olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="92389-105">Adding as owner optionally allows the adding class to provide type-specific metadata.</span></span>  
  
 <span data-ttu-id="92389-106">Aşağıdaki örnekte, `StateProperty` bir özellik tarafından kayıtlı `MyStateControl` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="92389-106">In the following example, `StateProperty` is a property registered by the `MyStateControl` class.</span></span> <span data-ttu-id="92389-107">Sınıf `UnrelatedStateControl` kendisini sahibi olarak ekler `StateProperty` kullanarak <xref:System.Windows.DependencyProperty.AddOwner%2A> yöntemi, özellikle ekleme türü üzerinde mevcut olmadığından, bağımlılık özelliği için yeni meta sağlayan imza kullanarak.</span><span class="sxs-lookup"><span data-stu-id="92389-107">The class `UnrelatedStateControl` adds itself as an owner of the `StateProperty` using the <xref:System.Windows.DependencyProperty.AddOwner%2A> method, specifically using the signature that allows for new metadata for the dependency property as it exists on the adding type.</span></span> <span data-ttu-id="92389-108">Sağlamaları gereken bildirim [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] erişimciler gösterilen örneğe benzer bir özellik için [bağımlılık özelliği uygulama](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) örnek olarak eklenen sınıf üzerinde bağımlılık özelliği tanımlayıcısını'yeniden kullanıma sahibi olarak.</span><span class="sxs-lookup"><span data-stu-id="92389-108">Notice that you should provide [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] accessors for the property similar to the example shown in the [Implement a Dependency Property](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) example, as well as re-expose the dependency property identifier on the class being added as owner.</span></span>  
  
 <span data-ttu-id="92389-109">Sarmalayıcılar olmadan bağımlılık özelliği hala programlı erişim kullanmanın açısından çalışır <xref:System.Windows.DependencyObject.GetValue%2A> veya <xref:System.Windows.DependencyObject.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="92389-109">Without wrappers, the dependency property would still work from the perspective of programmatic access using <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="92389-110">Ancak, genellikle bu özelliği sistem davranışı ile paralel istediğiniz [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] özelliği sarmalayıcıları.</span><span class="sxs-lookup"><span data-stu-id="92389-110">But you typically want to parallel this property-system behavior with the [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property wrappers.</span></span> <span data-ttu-id="92389-111">Sarmalayıcılar bağımlılık özelliği programlı olarak ayarlamak kolaylaştırmak ve özellikleri olarak ayarlamayı olanaklı hale getirir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] öznitelikleri.</span><span class="sxs-lookup"><span data-stu-id="92389-111">The wrappers make it easier to set the dependency property programmatically, and make it possible to set the properties as [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributes.</span></span>  
  
 <span data-ttu-id="92389-112">Varsayılan meta verileri geçersiz kılmak nasıl öğrenmek için bkz: [bağımlılık özelliği için geçersiz meta veriler](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).</span><span class="sxs-lookup"><span data-stu-id="92389-112">To find out how to override default metadata, see [Override Metadata for a Dependency Property](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="92389-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="92389-113">Example</span></span>  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="92389-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="92389-114">See Also</span></span>  
 [<span data-ttu-id="92389-115">Özel bağımlılık özellikleri</span><span class="sxs-lookup"><span data-stu-id="92389-115">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="92389-116">Bağımlılık özelliklerine genel bakış</span><span class="sxs-lookup"><span data-stu-id="92389-116">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)