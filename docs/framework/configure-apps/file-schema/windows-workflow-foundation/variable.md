---
title: "&lt;değişken&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3db57b3332638092fc9f16de5199b65c4efafebd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltvariablegt"></a><span data-ttu-id="6e41d-102">&lt;değişken&gt;</span><span class="sxs-lookup"><span data-stu-id="6e41d-102">&lt;variable&gt;</span></span>
<span data-ttu-id="6e41d-103">Bu etkinlik sorguyla ilişkilendirilen değişkeni koleksiyonunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="6e41d-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="6e41d-104">Profil sorguları izleme ile ilgili daha fazla bilgi için bkz: [izleme profilleri](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6e41d-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="6e41d-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6e41d-105">\<system.serviceModel></span></span>  
<span data-ttu-id="6e41d-106">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="6e41d-106">\<tracking></span></span>  
<span data-ttu-id="6e41d-107">\<profilleri ></span><span class="sxs-lookup"><span data-stu-id="6e41d-107">\<profiles></span></span>  
<span data-ttu-id="6e41d-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6e41d-108">\<trackingProfile></span></span>  
<span data-ttu-id="6e41d-109">\<İş akışı ></span><span class="sxs-lookup"><span data-stu-id="6e41d-109">\<workflow></span></span>  
<span data-ttu-id="6e41d-110">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="6e41d-110">\<activityStateQueries></span></span>  
<span data-ttu-id="6e41d-111">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="6e41d-111">\<activityStateQuery></span></span>  
<span data-ttu-id="6e41d-112">\<değişkenleri ></span><span class="sxs-lookup"><span data-stu-id="6e41d-112">\<variables></span></span>  
<span data-ttu-id="6e41d-113">\<değişken ></span><span class="sxs-lookup"><span data-stu-id="6e41d-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e41d-114">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6e41d-114">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e41d-115">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="6e41d-115">Attributes and Elements</span></span>  
 <span data-ttu-id="6e41d-116">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="6e41d-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e41d-117">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="6e41d-117">Attributes</span></span>  
  
|<span data-ttu-id="6e41d-118">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="6e41d-118">Attribute</span></span>|<span data-ttu-id="6e41d-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6e41d-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e41d-120">name</span><span class="sxs-lookup"><span data-stu-id="6e41d-120">name</span></span>|<span data-ttu-id="6e41d-121">Değişkenin adını belirten dize.</span><span class="sxs-lookup"><span data-stu-id="6e41d-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e41d-122">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="6e41d-122">Child Elements</span></span>  
 <span data-ttu-id="6e41d-123">Yok.</span><span class="sxs-lookup"><span data-stu-id="6e41d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e41d-124">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="6e41d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6e41d-125">Öğe</span><span class="sxs-lookup"><span data-stu-id="6e41d-125">Element</span></span>|<span data-ttu-id="6e41d-126">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6e41d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e41d-127">\<değişken ></span><span class="sxs-lookup"><span data-stu-id="6e41d-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="6e41d-128">Bir etkinlik durumu sorgusu ile ilişkili bir değişkeni.</span><span class="sxs-lookup"><span data-stu-id="6e41d-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e41d-129">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6e41d-129">Remarks</span></span>  
 <span data-ttu-id="6e41d-130">Bir benzersiz bir ActivityStateQuery bir iş akışının yürütülmesini izlerken veri çıkarma özelliğidir.</span><span class="sxs-lookup"><span data-stu-id="6e41d-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="6e41d-131">İzleme erişme post kaydettiğinde bu yürütme ek bağlam sağlar.</span><span class="sxs-lookup"><span data-stu-id="6e41d-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="6e41d-132">Kullanabileceğiniz [ \<bağımsız değişkenleri >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<durumları >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) ve [ \<durumları >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) herhangi bir değişken veya değişken ayıklamak için öğeleri bir iş akışındaki herhangi bir etkinlikten. Aşağıdaki örnek, değişkenler ve bağımsız değişkenler ayıklar bir etkinlik durumu sorgu gösterir, etkinliğin `Closed` izleme kaydı yayılan.</span><span class="sxs-lookup"><span data-stu-id="6e41d-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="6e41d-133">Değişkenleri ve bağımsız değişkenler ile yalnızca bir ActivityStateRecord ayıklanabilir ve bu nedenle bir izleme içinde abone olduğunuz kullanarak profil [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="6e41d-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6e41d-134">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6e41d-134">See Also</span></span>  
 <span data-ttu-id="6e41d-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6e41d-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="6e41d-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6e41d-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="6e41d-137">İzleme ve izleme iş akışı</span><span class="sxs-lookup"><span data-stu-id="6e41d-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="6e41d-138">Profillerini izleme</span><span class="sxs-lookup"><span data-stu-id="6e41d-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)