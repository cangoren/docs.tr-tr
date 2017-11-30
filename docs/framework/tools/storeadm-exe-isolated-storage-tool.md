---
title: "Storeadm.exe (Yalıtılmış Depolama Aracı)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d9ae6b007fe32dfbef973105311ba929cc247e6b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="storeadmexe-isolated-storage-tool"></a><span data-ttu-id="7a65e-102">Storeadm.exe (Yalıtılmış Depolama Aracı)</span><span class="sxs-lookup"><span data-stu-id="7a65e-102">Storeadm.exe (Isolated Storage Tool)</span></span>
<span data-ttu-id="7a65e-103">Yalıtılmış Depolama aracı, geçerli kullanıcı için varolan tüm depoları listeler veya kaldırır.</span><span class="sxs-lookup"><span data-stu-id="7a65e-103">The Isolated Storage tool lists or removes all existing stores for the current user.</span></span>  
  
 <span data-ttu-id="7a65e-104">Bu araç, Visual Studio ile birlikte otomatik olarak yüklenir.</span><span class="sxs-lookup"><span data-stu-id="7a65e-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="7a65e-105">Aracı çalıştırmak için, Geliştirici Komut İstemi (veya Windows 7'de Visual Studio Komut İstemi) kullanın.</span><span class="sxs-lookup"><span data-stu-id="7a65e-105">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="7a65e-106">Daha fazla bilgi için bkz: [komut istemlerini](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="7a65e-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="7a65e-107">Komut satırına şunu yazın:</span><span class="sxs-lookup"><span data-stu-id="7a65e-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a65e-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7a65e-108">Syntax</span></span>  
  
```  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a65e-109">Parametreler</span><span class="sxs-lookup"><span data-stu-id="7a65e-109">Parameters</span></span>  
  
|<span data-ttu-id="7a65e-110">Seçenek</span><span class="sxs-lookup"><span data-stu-id="7a65e-110">Option</span></span>|<span data-ttu-id="7a65e-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7a65e-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7a65e-112">**/h**[**ardım**]</span><span class="sxs-lookup"><span data-stu-id="7a65e-112">**/h**[**elp**]</span></span>|<span data-ttu-id="7a65e-113">Araç için komut sözdizimini ve seçenekleri görüntüler.</span><span class="sxs-lookup"><span data-stu-id="7a65e-113">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="7a65e-114">**/ List**</span><span class="sxs-lookup"><span data-stu-id="7a65e-114">**/list**</span></span>|<span data-ttu-id="7a65e-115">Geçerli kullanıcı için varolan tüm depoları görüntüler.</span><span class="sxs-lookup"><span data-stu-id="7a65e-115">Displays all existing stores for the current user.</span></span> <span data-ttu-id="7a65e-116">Buna, kullanıcı tarafından çalıştırılan tüm uygulamaların veya derlemelerin depoları dahildir.</span><span class="sxs-lookup"><span data-stu-id="7a65e-116">This includes the stores for all applications or assemblies executed by this user.</span></span>|  
|<span data-ttu-id="7a65e-117">**/ Makine**</span><span class="sxs-lookup"><span data-stu-id="7a65e-117">**/machine**</span></span>|<span data-ttu-id="7a65e-118">Makine deposunu seçer.</span><span class="sxs-lookup"><span data-stu-id="7a65e-118">Selects the machine store.</span></span> <span data-ttu-id="7a65e-119">Bu seçenek ile kullanmak **/list** veya **/Kaldır** eylemi makine deposuna uygulamalıdır belirtmek için seçeneği.</span><span class="sxs-lookup"><span data-stu-id="7a65e-119">Use this option with the **/list** or **/remove** option to specify that the action should apply to the machine store.</span></span><br /><br /> <span data-ttu-id="7a65e-120">.NET Framework 2.0'da yeni bir özelliktir</span><span class="sxs-lookup"><span data-stu-id="7a65e-120">New in the .NET Framework 2.0</span></span>|  
|<span data-ttu-id="7a65e-121">**istemci bilgisayarlara**</span><span class="sxs-lookup"><span data-stu-id="7a65e-121">**/quiet**</span></span>|<span data-ttu-id="7a65e-122">Sessiz mod kullanılacağını belirtir; yalnızca hata iletileri görünecek şekilde bilgilendirici çıktıyı engeller.</span><span class="sxs-lookup"><span data-stu-id="7a65e-122">Specifies quiet mode; suppresses informational output so that only error messages appear.</span></span>|  
|<span data-ttu-id="7a65e-123">**/ Remove**</span><span class="sxs-lookup"><span data-stu-id="7a65e-123">**/remove**</span></span>|<span data-ttu-id="7a65e-124">Geçerli kullanıcı için varolan tüm depoları kalıcı olarak kaldırır.</span><span class="sxs-lookup"><span data-stu-id="7a65e-124">Permanently removes all existing stores for the current user.</span></span>|  
|<span data-ttu-id="7a65e-125">**/ Dolaşım**</span><span class="sxs-lookup"><span data-stu-id="7a65e-125">**/roaming**</span></span>|<span data-ttu-id="7a65e-126">Dolaşım deposunu seçer.</span><span class="sxs-lookup"><span data-stu-id="7a65e-126">Selects the roaming store.</span></span> <span data-ttu-id="7a65e-127">Bu seçenek ile kullanmak **/list** veya **/Kaldır** eylemi gezici deposuna uygulamalıdır belirtmek için Seçenekler.</span><span class="sxs-lookup"><span data-stu-id="7a65e-127">Use this option with the **/list** or **/remove** options to specify that the action should apply to the roaming store.</span></span>|  
|<span data-ttu-id="7a65e-128">**/?**</span><span class="sxs-lookup"><span data-stu-id="7a65e-128">**/?**</span></span>|<span data-ttu-id="7a65e-129">Araç için komut sözdizimini ve seçenekleri görüntüler.</span><span class="sxs-lookup"><span data-stu-id="7a65e-129">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a65e-130">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7a65e-130">Remarks</span></span>  
 <span data-ttu-id="7a65e-131">Herhangi bir seçenek belirtmeden Storeadm.exe'yi komut satırından çalıştırmak sözdizimini ve araç için seçenekleri görüntüler.</span><span class="sxs-lookup"><span data-stu-id="7a65e-131">Running Storeadm.exe from the command line without specifying any options displays the syntax and options for the tool.</span></span>  
  
 <span data-ttu-id="7a65e-132">**/List** ve **/Kaldır** seçenekleri genellikle kullanılan birer birer; iki veya daha fazla seçenek belirtilmezse, ancak bunlar komut satırında göründükleri sırada gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="7a65e-132">The **/list** and **/remove** options are typically used one at a time; however, if two or more options are specified they will be performed in the order in which they appear on the command line.</span></span>  
  
 <span data-ttu-id="7a65e-133">Uygulamaların, bir kullanıcı için iki depodan birine veya makine deposuna kaydetme seçeneği vardır:</span><span class="sxs-lookup"><span data-stu-id="7a65e-133">Applications have a choice of saving to one of two stores for a user or to the machine store:</span></span>  
  
-   <span data-ttu-id="7a65e-134">Kullanıcı için gezici kullanıcı verileri etkin olsa bile (Windows 2000 ve daha sonra) dolaştırmamayı garanti bir konumda yerel deposu bulunmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7a65e-134">The local store exists in a location that is guaranteed not to roam (on Windows 2000 and later) even if user data roaming is enabled for the user.</span></span>  
  
-   <span data-ttu-id="7a65e-135">Dolaşım deposu dolaşan kurabilen bir konumda var, ancak Windows NT Yönetim aracılığıyla kullanıcı için gezici etkinse, yalnızca bunu yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7a65e-135">The roaming store exists in a location that is able to roam, but can only do so if roaming is enabled for the user via Windows NT administration.</span></span>  
  
-   <span data-ttu-id="7a65e-136">Makine deposu bir makinedeki tüm kullanıcılar için ortaktır ve o makinede ortak bir dizin altında depolanır.</span><span class="sxs-lookup"><span data-stu-id="7a65e-136">The machine store is common to all users on a machine and is stored under a common directory on that machine.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a65e-137">Makine deposu .NET Framework sürüm 2.0'da yeni bir özelliktir.</span><span class="sxs-lookup"><span data-stu-id="7a65e-137">The machine store is new in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="7a65e-138">Dolaşımın kullanıcı için etkinleştirilip etkinleştirilmediği Storeadm.exe'nin yönetimini etkilemez.</span><span class="sxs-lookup"><span data-stu-id="7a65e-138">Whether roaming is actually enabled for the user does not affect the administration of Storeadm.exe.</span></span> <span data-ttu-id="7a65e-139">Aracı hiçbir seçenek olmadan çalıştırmak yerel depoya tüm işlemleri uygular.</span><span class="sxs-lookup"><span data-stu-id="7a65e-139">Running the tool without any options applies all actions to the local store.</span></span> <span data-ttu-id="7a65e-140">Aracı ile çalışan **/ gezici** seçeneği dolaşabilir deposu tüm eylemleri uygular.</span><span class="sxs-lookup"><span data-stu-id="7a65e-140">Running the tool with the **/roaming** option applies all actions to the store that is able to roam.</span></span> <span data-ttu-id="7a65e-141">Aracı ile çalışan **/makine** seçeneği makine deposuna tüm eylemleri uygular.</span><span class="sxs-lookup"><span data-stu-id="7a65e-141">Running the tool with the **/machine** option applies all actions to the machine store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a65e-142">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7a65e-142">See Also</span></span>  
 [<span data-ttu-id="7a65e-143">Araçları</span><span class="sxs-lookup"><span data-stu-id="7a65e-143">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="7a65e-144">Yalıtılmış Depolama</span><span class="sxs-lookup"><span data-stu-id="7a65e-144">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="7a65e-145">Komut istemleri</span><span class="sxs-lookup"><span data-stu-id="7a65e-145">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)