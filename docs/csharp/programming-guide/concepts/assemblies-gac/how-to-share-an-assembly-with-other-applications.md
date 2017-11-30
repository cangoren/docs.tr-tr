---
title: "Nasıl yapılır: bir derlemeyi başka uygulamalarla (C#) paylaşma"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dedbd90cdc6f33bfa03ce5e38138ca3b23178b95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a><span data-ttu-id="d517e-102">Nasıl yapılır: bir derlemeyi başka uygulamalarla (C#) paylaşma</span><span class="sxs-lookup"><span data-stu-id="d517e-102">How to: Share an Assembly with Other Applications (C#)</span></span>
<span data-ttu-id="d517e-103">Derlemeler, özel veya paylaşılan olabilir: varsayılan olarak, diğer uygulamalar tarafından kullanılması amaçlanmıştır değil çünkü basit programlarının çoğu özel bir derlemenin oluşur.</span><span class="sxs-lookup"><span data-stu-id="d517e-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="d517e-104">Bir derlemeyi başka uygulamalarla paylaşma için onu yerleştirilmelidir [genel derleme önbelleği](../../../../framework/app-domains/gac.md) (GAC).</span><span class="sxs-lookup"><span data-stu-id="d517e-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="d517e-105">Bir derlemeyi paylaşımı</span><span class="sxs-lookup"><span data-stu-id="d517e-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="d517e-106">Derlemenizi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="d517e-106">Create your assembly.</span></span> <span data-ttu-id="d517e-107">Daha fazla bilgi için bkz: [derlemeler oluşturma](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="d517e-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="d517e-108">Güçlü bir ad, derlemenizi atayın.</span><span class="sxs-lookup"><span data-stu-id="d517e-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="d517e-109">Daha fazla bilgi için bkz: [nasıl yapılır: bir derlemeyi tanımlayıcı adla oturum](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="d517e-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="d517e-110">Sürüm bilgileri, derlemenizi atayın.</span><span class="sxs-lookup"><span data-stu-id="d517e-110">Assign version information to your assembly.</span></span> <span data-ttu-id="d517e-111">Daha fazla bilgi için bkz: [derleme sürümü oluşturma](https://msdn.microsoft.com/library/51ket42z).</span><span class="sxs-lookup"><span data-stu-id="d517e-111">For more information, see [Assembly Versioning](https://msdn.microsoft.com/library/51ket42z).</span></span>  
  
4.  <span data-ttu-id="d517e-112">Derleme genel derleme önbelleğine ekleme.</span><span class="sxs-lookup"><span data-stu-id="d517e-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="d517e-113">Daha fazla bilgi için bkz: [nasıl yapılır: bir derlemeyi genel derleme önbelleğine yükleme](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="d517e-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="d517e-114">Diğer uygulamalardan derlemesinde bulunan türleri erişin.</span><span class="sxs-lookup"><span data-stu-id="d517e-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="d517e-115">Daha fazla bilgi için bkz: [nasıl yapılır: bir Strong-Named derleme başvurusu](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span><span class="sxs-lookup"><span data-stu-id="d517e-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d517e-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d517e-116">See Also</span></span>  
 [<span data-ttu-id="d517e-117">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="d517e-117">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d517e-118">Derlemelerle programlama</span><span class="sxs-lookup"><span data-stu-id="d517e-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)