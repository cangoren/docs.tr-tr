---
title: /main
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2697b837a536b1b879196bd10843a2b76314747a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="main"></a><span data-ttu-id="fb112-102">/main</span><span class="sxs-lookup"><span data-stu-id="fb112-102">/main</span></span>
<span data-ttu-id="fb112-103">Sınıf veya içeren modülünü belirtir `Sub Main` yordamı.</span><span class="sxs-lookup"><span data-stu-id="fb112-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb112-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="fb112-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="fb112-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="fb112-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="fb112-106">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="fb112-106">Required.</span></span> <span data-ttu-id="fb112-107">Tam nitelenmiş sınıfı ya da içeren modülünü `Sub Main` program başladığında çağrılacak yordamı.</span><span class="sxs-lookup"><span data-stu-id="fb112-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="fb112-108">Bu formda olabilir **/main:module** veya **/main:namespace.module**.</span><span class="sxs-lookup"><span data-stu-id="fb112-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb112-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="fb112-109">Remarks</span></span>  
 <span data-ttu-id="fb112-110">Bir yürütülebilir dosya veya Windows yürütülebilir program oluşturduğunuzda, bu seçeneği kullanın.</span><span class="sxs-lookup"><span data-stu-id="fb112-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="fb112-111">Varsa **/ana** seçeneği atlanırsa, derleyici geçerli bir için paylaşılan arar `Sub Main` tüm ortak sınıfları ve modüller.</span><span class="sxs-lookup"><span data-stu-id="fb112-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="fb112-112">Bkz: [Visual Basic'de ana yordam](../../../visual-basic/programming-guide/program-structure/main-procedure.md) çeşitli formlarının Tartışması için `Main` yordamı.</span><span class="sxs-lookup"><span data-stu-id="fb112-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="fb112-113">Zaman `location` öğesinden devralınan bir sınıf <xref:System.Windows.Forms.Form>, varsayılan derleyici sağlar `Main` sınıfı Hayır ise, uygulama başladığında yordamı `Main` yordamı.</span><span class="sxs-lookup"><span data-stu-id="fb112-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="fb112-114">Bu, komut satırında geliştirme ortamında oluşturulan kod derleme sağlar.</span><span class="sxs-lookup"><span data-stu-id="fb112-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="fb112-115">Tümleşik geliştirme ortamı/Main Visual Studio'da ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="fb112-115">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="fb112-116">Seçili bir projeyi **Çözüm Gezgini**.</span><span class="sxs-lookup"><span data-stu-id="fb112-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fb112-117">Üzerinde **proje** menüsünde tıklatın **özellikleri**.</span><span class="sxs-lookup"><span data-stu-id="fb112-117">On the **Project** menu, click **Properties**.</span></span>  
  
     <span data-ttu-id="fb112-118">Daha fazla bilgi için bkz: [Proje Tasarımcısı giriş](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="fb112-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="fb112-119">Tıklatın **uygulama** sekmesi.</span><span class="sxs-lookup"><span data-stu-id="fb112-119">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="fb112-120">Emin olun **etkinleştir uygulama çerçevesi** onay kutusu işaretli değildir.</span><span class="sxs-lookup"><span data-stu-id="fb112-120">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="fb112-121">Değer değiştirme **Başlangıç nesnesi** kutusu.</span><span class="sxs-lookup"><span data-stu-id="fb112-121">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb112-122">Örnek</span><span class="sxs-lookup"><span data-stu-id="fb112-122">Example</span></span>  
 <span data-ttu-id="fb112-123">Aşağıdaki kod derlerken `T2.vb` ve `T3.vb`, belirtme, `Sub Main` yordamı bulunan `Test2` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="fb112-123">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb112-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fb112-124">See Also</span></span>  
 [<span data-ttu-id="fb112-125">Visual Basic komut satırı derleyicisi</span><span class="sxs-lookup"><span data-stu-id="fb112-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="fb112-126">/ target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb112-126">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="fb112-127">Örnek derleme komut satırları</span><span class="sxs-lookup"><span data-stu-id="fb112-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="fb112-128">NIB: Visual Basic Hello, World sürümü</span><span class="sxs-lookup"><span data-stu-id="fb112-128">NIB: Visual Basic Version of Hello, World</span></span>](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [<span data-ttu-id="fb112-129">Visual Basic'de ana yordam</span><span class="sxs-lookup"><span data-stu-id="fb112-129">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)