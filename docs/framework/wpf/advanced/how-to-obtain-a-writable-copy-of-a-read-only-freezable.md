---
title: "Nasıl yapılır: Salt Okunur Freezable'ın Yazılabilir Kopyasını Edinme"
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
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6925e9322063d68d0d7f8c8e048eed254cd14ed7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="3533e-102">Nasıl yapılır: Salt Okunur Freezable'ın Yazılabilir Kopyasını Edinme</span><span class="sxs-lookup"><span data-stu-id="3533e-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="3533e-103">Bu örnek nasıl kullanılacağını gösterir <xref:System.Windows.Freezable.Clone%2A> salt okunur yazılabilir bir kopyasını oluşturmak için yöntemi <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="3533e-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="3533e-104">Sonra bir <xref:System.Windows.Freezable> nesne işaretlenmiş salt okunur ("dondurulmuş"), onu değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="3533e-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="3533e-105">Ancak, kullanabileceğiniz <xref:System.Windows.Freezable.Clone%2A> dondurulmuş nesne değiştirilebilir bir kopyasını oluşturmak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3533e-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3533e-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="3533e-106">Example</span></span>  
 <span data-ttu-id="3533e-107">Aşağıdaki örnek, dondurulmuş değiştirilebilir kopyasını oluşturur <xref:System.Windows.Media.SolidColorBrush> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="3533e-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="3533e-108">Hakkında daha fazla bilgi için <xref:System.Windows.Freezable> nesneleri bkz [Freezable nesnelere genel bakış](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3533e-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3533e-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3533e-109">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CloneCurrentValue%2A>  
 [<span data-ttu-id="3533e-110">Freezable nesnelere genel bakış</span><span class="sxs-lookup"><span data-stu-id="3533e-110">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="3533e-111">Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="3533e-111">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)