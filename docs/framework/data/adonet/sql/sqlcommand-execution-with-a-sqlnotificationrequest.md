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
# <a name="sqlcommand-execution-with-a-sqlnotificationrequest"></a>Bir SqlNotificationRequest ile SqlCommand yürütme
A <xref:System.Data.SqlClient.SqlCommand> veri sunucudan alınan sonra sonuç kümesi sorguyu yeniden yürütüldü farklı olacaktır değiştiğinde bildirim oluşturmak için yapılandırılabilir. Bu özel bildirim sırası sunucuda veya dinamik nesneler korumak istemediğiniz zaman kullanmak istediğiniz senaryolar için kullanışlıdır.  
  
## <a name="creating-the-notification-request"></a>Bildirim isteği oluşturma  
 Kullanabileceğiniz bir <xref:System.Data.Sql.SqlNotificationRequest> bağlama tarafından bildirim isteği oluşturmak için nesnesi bir `SqlCommand` nesnesi. İstek oluşturulduktan sonra artık ihtiyaç duymadığınız `SqlNotificationRequest` nesnesi. Sıra herhangi bir bildirim için sorgu ve uygun şekilde yanıt. Uygulama kapatılır ve daha sonra yeniden olsa bile bildirimleri ortaya çıkabilir.  
  
 İlişkili bildirim komutuyla yürütüldüğünde, özgün sonucu herhangi bir değişiklik bildirim istekte yapılandırılan SQL Server kuyruğa ileti gönderme tetikleyici ayarlayın.  
  
 SQL Server sıranın yoklamak ve iletiyi yorumlayamadı nasıl uygulamanıza özeldir. Uygulama sıra yoklama için sorumludur ve tepki ileti içeriğine bağlı.  
  
> [!NOTE]
>  SQL Server bildirim istekleriyle kullanırken <xref:System.Data.SqlClient.SqlDependency>, varsayılan hizmet adı kullanmak yerine, kendi sıra adı oluşturun.  
  
 Yeni istemci-tarafı güvenlik öğe için <xref:System.Data.Sql.SqlNotificationRequest>. Bu birincil bir sunucu özelliğidir ve sunucunun kullanıcıları bir bildirim istemek zorunda özel ayrıcalıklar oluşturdu.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod parçası nasıl oluşturulduğunu gösteren bir <xref:System.Data.Sql.SqlNotificationRequest> ve bu ilişkilendirmeyi bir <xref:System.Data.SqlClient.SqlCommand>.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SQL Server'da sorgu bildirimleri](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=217917)
