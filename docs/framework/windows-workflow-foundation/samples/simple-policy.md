---
title: "Basit İlkesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0c704a9f3f27d63fb1a28db61f03cdc9b8de4370
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="simple-policy"></a><span data-ttu-id="c60ae-102">Basit İlkesi</span><span class="sxs-lookup"><span data-stu-id="c60ae-102">Simple Policy</span></span>
<span data-ttu-id="c60ae-103">Bu örnek nasıl kullanılacağını gösteren bir <xref:System.Workflow.Activities.PolicyActivity> bir iş akışı etkinlik.</span><span class="sxs-lookup"><span data-stu-id="c60ae-103">This sample shows how to use a <xref:System.Workflow.Activities.PolicyActivity> activity in a workflow.</span></span>  
  
 <span data-ttu-id="c60ae-104">Bu örnekte sıralı iş akışı kullanılarak oluşturulan bir <xref:System.Workflow.Activities.PolicyActivity> etkinlik.</span><span class="sxs-lookup"><span data-stu-id="c60ae-104">The sequential workflow in this sample is created by using a <xref:System.Workflow.Activities.PolicyActivity> activity.</span></span> <span data-ttu-id="c60ae-105">İş akışını tanımlayan `orderValue`, `customerType`, ve `discount` bir ürün tanımlamak için kullanılan alanları indirim iş akışı.</span><span class="sxs-lookup"><span data-stu-id="c60ae-105">The workflow defines `orderValue`, `customerType`, and `discount` fields that are used to define a product discount workflow.</span></span> <span data-ttu-id="c60ae-106">Kural dosyasında tanımlanan kurallar temel alır bir indirim değeri ayarlamak `orderValue` ve `customerType`.</span><span class="sxs-lookup"><span data-stu-id="c60ae-106">The rules defined in the rules file set a discount value that is based on the `orderValue` and `customerType`.</span></span> <span data-ttu-id="c60ae-107">`orderValue` Ve `customerType` ayarlanır `SimplePolicyWorkflow` sınıf tanımının ve davranışı değiştirmek için değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="c60ae-107">The `orderValue` and `customerType` are set in the `SimplePolicyWorkflow` class definition and can be changed to alter the behavior.</span></span> <span data-ttu-id="c60ae-108">Sonuçta elde edilen indirim konsolda yazılır <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> tanımlanan olay işleyicisi `SimplePolicyWorkflow` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="c60ae-108">The resulting discount is written to the console in the <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> event handler that is defined in the `SimplePolicyWorkflow` class.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="c60ae-109">Örneği oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="c60ae-109">To build the sample</span></span>  
  
1.  <span data-ttu-id="c60ae-110">Çözümde açmak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c60ae-110">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="c60ae-111">CTRL + SHIFT + B tuşlarına basarak çözümü oluşturun.</span><span class="sxs-lookup"><span data-stu-id="c60ae-111">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="c60ae-112">CTRL + F5'e basarak hata ayıklama olmadan çözümü çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="c60ae-112">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="c60ae-113">Örnek çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="c60ae-113">To run the sample</span></span>  
  
-   <span data-ttu-id="c60ae-114">Örnek için ana klasörü altında bulunan .exe dosyasını SimplePolicy\bin\debug klasöründe (veya örnek Visual Basic sürümü için SimplePolicy\bin klasör) SDK komut istemi penceresinde çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="c60ae-114">In the SDK Command Prompt window, run the .exe file in the SimplePolicy\bin\debug folder (or the SimplePolicy\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c60ae-115">Örnekler, bilgisayarınızda yüklü.</span><span class="sxs-lookup"><span data-stu-id="c60ae-115">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c60ae-116">Devam etmeden önce aşağıdaki (varsayılan) dizin denetle:</span><span class="sxs-lookup"><span data-stu-id="c60ae-116">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c60ae-117">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="c60ae-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c60ae-118">Bu örnek aşağıdaki dizinde bulunur:</span><span class="sxs-lookup"><span data-stu-id="c60ae-118">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a><span data-ttu-id="c60ae-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c60ae-119">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="c60ae-120">Gelişmiş İlkesi</span><span class="sxs-lookup"><span data-stu-id="c60ae-120">Advanced Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)