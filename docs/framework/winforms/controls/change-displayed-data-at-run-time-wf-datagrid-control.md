---
title: "Nasıl yapılır: Windows Forms DataGrid Denetiminde Çalışma Zamanında Görüntülenen Verileri Değiştirme"
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
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45772035a7f2229ca0e0320ee9b65eb128c4fc32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Nasıl yapılır: Windows Forms DataGrid Denetiminde Çalışma Zamanında Görüntülenen Verileri Değiştirme
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> Denetimi değiştirir ve işlevlerini ekler <xref:System.Windows.Forms.DataGrid> kontrol; ancak, <xref:System.Windows.Forms.DataGrid> denetim tutulur geriye dönük uyumluluk ve gelecekte kullanım için seçerseniz. Daha fazla bilgi için bkz: [farklar arasında Windows Forms DataGridView ve DataGrid denetimleri](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Windows Forms oluşturduktan sonra <xref:System.Windows.Forms.DataGrid> tasarım-zamanı özellikleri kullanarak, ayrıca dinamik olarak öğeleri değiştirmek istediğiniz <xref:System.Data.DataSet> kılavuza çalışma zamanında nesne. Bu tablonun ya da tek tek değerlerine değişiklikleri içerebilir veya hangi veri kaynağını değiştirme bağlı <xref:System.Windows.Forms.DataGrid> denetim. Değerlerini ayrı ayrı yapılan değişiklikler aracılığıyla yapılır <xref:System.Data.DataSet> nesnesi değil, <xref:System.Windows.Forms.DataGrid> denetim.  
  
### <a name="to-change-data-programmatically"></a>Verileri programlı olarak değiştirmek için  
  
1.  İstenen tablosundan belirtin <xref:System.Data.DataSet> nesne ve istenen satır ve tablosundan alan ve hücre yeni değere eşit ayarlayın.  
  
    > [!NOTE]
    >  İlk tablonun belirtmek için <xref:System.Data.DataSet> veya tablonun ilk satırını 0 kullanın.  
  
     Aşağıdaki örnek, bir veri kümesi ilk tablonun ilk satırının ikinci giriş tıklayarak değiştirmek gösterilmiştir `Button1`. <xref:System.Data.DataSet> (`ds`) Ve tablolar (`0` ve `1`) daha önce oluşturulmuş.  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:   
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Formun oluşturucuda olay işleyicisi kaydetmek için aşağıdaki kodu yerleştirin.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Çalışma zamanında kullanabileceğiniz <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> bağlamak için yöntemi <xref:System.Windows.Forms.DataGrid> denetlemek için farklı bir veri kaynağı. Örneğin, birkaç olabilir [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] veri denetimleri, her bağlı farklı bir veritabanına.  
  
### <a name="to-change-the-datasource-programmatically"></a>Veri kaynağı programlı olarak değiştirmek için  
  
1.  Ayarlama <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> veri kaynağı ve bağlamak istediğiniz tablo adını yöntemi.  
  
     Aşağıdaki örnek değişiklik tarihi kaynağı kullanma gösterilmektedir <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> yönteme bir [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Pubs veritabanındaki yazarlar tabloya bağlı veri denetimi (adoPubsAuthors).  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ADO.NET veri kümeleri](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 [Nasıl yapılır: sütunları silme veya gizleme Windows Forms DataGrid denetimi](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [Nasıl yapılır: tabloları ekleyebilir ve sütunları Windows Forms DataGrid denetimi](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [Nasıl yapılır: Windows Forms DataGrid denetimini veri kaynağına bağlama](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
