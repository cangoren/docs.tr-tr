---
title: "Yöntem temelli sorgu sözdizimi örnekler: Birleştirme (LINQ-DataSet)"
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
ms.assetid: 4fd5ed2c-b03a-4054-a3ed-3ddb380d7d9d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b1f32c5fcedf9bd11e44cb9c8d6e6dddf205b865
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="method-based-query-syntax-examples-join-linq-to-dataset"></a>Yöntem temelli sorgu sözdizimi örnekler: Birleştirme (LINQ-DataSet)
Birleştirme, birbirlerine, gezinebilir hiçbir ilişki ilişkisel veritabanı tabloları gibi sahip veri kaynaklarına hedef sorgularda önemli bir işlemdir. İki veri kaynaklarının bir birleştirme nesnelerin bir veri kaynağının diğer veri kaynağındaki ortak bir özniteliği paylaşan nesnelerle ilişkidir. Daha fazla bilgi için bkz: [standart sorgu işleçlerine genel bakış](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
 Bu konudaki örnekler nasıl kullanılacağını gösteren <xref:System.Linq.Enumerable.Join%2A> sorgu yönteme bir <xref:System.Data.DataSet> yöntemi sorgu sözdizimini kullanarak.  
  
 `FillDataSet` Bu örneklerde kullanılan yöntemi belirtilen [yüklenirken veri içine bir veri kümesi](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 Bu konudaki örnekler kişi, adres, ürün, SalesOrderHeader ve satış siparişi ayrıntısını tablolarını AdventureWorks örnek veritabanını kullanın.  
  
 Aşağıdaki örneklerde bu konudaki `using` / `Imports` deyimleri:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: bir LINQ to Visual Studio'da DataSet projesi oluşturma](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="join"></a>Birleştirme  
  
### <a name="example"></a>Örnek  
 Bu örnek üzerinde birleştirme gerçekleştirir `Contact` ve `SalesOrderHeader` tabloları.  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a>Örnek  
 Bu örnek üzerinde birleştirme gerçekleştirir `Contact` ve `SalesOrderHeader` sonuçlarına göre gruplandırma tabloları başvurun kimliği.  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir veri kümesine veri yükleme](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [LINQ-DataSet örnekleri](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [Standart sorgu işleçlerine genel bakış](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 [Örnekleri katılma](http://go.microsoft.com/fwlink/?LinkId=187357)  
 [Veri kümesi örnekleri](http://go.microsoft.com/fwlink/?LinkId=187358)
