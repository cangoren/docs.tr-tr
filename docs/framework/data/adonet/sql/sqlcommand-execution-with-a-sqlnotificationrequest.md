---
title: "Bir SqlNotificationRequest ile SqlCommand yürütme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1776f48f-9bea-41f6-83a4-c990c7a2c991
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fdd76820ee0758492fab1364c7561920c549a412
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="sqlcommand-execution-with-a-sqlnotificationrequest"></a><span data-ttu-id="e78b7-102">Bir SqlNotificationRequest ile SqlCommand yürütme</span><span class="sxs-lookup"><span data-stu-id="e78b7-102">SqlCommand Execution with a SqlNotificationRequest</span></span>
<span data-ttu-id="e78b7-103">A <xref:System.Data.SqlClient.SqlCommand> veri sunucudan alınan sonra sonuç kümesi sorguyu yeniden yürütüldü farklı olacaktır değiştiğinde bildirim oluşturmak için yapılandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="e78b7-103">A <xref:System.Data.SqlClient.SqlCommand> can be configured to generate a notification when data changes after it has been fetched from the server and the result set would be different if the query were executed again.</span></span> <span data-ttu-id="e78b7-104">Bu özel bildirim sırası sunucuda veya dinamik nesneler korumak istemediğiniz zaman kullanmak istediğiniz senaryolar için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="e78b7-104">This is useful for scenarios where you want to use custom notification queues on the server or when you do not want to maintain live objects.</span></span>  
  
## <a name="creating-the-notification-request"></a><span data-ttu-id="e78b7-105">Bildirim isteği oluşturma</span><span class="sxs-lookup"><span data-stu-id="e78b7-105">Creating the Notification Request</span></span>  
 <span data-ttu-id="e78b7-106">Kullanabileceğiniz bir <xref:System.Data.Sql.SqlNotificationRequest> bağlama tarafından bildirim isteği oluşturmak için nesnesi bir `SqlCommand` nesnesi.</span><span class="sxs-lookup"><span data-stu-id="e78b7-106">You can use a <xref:System.Data.Sql.SqlNotificationRequest> object to create the notification request by binding it to a `SqlCommand` object.</span></span> <span data-ttu-id="e78b7-107">İstek oluşturulduktan sonra artık ihtiyaç duymadığınız `SqlNotificationRequest` nesnesi.</span><span class="sxs-lookup"><span data-stu-id="e78b7-107">Once the request is created, you no longer need the `SqlNotificationRequest` object.</span></span> <span data-ttu-id="e78b7-108">Sıra herhangi bir bildirim için sorgu ve uygun şekilde yanıt.</span><span class="sxs-lookup"><span data-stu-id="e78b7-108">You can query the queue for any notifications and respond appropriately.</span></span> <span data-ttu-id="e78b7-109">Uygulama kapatılır ve daha sonra yeniden olsa bile bildirimleri ortaya çıkabilir.</span><span class="sxs-lookup"><span data-stu-id="e78b7-109">Notifications can occur even if the application is shut down and subsequently restarted.</span></span>  
  
 <span data-ttu-id="e78b7-110">İlişkili bildirim komutuyla yürütüldüğünde, özgün sonucu herhangi bir değişiklik bildirim istekte yapılandırılan SQL Server kuyruğa ileti gönderme tetikleyici ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="e78b7-110">When the command with the associated notification is executed, any changes to the original result set trigger sending a message to the SQL Server queue that was configured in the notification request.</span></span>  
  
 <span data-ttu-id="e78b7-111">SQL Server sıranın yoklamak ve iletiyi yorumlayamadı nasıl uygulamanıza özeldir.</span><span class="sxs-lookup"><span data-stu-id="e78b7-111">How you poll the SQL Server queue and interpret the message is specific to your application.</span></span> <span data-ttu-id="e78b7-112">Uygulama sıra yoklama için sorumludur ve tepki ileti içeriğine bağlı.</span><span class="sxs-lookup"><span data-stu-id="e78b7-112">The application is responsible for polling the queue and reacting based on the contents of the message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e78b7-113">SQL Server bildirim istekleriyle kullanırken <xref:System.Data.SqlClient.SqlDependency>, varsayılan hizmet adı kullanmak yerine, kendi sıra adı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="e78b7-113">When using SQL Server notification requests with <xref:System.Data.SqlClient.SqlDependency>, create your own queue name instead of using the default service name.</span></span>  
  
 <span data-ttu-id="e78b7-114">Yeni istemci-tarafı güvenlik öğe için <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="e78b7-114">There are no new client-side security elements for <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="e78b7-115">Bu birincil bir sunucu özelliğidir ve sunucunun kullanıcıları bir bildirim istemek zorunda özel ayrıcalıklar oluşturdu.</span><span class="sxs-lookup"><span data-stu-id="e78b7-115">This is primarily a server feature, and the server has created special privileges that users must have to request a notification.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e78b7-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="e78b7-116">Example</span></span>  
 <span data-ttu-id="e78b7-117">Aşağıdaki kod parçası nasıl oluşturulduğunu gösteren bir <xref:System.Data.Sql.SqlNotificationRequest> ve bu ilişkilendirmeyi bir <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="e78b7-117">The following code fragment demonstrates how to create a <xref:System.Data.Sql.SqlNotificationRequest> and associate it with a <xref:System.Data.SqlClient.SqlCommand>.</span></span>  
  
```vb  
' Assume connection is an open SqlConnection.  
' Create a new SqlCommand object.  
Dim command As New SqlCommand( _  
  "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection)  
  
' Create a SqlNotificationRequest object.  
Dim notficationRequest As New SqlNotificationRequest()  
notficationRequest.id = "NotificationID"  
notficationRequest.Service = "mySSBQueue"  
  
' Associate the notification request with the command.  
command.Notification = notficationRequest  
' Execute the command.  
command.ExecuteReader()  
' Process the DataReader.  
' You can use Transact-SQL syntax to periodically poll the   
' SQL Server queue to see if you have a new message.  
```  
  
```csharp  
// Assume connection is an open SqlConnection.  
// Create a new SqlCommand object.  
SqlCommand command=new SqlCommand(  
 "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection);  
  
// Create a SqlNotificationRequest object.  
SqlNotificationRequest notficationRequest=new SqlNotificationRequest();  
notficationRequest.id="NotificationID";  
notficationRequest.Service="mySSBQueue";  
  
// Associate the notification request with the command.  
command.Notification=notficationRequest;  
// Execute the command.  
command.ExecuteReader();  
// Process the DataReader.  
// You can use Transact-SQL syntax to periodically poll the   
// SQL Server queue to see if you have a new message.  
```  
  
## <a name="see-also"></a><span data-ttu-id="e78b7-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e78b7-118">See Also</span></span>  
 [<span data-ttu-id="e78b7-119">SQL Server'da sorgu bildirimleri</span><span class="sxs-lookup"><span data-stu-id="e78b7-119">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="e78b7-120">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="e78b7-120">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)