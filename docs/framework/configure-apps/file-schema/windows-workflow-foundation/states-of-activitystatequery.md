---
title: "&lt;durumları&gt; , &lt;activityStateQuery&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4ee98263f43d9557d0ee81484ff8550f0e927ca6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltstatesgt-of-ltactivitystatequerygt"></a><span data-ttu-id="bf4f5-102">&lt;durumları&gt; , &lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="bf4f5-102">&lt;states&gt; of &lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="bf4f5-103">Bir izleme kaydını yayınlaması gerektiğini abone etkinlik durumunu içeren yapılandırma öğeleri koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="bf4f5-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="bf4f5-104">Profil sorguları izleme ile ilgili daha fazla bilgi için bkz: [izleme profilleri](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="bf4f5-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="bf4f5-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="bf4f5-105">\<system.serviceModel></span></span>  
<span data-ttu-id="bf4f5-106">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="bf4f5-106">\<tracking></span></span>  
<span data-ttu-id="bf4f5-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="bf4f5-107">\<trackingProfile></span></span>  
<span data-ttu-id="bf4f5-108">\<İş akışı ></span><span class="sxs-lookup"><span data-stu-id="bf4f5-108">\<workflow></span></span>  
<span data-ttu-id="bf4f5-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="bf4f5-109">\<activityStateQueries></span></span>  
<span data-ttu-id="bf4f5-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="bf4f5-110">\<activityStateQuery></span></span>  
<span data-ttu-id="bf4f5-111">\<durumları ></span><span class="sxs-lookup"><span data-stu-id="bf4f5-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf4f5-112">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="bf4f5-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf4f5-113">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="bf4f5-113">Attributes and Elements</span></span>  
 <span data-ttu-id="bf4f5-114">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="bf4f5-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf4f5-115">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="bf4f5-115">Attributes</span></span>  
 <span data-ttu-id="bf4f5-116">Yok.</span><span class="sxs-lookup"><span data-stu-id="bf4f5-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bf4f5-117">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="bf4f5-117">Child Elements</span></span>  
  
|<span data-ttu-id="bf4f5-118">Öğe</span><span class="sxs-lookup"><span data-stu-id="bf4f5-118">Element</span></span>|<span data-ttu-id="bf4f5-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bf4f5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf4f5-120">\<durumu ></span><span class="sxs-lookup"><span data-stu-id="bf4f5-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|<span data-ttu-id="bf4f5-121">Bir izleme kaydını yayınlaması gerektiğini abone etkinlik durumunu içeren bir yapılandırma öğesi.</span><span class="sxs-lookup"><span data-stu-id="bf4f5-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf4f5-122">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="bf4f5-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bf4f5-123">Öğe</span><span class="sxs-lookup"><span data-stu-id="bf4f5-123">Element</span></span>|<span data-ttu-id="bf4f5-124">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bf4f5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf4f5-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="bf4f5-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="bf4f5-126">Üst etkinlik göre alt etkinlik iptal etme istekleri izlemek için kullanılan bir yapılandırma öğesi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="bf4f5-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="bf4f5-127">Sorgu isteği kaydı nesneleri iptal etmek için abone olmak izleme katılımcı için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="bf4f5-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf4f5-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bf4f5-128">Remarks</span></span>  
 <span data-ttu-id="bf4f5-129">Bir benzersiz bir ActivityStateQuery bir iş akışının yürütülmesini izlerken veri çıkarma özelliğidir.</span><span class="sxs-lookup"><span data-stu-id="bf4f5-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="bf4f5-130">İzleme erişme post kaydettiğinde bu yürütme ek bağlam sağlar.</span><span class="sxs-lookup"><span data-stu-id="bf4f5-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="bf4f5-131">Kullanabileceğiniz [ \<bağımsız değişkenleri >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<durumları >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) ve [ \<durumları >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) herhangi bir değişken veya değişken ayıklamak için öğeleri bir iş akışındaki herhangi bir etkinlikten. Aşağıdaki örnek, değişkenler ve bağımsız değişkenler ayıklar bir etkinlik durumu sorgu gösterir, etkinliğin `Closed` izleme kaydı yayılan.</span><span class="sxs-lookup"><span data-stu-id="bf4f5-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="bf4f5-132">Değişkenleri ve bağımsız değişkenler ile yalnızca bir ActivityStateRecord ayıklanabilir ve bu nedenle bir izleme içinde abone olduğunuz kullanarak profil [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="bf4f5-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf4f5-133">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bf4f5-133">See Also</span></span>  
 <span data-ttu-id="bf4f5-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bf4f5-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>      
 <span data-ttu-id="bf4f5-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bf4f5-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="bf4f5-136">İzleme ve izleme iş akışı</span><span class="sxs-lookup"><span data-stu-id="bf4f5-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="bf4f5-137">Profillerini izleme</span><span class="sxs-lookup"><span data-stu-id="bf4f5-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)