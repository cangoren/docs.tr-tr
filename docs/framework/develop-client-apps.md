---
title: ".NET Framework ile İstemci Uygulamaları Geliştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- client application services
- applications [Windows Forms]
- Windows Presentation Foundation, in Visual Studio
- WPF, in Visual Studio
- Windows applications
- rich client applications
- .NET applications, Windows applications
- Visual Basic code, creating applications
- Visual C#, creating applications
- client/server applications, Windows applications
ms.assetid: 2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: daf09f94b4c0854365274773f8c426cc07e8c6dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="developing-client-applications-with-the-net-framework"></a><span data-ttu-id="a7fa4-102">.NET Framework ile İstemci Uygulamaları Geliştirme</span><span class="sxs-lookup"><span data-stu-id="a7fa4-102">Developing Client Applications with the .NET Framework</span></span>
<span data-ttu-id="a7fa4-103">Kullanıcıların bilgisayarları veya cihazları yerel olarak çalışan Windows tabanlı uygulamalar .NET framework ile geliştirmek için birden çok yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="a7fa4-103">There are multiple ways to develop Windows-based applications with the .NET framework that run locally on users' computers or devices.</span></span> <span data-ttu-id="a7fa4-104">Bu bölüm, Windows Presentation Foundation (WPF) kullanarak veya Windows formları kullanarak Windows tabanlı uygulamalar oluşturmak nasıl açıklayan konuları içerir.</span><span class="sxs-lookup"><span data-stu-id="a7fa4-104">This section contains topics that describe how to create Windows-based applications by using Windows Presentation Foundation (WPF) or by using Windows Forms.</span></span> <span data-ttu-id="a7fa4-105">Ancak, .NET Framework kullanarak web uygulamaları ve istemci uygulamalarını bilgisayarları veya Windows mağazası veya Windows Phone mağazası kullanılabilir hale de oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a7fa4-105">However, you can also create web applications using the .NET Framework, and client applications for computers or devices that you make available through the Windows Store or Windows Phone Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7fa4-106">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="a7fa4-106">In This Section</span></span>  
 [<span data-ttu-id="a7fa4-107">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="a7fa4-107">Windows Presentation Foundation</span></span>](../../docs/framework/wpf/index.md)  
 <span data-ttu-id="a7fa4-108">WPF kullanarak uygulamaları geliştirme hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="a7fa4-108">Provides information about developing applications by using WPF.</span></span>  
  
 [<span data-ttu-id="a7fa4-109">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a7fa4-109">Windows Forms</span></span>](../../docs/framework/winforms/index.md)  
 <span data-ttu-id="a7fa4-110">Windows Forms kullanarak uygulamaları geliştirme hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="a7fa4-110">Provides information about developing applications by using Windows Forms.</span></span>  
  
 [<span data-ttu-id="a7fa4-111">Ortak istemci teknolojileri</span><span class="sxs-lookup"><span data-stu-id="a7fa4-111">Common Client Technologies</span></span>](../../docs/framework/common-client-technologies/index.md)  
 <span data-ttu-id="a7fa4-112">İstemci uygulamaları geliştirirken kullanılan ek teknolojiler hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="a7fa4-112">Provides information about additional technologies that can be used when developing client applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a7fa4-113">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="a7fa4-113">Related Sections</span></span>  
 [<span data-ttu-id="a7fa4-114">Windows mağazası uygulamaları</span><span class="sxs-lookup"><span data-stu-id="a7fa4-114">Windows Store apps</span></span>](http://msdn.microsoft.com/windows/apps/)  
 <span data-ttu-id="a7fa4-115">Windows mağazası aracılığıyla kullanıcılara kullanılabilir yapabileceğiniz uygulamaları oluşturmayı açıklar</span><span class="sxs-lookup"><span data-stu-id="a7fa4-115">Describes how to create apps that you can make available to users through the Windows Store</span></span>  
  
 [<span data-ttu-id="a7fa4-116">Mağaza uygulamaları için .NET</span><span class="sxs-lookup"><span data-stu-id="a7fa4-116">.NET for Store apps</span></span>](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 <span data-ttu-id="a7fa4-117">Windows bilgisayarları ve aygıtları dağıtılabilir mağazası uygulamaları için .NET Framework Destek açıklanır.</span><span class="sxs-lookup"><span data-stu-id="a7fa4-117">Describes the .NET Framework support for Store apps, which can be deployed to Windows computers and devices.</span></span>  
  
 <span data-ttu-id="a7fa4-118">[Windows Phone Silverlight için .NET API](http://msdn.microsoft.com/library/windows/apps/xaml/jj207211\(v=vs.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="a7fa4-118">[.NET API for Windows Phone Silverlight](http://msdn.microsoft.com/library/windows/apps/xaml/jj207211\(v=vs.105\).aspx)</span></span>  
 <span data-ttu-id="a7fa4-119">.NET Framework ile Windows Phone Silverlight uygulamaları oluşturmak için kullanabileceğiniz API'ları Listele</span><span class="sxs-lookup"><span data-stu-id="a7fa4-119">List the .NET Framework APIs you can use for building apps with Windows Phone Silverlight</span></span>  
  
 [<span data-ttu-id="a7fa4-120">Birden çok platform için geliştirme</span><span class="sxs-lookup"><span data-stu-id="a7fa4-120">Developing for Multiple Platforms</span></span>](../../docs/standard/cross-platform/index.md)  
 <span data-ttu-id="a7fa4-121">.NET Framework birden çok istemci uygulama türleri hedeflemek için kullanabileceğiniz farklı yöntemler açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="a7fa4-121">Describes the different methods you can use the .NET Framework to target multiple client app types.</span></span>  
  
 [<span data-ttu-id="a7fa4-122">ASP.NET Web siteleri ile çalışmaya başlama</span><span class="sxs-lookup"><span data-stu-id="a7fa4-122">Get Started with ASP.NET Web Sites</span></span>](http://www.asp.net/get-started/websites)  
 <span data-ttu-id="a7fa4-123">ASP.NET kullanarak web uygulamaları geliştirmek yolları açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="a7fa4-123">Describes the ways you can develop web apps using ASP.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7fa4-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a7fa4-124">See Also</span></span>  
 [<span data-ttu-id="a7fa4-125">Taşınabilir sınıf kitaplığı</span><span class="sxs-lookup"><span data-stu-id="a7fa4-125">Portable Class Library</span></span>](../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)  
 [<span data-ttu-id="a7fa4-126">Genel bakış</span><span class="sxs-lookup"><span data-stu-id="a7fa4-126">Overview</span></span>](../../docs/framework/get-started/overview.md)  
 [<span data-ttu-id="a7fa4-127">Geliştirme Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="a7fa4-127">Development Guide</span></span>](../../docs/framework/development-guide.md)  
 [<span data-ttu-id="a7fa4-128">Nasıl yapılır: bir Windows masaüstü uygulaması oluşturma</span><span class="sxs-lookup"><span data-stu-id="a7fa4-128">How to: Create a Windows Desktop Application</span></span>](http://msdn.microsoft.com/library/47021403-eaca-4c34-946a-a26c42a64148)  
 [<span data-ttu-id="a7fa4-129">Windows hizmet uygulamaları</span><span class="sxs-lookup"><span data-stu-id="a7fa4-129">Windows Service Applications</span></span>](../../docs/framework/windows-services/index.md)