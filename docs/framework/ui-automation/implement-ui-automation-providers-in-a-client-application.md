---
title: "UI Otomasyon Sağlayıcıları İstemci Programına Uygulama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
caps.latest.revision: "6"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: ae7b478ec8d836f1e0772d81185b9bb0119c0fa8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="4d379-102">UI Otomasyon Sağlayıcıları İstemci Programına Uygulama</span><span class="sxs-lookup"><span data-stu-id="4d379-102">Implement UI Automation Providers in a Client Application</span></span>
> [!NOTE]
>  <span data-ttu-id="4d379-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="4d379-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4d379-104">Hakkında en yeni bilgiler için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Otomasyon API: UI Otomasyonu](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="4d379-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4d379-105">Bu konu, bir uygulama içinde istemci tarafı UI Otomasyonu sağlayıcıyı uygulama gösteren kod örneği içerir.</span><span class="sxs-lookup"><span data-stu-id="4d379-105">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="4d379-106">Bu seyrek bir senaryodur.</span><span class="sxs-lookup"><span data-stu-id="4d379-106">This is an uncommon scenario.</span></span> <span data-ttu-id="4d379-107">Genellikle, bir UI Otomasyonu istemci uygulaması sunucu tarafı sağlayıcıları veya DLL'de bulunan istemci-tarafı sağlayıcıları kullanır.</span><span class="sxs-lookup"><span data-stu-id="4d379-107">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d379-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="4d379-108">Example</span></span>  
 <span data-ttu-id="4d379-109">Aşağıdaki örnek kod bir konsol penceresi için basit bir sağlayıcı uygular.</span><span class="sxs-lookup"><span data-stu-id="4d379-109">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="4d379-110">Kod yararlı bir işlevi yoktur, ancak istemci kod içinde bir sağlayıcı ayarlama ve kullanarak kaydetme temel adımları göstermek için tasarlanmıştır <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d379-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="4d379-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4d379-111">See Also</span></span>  
 [<span data-ttu-id="4d379-112">UI Otomasyon sağlayıcılara genel bakış</span><span class="sxs-lookup"><span data-stu-id="4d379-112">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="4d379-113">İstemci tarafı sağlayıcı derlemesini kaydetme</span><span class="sxs-lookup"><span data-stu-id="4d379-113">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)  
 [<span data-ttu-id="4d379-114">İstemci tarafı UI Otomasyon sağlayıcı oluşturma</span><span class="sxs-lookup"><span data-stu-id="4d379-114">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)  
 [<span data-ttu-id="4d379-115">İstemci tarafı UI Otomasyon sağlayıcıyı uygulama</span><span class="sxs-lookup"><span data-stu-id="4d379-115">Client-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)