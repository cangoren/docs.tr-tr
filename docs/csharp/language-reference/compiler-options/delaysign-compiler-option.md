---
title: "-delaysign (C# Derleyici Seçenekleri)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 62f76747a29a90562706dff5fa742316c5b99b74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="delaysign-c-compiler-options"></a><span data-ttu-id="aa304-102">/delaysign (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="aa304-102">/delaysign (C# Compiler Options)</span></span>
<span data-ttu-id="aa304-103">Bu seçenek, böylece bir dijital imza daha sonra eklenebilir çıktı dosyasında yer ayırmak için derleyici neden olur.</span><span class="sxs-lookup"><span data-stu-id="aa304-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa304-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="aa304-104">Syntax</span></span>  
  
```console  
/delaysign[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="aa304-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="aa304-105">Arguments</span></span>  
 <span data-ttu-id="aa304-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="aa304-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="aa304-107">Kullanım **/delaysign-** tam imzalı bir derleme istiyorsanız.</span><span class="sxs-lookup"><span data-stu-id="aa304-107">Use **/delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="aa304-108">Kullanım **/delaysign+** yalnızca ortak anahtar derlemede yerleştirmek istiyorsanız.</span><span class="sxs-lookup"><span data-stu-id="aa304-108">Use **/delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="aa304-109">Varsayılan değer **/delaysign-**.</span><span class="sxs-lookup"><span data-stu-id="aa304-109">The default is **/delaysign-**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa304-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="aa304-110">Remarks</span></span>  
 <span data-ttu-id="aa304-111">**/Delaysign** seçeneği hiçbir etkisi ile kullanılmadığı sürece [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) veya [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="aa304-111">The **/delaysign** option has no effect unless used with [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) or [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span>  
  
 <span data-ttu-id="aa304-112">Tam imzalı bir derleme istediğinde bildirimi (derleme meta verilerini) içeren ve karmayı özel anahtarıyla imzalar dosyayı derleyici karma hale getirir.</span><span class="sxs-lookup"><span data-stu-id="aa304-112">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="aa304-113">Elde edilen dijital imza, bildirimi içeren dosyada depolanır.</span><span class="sxs-lookup"><span data-stu-id="aa304-113">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="aa304-114">Bir derlemeyi imzalı gecikme olduğunda derleyici işlem değil ve daha sonra imzanın eklenmesi için imza ancak yer ayırır dosyasında depolamak.</span><span class="sxs-lookup"><span data-stu-id="aa304-114">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="aa304-115">Örneğin, kullanarak **/delaysign+** genel önbelleğinde derleme yerleştirilecek tester sağlar.</span><span class="sxs-lookup"><span data-stu-id="aa304-115">For example, using **/delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="aa304-116">Sınama sonra tam olarak derleme özel anahtarı kullanarak derlemeye koyarak oturum [derleme bağlayıcı](../../../framework/tools/al-exe-assembly-linker.md) yardımcı programı.</span><span class="sxs-lookup"><span data-stu-id="aa304-116">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>  
  
 <span data-ttu-id="aa304-117">Daha fazla bilgi için bkz: [bkz](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) ve [Gecikmeli bir derleme imzalama](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="aa304-117">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="aa304-118">Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="aa304-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="aa304-119">Açık **özellikleri** projesi için sayfa.</span><span class="sxs-lookup"><span data-stu-id="aa304-119">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="aa304-120">Değiştirme **gecikme yalnızca oturum** özelliği.</span><span class="sxs-lookup"><span data-stu-id="aa304-120">Modify the **Delay sign only** property.</span></span>  
  
 <span data-ttu-id="aa304-121">Bu derleyici seçeneği programlı olarak nasıl ayarlanacağı hakkında daha fazla bilgi için bkz: <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="aa304-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa304-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="aa304-122">See Also</span></span>  
 [<span data-ttu-id="aa304-123">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="aa304-123">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="aa304-124">Proje ve çözüm özelliklerini yönetme</span><span class="sxs-lookup"><span data-stu-id="aa304-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)