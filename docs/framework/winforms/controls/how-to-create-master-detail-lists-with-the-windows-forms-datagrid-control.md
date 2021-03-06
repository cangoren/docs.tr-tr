---
title: "Nasıl yapılır: Windows Forms DataGrid denetimi ile ana / ayrıntı listeleri oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63cb647e2ed6dcbc97fab15db3166b55c52f635a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Nasıl yapılır: Windows Forms DataGrid Denetimi ile Ana/Ayrıntı Listeleri Oluşturma
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> Denetimi değiştirir ve işlevlerini ekler <xref:System.Windows.Forms.DataGrid> kontrol; ancak, <xref:System.Windows.Forms.DataGrid> denetim tutulur geriye dönük uyumluluk ve gelecekte kullanım için seçerseniz. Daha fazla bilgi için bkz: [farklar arasında Windows Forms DataGridView ve DataGrid denetimleri](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Varsa, <xref:System.Data.DataSet> bir dizi içerir ilgili tabloları, iki kullanabilirsiniz <xref:System.Windows.Forms.DataGrid> verileri ana/ayrıntı biçimde görüntülemek için kontrol eder. Bir <xref:System.Windows.Forms.DataGrid> ana kılavuz olarak atanan ve ikinci ayrıntıları kılavuz olarak atanan. Ana listesinde bir girişi seçtiğinizde, tüm ilgili alt girdilerini ayrıntıları listesinde gösterilir. Örneğin, varsa, <xref:System.Data.DataSet> Müşteriler tablosu ile ilgili Siparişler tablosu içeren ana kılavuz olarak Müşteriler tablosu ve ayrıntıları kılavuz olarak Siparişler tablosundaki belirtmeniz gerekir. Bir müşteri Ana kılavuzdan seçildiğinde, o müşteri Siparişler tablosundaki ilişkili siparişleri tümünün Ayrıntılar kılavuzunda görüntülenir.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>Ana/ayrıntı ilişkisi programlı olarak ayarlamak için  
  
1.  İki yeni oluşturmak <xref:System.Windows.Forms.DataGrid> denetler ve bunların özelliklerini ayarlayın.  
  
2.  Tabloları kümesine ekleyin.  
  
3.  Türünde bir değişken bildirme <xref:System.Data.DataRelation> oluşturmak istiyorsanız ilişki temsil etmek için.  
  
4.  İlişki için bir ad belirtmek ve tablo, sütun ve iki tablo tie öğesi belirterek ilişki örneği oluşturur.  
  
5.  İlişkinin eklemek <xref:System.Data.DataSet> nesnenin <xref:System.Data.DataSet.Relations%2A> koleksiyonu.  
  
6.  Kullanım <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> yöntemi <xref:System.Windows.Forms.DataGrid> her biri için kılavuzları bağlamak için <xref:System.Data.DataSet>.  
  
     Aşağıdaki örnek, müşteriler ve siparişler tablolar arasında daha önce oluşturulan bir ana öğe/ayrıntı ilişkisi gösterilmiştir <xref:System.Data.DataSet> (`ds`).  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DataGrid denetimi](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [DataGrid denetimine genel bakış](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Nasıl yapılır: Windows Forms DataGrid denetimini veri kaynağına bağlama](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
