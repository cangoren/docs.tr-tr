---
title: 1015 - StartCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7457b65f81e9e26b9de6055df474a83ce4264846
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="fda65-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="fda65-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fda65-103">Özellikler</span><span class="sxs-lookup"><span data-stu-id="fda65-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fda65-104">Kimlik</span><span class="sxs-lookup"><span data-stu-id="fda65-104">ID</span></span>|<span data-ttu-id="fda65-105">1015</span><span class="sxs-lookup"><span data-stu-id="fda65-105">1015</span></span>|  
|<span data-ttu-id="fda65-106">Anahtar Sözcükler</span><span class="sxs-lookup"><span data-stu-id="fda65-106">Keywords</span></span>|<span data-ttu-id="fda65-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fda65-107">WFRuntime</span></span>|  
|<span data-ttu-id="fda65-108">Düzey</span><span class="sxs-lookup"><span data-stu-id="fda65-108">Level</span></span>|<span data-ttu-id="fda65-109">Ayrıntılı</span><span class="sxs-lookup"><span data-stu-id="fda65-109">Verbose</span></span>|  
|<span data-ttu-id="fda65-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="fda65-110">Channel</span></span>|<span data-ttu-id="fda65-111">Microsoft Windows uygulaması sunucu-uygulamalar/hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="fda65-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fda65-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="fda65-112">Description</span></span>  
 <span data-ttu-id="fda65-113">Bir CompletionWorkItem yürütme başlanacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="fda65-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fda65-114">İleti</span><span class="sxs-lookup"><span data-stu-id="fda65-114">Message</span></span>  
 <span data-ttu-id="fda65-115">Üst etkinlik '%1', DisplayName için CompletionWorkItem yürütülmesi başlatılıyor: '%2', örnek kimliği: '%3'.</span><span class="sxs-lookup"><span data-stu-id="fda65-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="fda65-116">'%4', DisplayName etkinliği tamamlandı: '%5', örnek kimliği: '%6'.</span><span class="sxs-lookup"><span data-stu-id="fda65-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fda65-117">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="fda65-117">Details</span></span>  
  
|<span data-ttu-id="fda65-118">Veri öğesi adı</span><span class="sxs-lookup"><span data-stu-id="fda65-118">Data Item Name</span></span>|<span data-ttu-id="fda65-119">Veri öğesi türü</span><span class="sxs-lookup"><span data-stu-id="fda65-119">Data Item Type</span></span>|<span data-ttu-id="fda65-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="fda65-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fda65-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="fda65-121">ParentActivity</span></span>|<span data-ttu-id="fda65-122">xs: String</span><span class="sxs-lookup"><span data-stu-id="fda65-122">xs:string</span></span>|<span data-ttu-id="fda65-123">Üst etkinlik türü adı.</span><span class="sxs-lookup"><span data-stu-id="fda65-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="fda65-124">Ana görüntü adı</span><span class="sxs-lookup"><span data-stu-id="fda65-124">ParentDisplayName</span></span>|<span data-ttu-id="fda65-125">xs: String</span><span class="sxs-lookup"><span data-stu-id="fda65-125">xs:string</span></span>|<span data-ttu-id="fda65-126">Üst etkinliğin görünen adı.</span><span class="sxs-lookup"><span data-stu-id="fda65-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="fda65-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="fda65-127">ParentInstanceId</span></span>|<span data-ttu-id="fda65-128">xs: String</span><span class="sxs-lookup"><span data-stu-id="fda65-128">xs:string</span></span>|<span data-ttu-id="fda65-129">Üst etkinlik örnek kimliği.</span><span class="sxs-lookup"><span data-stu-id="fda65-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="fda65-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="fda65-130">CompletedActivity</span></span>|<span data-ttu-id="fda65-131">xs: String</span><span class="sxs-lookup"><span data-stu-id="fda65-131">xs:string</span></span>|<span data-ttu-id="fda65-132">Tamamlanan etkinliğin türü adı.</span><span class="sxs-lookup"><span data-stu-id="fda65-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="fda65-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="fda65-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="fda65-134">xs: String</span><span class="sxs-lookup"><span data-stu-id="fda65-134">xs:string</span></span>|<span data-ttu-id="fda65-135">Tamamlanan etkinliğin görünen adı.</span><span class="sxs-lookup"><span data-stu-id="fda65-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="fda65-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="fda65-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="fda65-137">xs: String</span><span class="sxs-lookup"><span data-stu-id="fda65-137">xs:string</span></span>|<span data-ttu-id="fda65-138">Tamamlanan etkinliğin örnek kimliği.</span><span class="sxs-lookup"><span data-stu-id="fda65-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="fda65-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fda65-139">AppDomain</span></span>|<span data-ttu-id="fda65-140">xs: String</span><span class="sxs-lookup"><span data-stu-id="fda65-140">xs:string</span></span>|<span data-ttu-id="fda65-141">AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.</span><span class="sxs-lookup"><span data-stu-id="fda65-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|