---
title: "Nasıl yapılır: Freezable'ı Salt Okunur Yapma"
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
helpviewer_keywords: Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c407a2fcccfbda29ba23f63ba6ae71302c734d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="bb2aa-102">Nasıl yapılır: Freezable'ı Salt Okunur Yapma</span><span class="sxs-lookup"><span data-stu-id="bb2aa-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="bb2aa-103">Bu örnek nasıl yapılacağını gösteren bir <xref:System.Windows.Freezable> salt okunur çağırarak kendi <xref:System.Windows.Freezable.Freeze%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="bb2aa-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="bb2aa-104">Freeze olamaz bir <xref:System.Windows.Freezable> aşağıdaki koşullardan herhangi biri olup olmadığını nesne `true` nesneyle ilgili:</span><span class="sxs-lookup"><span data-stu-id="bb2aa-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
-   <span data-ttu-id="bb2aa-105">Animasyonlu veya veri ilişkili özellikleri.</span><span class="sxs-lookup"><span data-stu-id="bb2aa-105">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="bb2aa-106">Dinamik bir kaynak tarafından ayarlanan özellikleri vardır.</span><span class="sxs-lookup"><span data-stu-id="bb2aa-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="bb2aa-107">Dinamik kaynaklar hakkında daha fazla bilgi için bkz: [XAML kaynakları](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="bb2aa-107">For more information about dynamic resources, see the [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
-   <span data-ttu-id="bb2aa-108">İçerdiği <xref:System.Windows.Freezable> dondurulmuş olamaz alt nesneler.</span><span class="sxs-lookup"><span data-stu-id="bb2aa-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="bb2aa-109">Bu koşullar olduğunda `false` için <xref:System.Windows.Freezable> nesne ve düşünmüyorsanız değiştirmek için performans avantajı için dondurmayı göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="bb2aa-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb2aa-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="bb2aa-110">Example</span></span>  
 <span data-ttu-id="bb2aa-111">Aşağıdaki örnek donuyor bir <xref:System.Windows.Media.SolidColorBrush>, bir tür olduğu <xref:System.Windows.Freezable> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="bb2aa-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="bb2aa-112">Hakkında daha fazla bilgi için <xref:System.Windows.Freezable> nesneleri bkz [Freezable nesnelere genel bakış](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bb2aa-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb2aa-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bb2aa-113">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="bb2aa-114">Freezable nesnelere genel bakış</span><span class="sxs-lookup"><span data-stu-id="bb2aa-114">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="bb2aa-115">Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="bb2aa-115">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)