---
title: "Nasıl yapılır: Uzaktan Yazıcıların Durumunu Araştırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ad824a1cef637edc99e6aaafc99d557167ea1f1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a><span data-ttu-id="7d217-102">Nasıl yapılır: Uzaktan Yazıcıların Durumunu Araştırma</span><span class="sxs-lookup"><span data-stu-id="7d217-102">How to: Remotely Survey the Status of Printers</span></span>
<span data-ttu-id="7d217-103">Orta ve büyük şirketlerin belirli bir zamanda adresindeki kağıt sıkışması veya kağıt veya bazı sorunlu durumlar dışında olan birden çok yazıcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="7d217-103">At any given time at medium and large companies there may be multiple printers that are not working due to a paper jam or being out of paper or some other problematic situation.</span></span> <span data-ttu-id="7d217-104">Yazıcı özellikleri de sağlanmaktadır zengin [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] , [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] yazıcıların durumlarının hızlı araştırmasını gerçekleştirmek için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="7d217-104">The rich set of printer properties exposed in the [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] of [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] provide a means for performing a rapid survey of the states of printers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d217-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="7d217-105">Example</span></span>  
 <span data-ttu-id="7d217-106">Bu tür bir yardımcı programı oluşturmak için önemli adımlar aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="7d217-106">The major steps for creating this kind of utility are as follows.</span></span>  
  
1.  <span data-ttu-id="7d217-107">Tüm yazdırma sunucularının bir listesini alın.</span><span class="sxs-lookup"><span data-stu-id="7d217-107">Obtain a list of all print servers.</span></span>  
  
2.  <span data-ttu-id="7d217-108">Kendi yazdırma sorgulamak için sunucular üzerinden döngü.</span><span class="sxs-lookup"><span data-stu-id="7d217-108">Loop through the servers to query their print queues.</span></span>  
  
3.  <span data-ttu-id="7d217-109">Sunucu döngüsünün her geçişinde sunucunun tüm kuyruklar üzerinden döngü ve sıranın şu an çalışmadığını gösterebilir her bir özellik okuyun.</span><span class="sxs-lookup"><span data-stu-id="7d217-109">Within each pass of the server loop, loop through all the server's queues and read each property that might indicate that the queue is not currently working.</span></span>  
  
 <span data-ttu-id="7d217-110">Aşağıdaki kod parçacıkları dizisidir.</span><span class="sxs-lookup"><span data-stu-id="7d217-110">The code below is a series of snippets.</span></span> <span data-ttu-id="7d217-111">Kolaylık sağlamak için bu örnek, yazdırma sunucularını CRLF ayrılmış bir listesi olduğunu varsayar.</span><span class="sxs-lookup"><span data-stu-id="7d217-111">For simplicity, this example assumes that there is a CRLF-delimited list of print servers.</span></span> <span data-ttu-id="7d217-112">Değişkeni `fileOfPrintServers` olan bir <xref:System.IO.StreamReader> bu dosya için nesne.</span><span class="sxs-lookup"><span data-stu-id="7d217-112">The variable `fileOfPrintServers` is a <xref:System.IO.StreamReader> object for this file.</span></span> <span data-ttu-id="7d217-113">Her sunucu adı kendi satırında olduğundan herhangi çağrısı <xref:System.IO.StreamReader.ReadLine%2A> sonraki sunucunun adını alır ve taşır <xref:System.IO.StreamReader>'s sonraki satırın başlangıcına imleç.</span><span class="sxs-lookup"><span data-stu-id="7d217-113">Since each server name is on its own line, any call of <xref:System.IO.StreamReader.ReadLine%2A> gets the name of the next server and moves the <xref:System.IO.StreamReader>'s cursor to the beginning of the next line.</span></span>  
  
 <span data-ttu-id="7d217-114">Dış döngü içinde kod oluşturur bir <xref:System.Printing.PrintServer> nesne için en son yazdırma sunucusu ve uygulama sunucusu için yönetici haklarına sahip olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="7d217-114">Within the outer loop, the code creates a <xref:System.Printing.PrintServer> object for the latest print server and specifies that the application is to have administrative rights to the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d217-115">Çok sunucu varsa, kullanarak performansı artırabilirsiniz <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> yalnızca bulacağınızı gerek özellikleri başlatma oluşturucular.</span><span class="sxs-lookup"><span data-stu-id="7d217-115">If there are a lot of servers, you can improve performance by using the <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructors that only initialize the properties you are going to need.</span></span>  
  
 <span data-ttu-id="7d217-116">Bu örnek daha sonra kullanır <xref:System.Printing.PrintServer.GetPrintQueues%2A> tüm sunucuların bir koleksiyonunu oluşturmak üzere sıraya koyar ve bunlar üzerinde döngü başlar kullanıcının.</span><span class="sxs-lookup"><span data-stu-id="7d217-116">The example then uses <xref:System.Printing.PrintServer.GetPrintQueues%2A> to create a collection of all of the server's queues and begins to loop through them.</span></span> <span data-ttu-id="7d217-117">İçteki döngü bir yazıcının durumunu denetleme iki yolla karşılık gelen bir dallanma yapısını içerir:</span><span class="sxs-lookup"><span data-stu-id="7d217-117">This inner loop contains a branching structure corresponding to the two ways of checking a printer's status:</span></span>  
  
-   <span data-ttu-id="7d217-118">Bayraklarını okuyabilirsiniz <xref:System.Printing.PrintQueue.QueueStatus%2A> türü olan özelliği <xref:System.Printing.PrintQueueStatus>.</span><span class="sxs-lookup"><span data-stu-id="7d217-118">You can read the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property which is of type <xref:System.Printing.PrintQueueStatus>.</span></span>  
  
-   <span data-ttu-id="7d217-119">İlgili her özelliği gibi okuyabilirsiniz <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, ve <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d217-119">You can read each relevant property such as <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, and <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span></span>  
  
 <span data-ttu-id="7d217-120">Bu örnekte, her iki yöntem gösterir, böylece kullanıcının daha önce hangi metodu istenir ve çözemiyorsa bayraklarını kullanmak isterse "y" yanıt <xref:System.Printing.PrintQueue.QueueStatus%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="7d217-120">This example demonstrates both methods, so the user was previously prompted as to which method to use and responded with "y" if he or she wanted to use the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property.</span></span> <span data-ttu-id="7d217-121">Aşağıda iki yöntem Ayrıntılar için bkz.</span><span class="sxs-lookup"><span data-stu-id="7d217-121">See below for the details of the two methods.</span></span>  
  
 <span data-ttu-id="7d217-122">Son olarak, sonuçların kullanıcıya sunulur.</span><span class="sxs-lookup"><span data-stu-id="7d217-122">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <span data-ttu-id="7d217-123">Bayraklarını kullanarak yazıcı durumunu denetlemek için <xref:System.Printing.PrintQueue.QueueStatus%2A> özelliği ayarlanmış olup olmadığını görmek için ilgili her bayrağı denetleyin.</span><span class="sxs-lookup"><span data-stu-id="7d217-123">To check printer status using the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property, you check each relevant flag to see if it is set.</span></span> <span data-ttu-id="7d217-124">Bir bit bit bayrakları kümesinde ayarlanmış olup olmadığını görmek için standart bir mantıksal ve işlem bayrakları kümesiyle olarak bir işlenen ve diğer bayrağı kendisini gerçekleştirmek için yoludur.</span><span class="sxs-lookup"><span data-stu-id="7d217-124">The standard way to see if one bit is set in a set of bit flags is to perform a logical AND operation with the set of flags as one operand and the flag itself as the other.</span></span> <span data-ttu-id="7d217-125">En fazla bayrağı ayarlayın, mantıksal sonucu yalnızca bir bit varsa ve bu yana o aynı bit ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="7d217-125">Since the flag itself has only one bit set, the result of the logical AND is that, at most, that same bit is set.</span></span> <span data-ttu-id="7d217-126">Bunu veya olup olmadığını öğrenmek için yalnızca mantıksal ve bayrağı sonucu karşılaştırın.</span><span class="sxs-lookup"><span data-stu-id="7d217-126">To find out whether it is or not, just compare the result of the logical AND with the flag itself.</span></span> <span data-ttu-id="7d217-127">Daha fazla bilgi için bkz: <xref:System.Printing.PrintQueueStatus>, [& işleci (C# Başvurusu)](~/docs/csharp/language-reference/operators/and-operator.md), ve <xref:System.FlagsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7d217-127">For more information, see <xref:System.Printing.PrintQueueStatus>, the [& Operator (C# Reference)](~/docs/csharp/language-reference/operators/and-operator.md), and <xref:System.FlagsAttribute>.</span></span>  
  
 <span data-ttu-id="7d217-128">Biti ayarlanmış olan her özniteliği için kod kullanıcıya sunulan son rapora bir bildirim ekler.</span><span class="sxs-lookup"><span data-stu-id="7d217-128">For each attribute whose bit is set, the code adds a notice to the final report that will be presented to the user.</span></span> <span data-ttu-id="7d217-129">( **ReportAvailabilityAtThisTime** kodu sonunda çağrılan yöntem aşağıda ele alınmıştır.)</span><span class="sxs-lookup"><span data-stu-id="7d217-129">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 <span data-ttu-id="7d217-130">Her bir özellik kullanarak yazıcı durumunu denetlemek için yalnızca her özelliği okuyun ve Not özelliği olan ise, kullanıcıya sunulan son rapora eklemek `true`.</span><span class="sxs-lookup"><span data-stu-id="7d217-130">To check printer status using each property, you simply read each property and add a note to the final report that will be presented to the user if the property is `true`.</span></span> <span data-ttu-id="7d217-131">( **ReportAvailabilityAtThisTime** kodu sonunda çağrılan yöntem aşağıda ele alınmıştır.)</span><span class="sxs-lookup"><span data-stu-id="7d217-131">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 <span data-ttu-id="7d217-132">**ReportAvailabilityAtThisTime** yöntemi oluşturuldu durumunda günün geçerli saatinde sıranın kullanılabilir olup olmadığını belirlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="7d217-132">The **ReportAvailabilityAtThisTime** method was created in case you need to determine if the queue is available at the current time of day.</span></span>  
  
 <span data-ttu-id="7d217-133">Yöntemi, hiçbir şey yapmaz varsa <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> ve <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> özelliklerdir eşit; bu durumda yazıcı her zaman kullanılabilir olduğundan.</span><span class="sxs-lookup"><span data-stu-id="7d217-133">The method will do nothing if the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are equal; because in that case the printer is available at all times.</span></span> <span data-ttu-id="7d217-134">Bunlar farklıysa, çünkü toplam dakika son gece dönüştürülecek olan geçerli saati yöntemi alır <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> ve <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> özellikleri <xref:System.Int32>dakika sonra-dönüştürmemiz, temsil eden değil s <xref:System.DateTime> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="7d217-134">If they are different, the method gets the current time which then has to be converted into total minutes past midnight because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are <xref:System.Int32>s representing minutes-after-midnight, not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="7d217-135">Son olarak, geçerli saati "kadar" kez başlangıç arasında olup olmadığını görmek için yöntem denetler.</span><span class="sxs-lookup"><span data-stu-id="7d217-135">Finally, the method checks to see if the current time is between the start and "until" times.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a><span data-ttu-id="7d217-136">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7d217-136">See Also</span></span>  
 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>  
 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>  
 <xref:System.DateTime>  
 <xref:System.Printing.PrintQueueStatus>  
 <xref:System.FlagsAttribute>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 [<span data-ttu-id="7d217-137">& İşleci (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="7d217-137">& Operator (C# Reference)</span></span>](~/docs/csharp/language-reference/operators/and-operator.md)  
 [<span data-ttu-id="7d217-138">WPF belgeleri</span><span class="sxs-lookup"><span data-stu-id="7d217-138">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="7d217-139">Yazdırma genel bakış</span><span class="sxs-lookup"><span data-stu-id="7d217-139">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)