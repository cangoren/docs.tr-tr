---
title: "Azaltma: Ürün Sürümü Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b507769ba6868a4cd841ca463900b126cfb5b90
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-product-versioning"></a><span data-ttu-id="d6c3c-102">Azaltma: Ürün Sürümü Oluşturma</span><span class="sxs-lookup"><span data-stu-id="d6c3c-102">Mitigation: Product Versioning</span></span>
<span data-ttu-id="d6c3c-103">İçinde [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ve ürün sürümü oluşturma (.NET Framework 4, 4.5, 4.5.1 ve 4.5.2) .NET Framework'ün önceki sürümlerden daha sonra değişti.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] and later, product versioning has changed from the previous releases of the .NET Framework (the .NET Framework 4, 4.5, 4.5.1, and 4.5.2).</span></span>  
  
## <a name="product-versioning-changes"></a><span data-ttu-id="d6c3c-104">Ürün sürümü oluşturma değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="d6c3c-104">Product versioning changes</span></span>  
 <span data-ttu-id="d6c3c-105">Ayrıntılı değişiklikler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="d6c3c-105">The following are the detailed changes:</span></span>  
  
-   <span data-ttu-id="d6c3c-106">Değeri `Version` girişi `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` anahtarı için değişti `4.6.` *xxxxx* .NET Framework 4.6 ve onun noktası serbest bırakır ve için `4.7.` *xxxxx* için. NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-106">The value of the `Version` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key has changed to `4.6.`*xxxxx* for the .NET Framework 4.6 and its point releases, and to `4.7.`*xxxxx* for the .NET Framework 4.7.</span></span> <span data-ttu-id="d6c3c-107">İsteğe bağlı olarak .NET Framework 4.5 ve 4.5.1 4.5.2, biçimi hatalıydı `4.5.` *xxxxx*.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-107">In the .NET Framework 4.5, 4.5.1, and 4.5.2, it had the format `4.5.`*xxxxx*.</span></span>  
  
-   <span data-ttu-id="d6c3c-108">.NET Framework dosyalar için dosya ve ürün sürümü oluşturma önceki sürüm düzeninden değişti `4.0.30319.x` için `4.6.X.0` .NET Framework 4.6 ve onun noktası serbest bırakır ve için `4.7.X.0` .NET Framework 4.7 ve kendi noktası için serbest bırakır.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-108">The file and product versioning for .NET Framework files has changed from the earlier versioning scheme of `4.0.30319.x` to `4.6.X.0` for the .NET Framework 4.6 and its point releases, and to `4.7.X.0` for the .NET Framework 4.7 and its point releases.</span></span> <span data-ttu-id="d6c3c-109">Dosyanın görüntülediğinizde, bu yeni değerler görebilirsiniz **özellikleri** bir dosyaya sağ tıklatıp sonra.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-109">You can see these new values when you view the file's **Properties** after right-clicking on a file.</span></span>  
  
-   <span data-ttu-id="d6c3c-110"><xref:System.Reflection.AssemblyFileVersionAttribute> Ve <xref:System.Reflection.AssemblyInformationalVersionAttribute> Yönetilen derlemeler için öznitelikleri <xref:System.Version> form değerleri `4.6.X.0` .NET Framework 4.6 ve onun noktası serbest bırakır ve `4.7.X.0` için .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-110">The <xref:System.Reflection.AssemblyFileVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes for managed assemblies have <xref:System.Version> values in the form `4.6.X.0` for the .NET Framework 4.6 and its point releases, and `4.7.X.0` for the .NET Framework 4.7.</span></span>  
  
-   <span data-ttu-id="d6c3c-111">İçinde [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2 ve 4.7, <xref:System.Environment.Version%2A?displayProperty=nameWithType> özelliği döndürür sabit sürüm dizesi `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-111">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2, and 4.7, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns the fixed version string `4.0.30319.42000`.</span></span> <span data-ttu-id="d6c3c-112">İsteğe bağlı olarak .NET Framework 4, 4.5, 4.5.1 ve 4.5.2, sürüm dizelerini biçimde döndürür `4.0.30319.xxxxx` (örneğin, "4.0.30319.18010").</span><span class="sxs-lookup"><span data-stu-id="d6c3c-112">In the .NET Framework 4, 4.5, 4.5.1, and 4.5.2, it returns version strings in the format `4.0.30319.xxxxx` (for example, "4.0.30319.18010").</span></span> <span data-ttu-id="d6c3c-113">Yeni bir bağımlılık almayı uygulama kodu önermiyoruz Not <xref:System.Environment.Version%2A?displayProperty=nameWithType> özelliği.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-113">Note that we do not recommend application code taking any new dependency on the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property.</span></span>  
  
### <a name="handling-the-product-versioning-changes"></a><span data-ttu-id="d6c3c-114">Ürün sürümü oluşturma değişiklikleri işleme</span><span class="sxs-lookup"><span data-stu-id="d6c3c-114">Handling the product versioning changes</span></span>  
 <span data-ttu-id="d6c3c-115">Genel olarak, uygulamalar .NET Framework ve yükleme dizinini çalışma zamanı sürümü gibi şeyler saptamak için önerilen teknikleri bağlı:</span><span class="sxs-lookup"><span data-stu-id="d6c3c-115">In general, applications should depend on the recommended techniques for detecting such things as the runtime version of the .NET Framework and the installation directory:</span></span>  
  
-   <span data-ttu-id="d6c3c-116">.NET Framework çalışma zamanı sürümü algılamak için bkz: [nasıl yapılır: belirlemek, .NET Framework sürümlerinin yüklendiğini](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="d6c3c-116">To detect the runtime version of the .NET Framework, see [How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>  
  
-   <span data-ttu-id="d6c3c-117">.NET Framework için yükleme yolu belirlemek için değerini kullanmak `InstallPath` girişi `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` anahtarı.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-117">To determine the installation path for the .NET Framework, use the value of the `InstallPath` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d6c3c-118">Alt anahtar adı `NET Framework Setup`değil `.NET Framework Setup`.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-118">The subkey name is `NET Framework Setup`, not `.NET Framework Setup`.</span></span>  
  
-   <span data-ttu-id="d6c3c-119">.NET Framework ortak dil çalışma zamanı dizin yolu belirlemek için arama <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-119">To determine the directory path to the .NET Framework common language runtime, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="d6c3c-120">CLR sürümünü almak için arama <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-120">To get the CLR version, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType> method.</span></span>   <span data-ttu-id="d6c3c-121">.NET Framework 4 ve kendi noktası için serbest (.NET Framework 4.5, 4.5.1, 4.5.2 ve [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2 ve 4.7), bir dize döndürür `v4.0.30319`.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-121">For the .NET Framework 4 and its point releases (the .NET Framework 4.5, 4.5.1, 4.5.2, and [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2, and 4.7), it returns the string `v4.0.30319`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c3c-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-122">See Also</span></span>  
 [<span data-ttu-id="d6c3c-123">Çalışma zamanı değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="d6c3c-123">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
 