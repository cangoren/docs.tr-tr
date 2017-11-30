---
title: "Nasıl yapılır: DataGrid Denetiminde Verileri Gruplandırma, Sıralama ve Filtreleme"
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
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3c8afacfafbe14794bf17a4e9a4df7c175a3668
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a><span data-ttu-id="42c9b-102">Nasıl yapılır: DataGrid Denetiminde Verileri Gruplandırma, Sıralama ve Filtreleme</span><span class="sxs-lookup"><span data-stu-id="42c9b-102">How to: Group, Sort, and Filter Data in the DataGrid Control</span></span>
<span data-ttu-id="42c9b-103">Genellikle verileri görüntülemek için yararlı bir <xref:System.Windows.Controls.DataGrid> gruplandırma, sıralama ve verileri filtreleme, farklı şekillerde.</span><span class="sxs-lookup"><span data-stu-id="42c9b-103">It is often useful to view data in a <xref:System.Windows.Controls.DataGrid> in different ways by grouping, sorting, and filtering the data.</span></span> <span data-ttu-id="42c9b-104">Grup, sıralamak ve verileri filtrelemek için bir <xref:System.Windows.Controls.DataGrid>, onu bağladıktan bir <xref:System.Windows.Data.CollectionView> bu işlevleri destekleyen.</span><span class="sxs-lookup"><span data-stu-id="42c9b-104">To group, sort, and filter the data in a <xref:System.Windows.Controls.DataGrid>, you bind it to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="42c9b-105">Ardından verileri ile çalışabilirsiniz <xref:System.Windows.Data.CollectionView> temel alınan veri kaynağını etkilemeden.</span><span class="sxs-lookup"><span data-stu-id="42c9b-105">You can then work with the data in the <xref:System.Windows.Data.CollectionView> without affecting the underlying source data.</span></span> <span data-ttu-id="42c9b-106">Koleksiyon görünümü değişiklikleri yansıtılır <xref:System.Windows.Controls.DataGrid> kullanıcı arabirimi (UI).</span><span class="sxs-lookup"><span data-stu-id="42c9b-106">The changes in the collection view are reflected in the <xref:System.Windows.Controls.DataGrid> user interface (UI).</span></span>  
  
 <span data-ttu-id="42c9b-107"><xref:System.Windows.Data.CollectionView> SAX gruplandırma ve işlevselliği uygulayan bir veri kaynağı için sıralama <xref:System.Collections.IEnumerable> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="42c9b-107">The <xref:System.Windows.Data.CollectionView> class provides grouping and sorting functionality for a data source that implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="42c9b-108"><xref:System.Windows.Data.CollectionViewSource> Sınıf özelliklerini ayarlamanıza olanak sağlayan bir <xref:System.Windows.Data.CollectionView> XAML gelen.</span><span class="sxs-lookup"><span data-stu-id="42c9b-108">The <xref:System.Windows.Data.CollectionViewSource> class enables you to set the properties of a <xref:System.Windows.Data.CollectionView> from XAML.</span></span>  
  
 <span data-ttu-id="42c9b-109">Bu örnekte, bir koleksiyonu `Task` nesneleri bağlı bir <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="42c9b-109">In this example, a collection of `Task` objects is bound to a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="42c9b-110"><xref:System.Windows.Data.CollectionViewSource> Olarak kullanılan <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> için <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="42c9b-110">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="42c9b-111">Gruplandırma, sıralama ve filtreleme üzerinde gerçekleştirilir <xref:System.Windows.Data.CollectionViewSource> ve görüntülenen <xref:System.Windows.Controls.DataGrid> UI.</span><span class="sxs-lookup"><span data-stu-id="42c9b-111">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="42c9b-112">![Gruplandırılmış bir DataGrid verileri](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span><span class="sxs-lookup"><span data-stu-id="42c9b-112">![Grouped data in a DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span></span>  
<span data-ttu-id="42c9b-113">DataGrid içinde gruplandırılmış veri</span><span class="sxs-lookup"><span data-stu-id="42c9b-113">Grouped Data in a DataGrid</span></span>  
  
## <a name="using-a-collectionviewsource-as-an-itemssource"></a><span data-ttu-id="42c9b-114">Bir CollectionViewSource bir ItemsSource kullanma</span><span class="sxs-lookup"><span data-stu-id="42c9b-114">Using a CollectionViewSource as an ItemsSource</span></span>  
 <span data-ttu-id="42c9b-115">Grup, sıralama ve filtre verilerde bir <xref:System.Windows.Controls.DataGrid> denetimi bağlarsanız <xref:System.Windows.Controls.DataGrid> için bir <xref:System.Windows.Data.CollectionView> bu işlevleri destekleyen.</span><span class="sxs-lookup"><span data-stu-id="42c9b-115">To group, sort, and filter data in a <xref:System.Windows.Controls.DataGrid> control, you bind the <xref:System.Windows.Controls.DataGrid> to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="42c9b-116">Bu örnekte, <xref:System.Windows.Controls.DataGrid> bağlı bir <xref:System.Windows.Data.CollectionViewSource> için bu işlevler sağlayan bir <xref:System.Collections.Generic.List%601> , `Task` nesneleri.</span><span class="sxs-lookup"><span data-stu-id="42c9b-116">In this example, the <xref:System.Windows.Controls.DataGrid> is bound to a <xref:System.Windows.Data.CollectionViewSource> that provides these functions for a <xref:System.Collections.Generic.List%601> of `Task` objects.</span></span>  
  
#### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a><span data-ttu-id="42c9b-117">DataGrid bir CollectionViewSource bağlamak için</span><span class="sxs-lookup"><span data-stu-id="42c9b-117">To bind a DataGrid to a CollectionViewSource</span></span>  
  
1.  <span data-ttu-id="42c9b-118">Arabirimini uygulayan bir veri toplama oluşturma <xref:System.Collections.IEnumerable> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="42c9b-118">Create a data collection that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
     <span data-ttu-id="42c9b-119">Kullanırsanız <xref:System.Collections.Generic.List%601> koleksiyonunuzu oluşturmak için devraldığı yeni bir sınıf oluşturmalısınız <xref:System.Collections.Generic.List%601> örneği başlatmasını yerine <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="42c9b-119">If you use <xref:System.Collections.Generic.List%601> to create your collection, you should create a new class that inherits from <xref:System.Collections.Generic.List%601> instead of instantiating an instance of <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="42c9b-120">Bu, veri bağlamak için XAML koleksiyonunda sağlar.</span><span class="sxs-lookup"><span data-stu-id="42c9b-120">This enables you to data bind to the collection in XAML.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="42c9b-121">Koleksiyonundaki nesneleri uygulamalıdır <xref:System.ComponentModel.INotifyPropertyChanged> değiştirilen arabirimi ve <xref:System.ComponentModel.IEditableObject> arabirimi sırayla <xref:System.Windows.Controls.DataGrid> özellik değişikliklerini ve düzenlemeleri için doğru şekilde yanıt vermesi.</span><span class="sxs-lookup"><span data-stu-id="42c9b-121">The objects in the collection must implement the <xref:System.ComponentModel.INotifyPropertyChanged> changed interface and the <xref:System.ComponentModel.IEditableObject> interface in order for the <xref:System.Windows.Controls.DataGrid> to respond correctly to property changes and edits.</span></span> <span data-ttu-id="42c9b-122">Daha fazla bilgi için bkz: [uygulama özellik değişikliği bildirimi](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="42c9b-122">For more information, see [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
     [!code-vb[DataGrid_GroupSortFilter#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]  
  
2.  <span data-ttu-id="42c9b-123">XAML'de koleksiyonu sınıfının bir örneğini oluşturup [x: Key yönergesi](../../../../docs/framework/xaml-services/x-key-directive.md).</span><span class="sxs-lookup"><span data-stu-id="42c9b-123">In XAML, create an instance of the collection class and set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md).</span></span>  
  
3.  <span data-ttu-id="42c9b-124">XAML'de bir örneğini oluşturmak <xref:System.Windows.Data.CollectionViewSource> sınıfı, Ayarla [x: Key yönergesi](../../../../docs/framework/xaml-services/x-key-directive.md)ve koleksiyon sınıfınızın örneğini ayarlamak <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span><span class="sxs-lookup"><span data-stu-id="42c9b-124">In XAML, create an instance of the <xref:System.Windows.Data.CollectionViewSource> class, set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md), and set the instance of your collection class as the <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#201](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]  
  
4.  <span data-ttu-id="42c9b-125">Bir örneğini oluşturmak <xref:System.Windows.Controls.DataGrid> sınıfı ve ayarlayın <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> özelliğine <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="42c9b-125">Create an instance of the <xref:System.Windows.Controls.DataGrid> class, and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#002](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]  
  
5.  <span data-ttu-id="42c9b-126">Erişim için <xref:System.Windows.Data.CollectionViewSource> da kodunuzdan kullanmak <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> bir başvuru almak için yöntemi <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="42c9b-126">To access the <xref:System.Windows.Data.CollectionViewSource> from your code, use the <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> method to get a reference to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
     [!code-vb[DataGrid_GroupSortFilter#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]  
  
## <a name="grouping-items-in-a-datagrid"></a><span data-ttu-id="42c9b-127">DataGrid öğeleri gruplandırma</span><span class="sxs-lookup"><span data-stu-id="42c9b-127">Grouping items in a DataGrid</span></span>  
 <span data-ttu-id="42c9b-128">Öğeleri nasıl gruplandırılacağını belirlemek için bir <xref:System.Windows.Controls.DataGrid>, kullandığınız <xref:System.Windows.Data.PropertyGroupDescription> kaynağı görünümündeki öğeleri gruplandırmak için türü.</span><span class="sxs-lookup"><span data-stu-id="42c9b-128">To specify how items are grouped in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.Windows.Data.PropertyGroupDescription> type to group the items in the source view.</span></span>  
  
#### <a name="to-group-items-in-a-datagrid-using-xaml"></a><span data-ttu-id="42c9b-129">XAML kullanılarak DataGrid'de öğeleri gruplandırmak için</span><span class="sxs-lookup"><span data-stu-id="42c9b-129">To group items in a DataGrid using XAML</span></span>  
  
1.  <span data-ttu-id="42c9b-130">Oluşturma bir <xref:System.Windows.Data.PropertyGroupDescription> grupla özelliğine belirtir.</span><span class="sxs-lookup"><span data-stu-id="42c9b-130">Create a <xref:System.Windows.Data.PropertyGroupDescription> that specifies the property to group by.</span></span> <span data-ttu-id="42c9b-131">XAML veya kod özelliği belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="42c9b-131">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="42c9b-132">XAML'de ayarlamak <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> göre gruplamak için özellik adı.</span><span class="sxs-lookup"><span data-stu-id="42c9b-132">In XAML, set the <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> to the name of the property to group by.</span></span>  
  
    2.  <span data-ttu-id="42c9b-133">Kodda, özelliğin adını oluşturucusu tarafından grubuna geçirin.</span><span class="sxs-lookup"><span data-stu-id="42c9b-133">In code, pass the name of the property to group by to the constructor.</span></span>  
  
2.  <span data-ttu-id="42c9b-134">Ekleme <xref:System.Windows.Data.PropertyGroupDescription> için <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="42c9b-134">Add the <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="42c9b-135">Ek örneklerini eklemek <xref:System.Windows.Data.PropertyGroupDescription> için <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> daha fazla Gruplandırma düzeyleri eklemek için koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="42c9b-135">Add additional instances of <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection to add more levels of grouping.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#012](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#112](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
     [!code-vb[DataGrid_GroupSortFilter#112](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]  
  
4.  <span data-ttu-id="42c9b-136">Bir grubu kaldırmak için <xref:System.Windows.Data.PropertyGroupDescription> gelen <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="42c9b-136">To remove a group, remove the <xref:System.Windows.Data.PropertyGroupDescription> from the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
5.  <span data-ttu-id="42c9b-137">Tüm grupları kaldırmak için arama <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> yöntemi <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="42c9b-137">To remove all groups, call the <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> method of the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#114](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
     [!code-vb[DataGrid_GroupSortFilter#114](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]  
  
 <span data-ttu-id="42c9b-138">Ne zaman öğeleri gruplandırılır içinde <xref:System.Windows.Controls.DataGrid>, tanımlayabileceğiniz bir <xref:System.Windows.Controls.GroupStyle> her grubu görünümünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="42c9b-138">When items are grouped in the <xref:System.Windows.Controls.DataGrid>, you can define a <xref:System.Windows.Controls.GroupStyle> that specifies the appearance of each group.</span></span> <span data-ttu-id="42c9b-139">Uyguladığınız <xref:System.Windows.Controls.GroupStyle> ekleyerek <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> DataGrid koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="42c9b-139">You apply the <xref:System.Windows.Controls.GroupStyle> by adding it to the <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> collection of the DataGrid.</span></span> <span data-ttu-id="42c9b-140">Gruplandırma birden çok düzeyi varsa, her grup düzeyine farklı stilleri uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="42c9b-140">If you have multiple levels of grouping, you can apply different styles to each group level.</span></span> <span data-ttu-id="42c9b-141">Stilleri tanımlı sırayla uygulanır.</span><span class="sxs-lookup"><span data-stu-id="42c9b-141">Styles are applied in the order in which they are defined.</span></span> <span data-ttu-id="42c9b-142">Örneğin, iki stili tanımlarsanız, ilk üst düzey satır gruplarına uygulanır.</span><span class="sxs-lookup"><span data-stu-id="42c9b-142">For example, if you define two styles, the first will be applied to top level row groups.</span></span> <span data-ttu-id="42c9b-143">İkinci stili ikinci düzeyde tüm satır grupları uygulanan ve daha düşük olacaktır.</span><span class="sxs-lookup"><span data-stu-id="42c9b-143">The second style will be applied to all row groups at the second level and lower.</span></span> <span data-ttu-id="42c9b-144"><xref:System.Windows.FrameworkElement.DataContext%2A> , <xref:System.Windows.Controls.GroupStyle> Olan <xref:System.Windows.Data.CollectionViewGroup> grubu temsil eden.</span><span class="sxs-lookup"><span data-stu-id="42c9b-144">The <xref:System.Windows.FrameworkElement.DataContext%2A> of the <xref:System.Windows.Controls.GroupStyle> is the <xref:System.Windows.Data.CollectionViewGroup> that the group represents.</span></span>  
  
#### <a name="to-change-the-appearance-of-row-group-headers"></a><span data-ttu-id="42c9b-145">Satır grup üstbilgileri görünümünü değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="42c9b-145">To change the appearance of row group headers</span></span>  
  
1.  <span data-ttu-id="42c9b-146">Oluşturma bir <xref:System.Windows.Controls.GroupStyle> , satır grubu görünümünü tanımlar.</span><span class="sxs-lookup"><span data-stu-id="42c9b-146">Create a <xref:System.Windows.Controls.GroupStyle> that defines the appearance of the row group.</span></span>  
  
2.  <span data-ttu-id="42c9b-147">PUT <xref:System.Windows.Controls.GroupStyle> içinde `<DataGrid.GroupStyle>` etiketler.</span><span class="sxs-lookup"><span data-stu-id="42c9b-147">Put the <xref:System.Windows.Controls.GroupStyle> inside the `<DataGrid.GroupStyle>` tags.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#003](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]  
  
## <a name="sorting-items-in-a-datagrid"></a><span data-ttu-id="42c9b-148">DataGrid öğeleri sıralama</span><span class="sxs-lookup"><span data-stu-id="42c9b-148">Sorting items in a DataGrid</span></span>  
 <span data-ttu-id="42c9b-149">Öğeleri nasıl sıralanacağını belirtmek için bir <xref:System.Windows.Controls.DataGrid>, kullandığınız <xref:System.ComponentModel.SortDescription> kaynağı görünümündeki öğeleri sıralama türü.</span><span class="sxs-lookup"><span data-stu-id="42c9b-149">To specify how items are sorted in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.ComponentModel.SortDescription> type to sort the items in the source view.</span></span>  
  
#### <a name="to-sort-items-in-a-datagrid"></a><span data-ttu-id="42c9b-150">DataGrid içindeki öğeleri sıralamak için</span><span class="sxs-lookup"><span data-stu-id="42c9b-150">To sort items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="42c9b-151">Oluşturma bir <xref:System.ComponentModel.SortDescription> göre sıralamak için özelliğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="42c9b-151">Create a <xref:System.ComponentModel.SortDescription> that specifies the property to sort by.</span></span> <span data-ttu-id="42c9b-152">XAML veya kod özelliği belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="42c9b-152">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="42c9b-153">XAML'de ayarlamak <xref:System.ComponentModel.SortDescription.PropertyName%2A> göre sıralamak için özelliğinin adı.</span><span class="sxs-lookup"><span data-stu-id="42c9b-153">In XAML, set the <xref:System.ComponentModel.SortDescription.PropertyName%2A> to the name of the property to sort by.</span></span>  
  
    2.  <span data-ttu-id="42c9b-154">Kod içinde göre sıralamak için özellik adını geçirmek ve <xref:System.ComponentModel.ListSortDirection> Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="42c9b-154">In code, pass the name of the property to sort by and the <xref:System.ComponentModel.ListSortDirection> to the constructor.</span></span>  
  
2.  <span data-ttu-id="42c9b-155">Ekleme <xref:System.ComponentModel.SortDescription> için <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="42c9b-155">Add the <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="42c9b-156">Ek örneklerini eklemek <xref:System.ComponentModel.SortDescription> için <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> ek bir özelliğe göre sıralamak için koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="42c9b-156">Add additional instances of <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> collection to sort by additional properties.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#011](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#211](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
     [!code-vb[DataGrid_GroupSortFilter#211](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]  
  
## <a name="filtering-items-in-a-datagrid"></a><span data-ttu-id="42c9b-157">DataGrid öğelerinin filtreleme</span><span class="sxs-lookup"><span data-stu-id="42c9b-157">Filtering items in a DataGrid</span></span>  
 <span data-ttu-id="42c9b-158">Öğelere filtre uygulamak için bir <xref:System.Windows.Controls.DataGrid> kullanarak bir <xref:System.Windows.Data.CollectionViewSource>, işleyicisi filtreleme mantık sağlayan <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> olay.</span><span class="sxs-lookup"><span data-stu-id="42c9b-158">To filter items in a <xref:System.Windows.Controls.DataGrid> using a <xref:System.Windows.Data.CollectionViewSource>, you provide the filtering logic in the handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
#### <a name="to-filter-items-in-a-datagrid"></a><span data-ttu-id="42c9b-159">DataGrid öğelerinin filtre uygulamak için</span><span class="sxs-lookup"><span data-stu-id="42c9b-159">To filter items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="42c9b-160">İçin bir işleyici ekleyin <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> olay.</span><span class="sxs-lookup"><span data-stu-id="42c9b-160">Add a handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
2.  <span data-ttu-id="42c9b-161">İçinde <xref:System.Windows.Data.CollectionViewSource.Filter> olay işleyicisi filtreleme mantığı tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="42c9b-161">In the <xref:System.Windows.Data.CollectionViewSource.Filter> event handler, define the filtering logic.</span></span>  
  
     <span data-ttu-id="42c9b-162">Filtre görünümü her yenilendiğinde uygulanacak.</span><span class="sxs-lookup"><span data-stu-id="42c9b-162">The filter will be applied every time the view is refreshed.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#013](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#113](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
     [!code-vb[DataGrid_GroupSortFilter#113](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]  
  
 <span data-ttu-id="42c9b-163">Alternatif olarak, öğeleri filtreleyebilirsiniz bir <xref:System.Windows.Controls.DataGrid> filtreleme mantığı ve ayarı sağlayan bir yöntem oluşturarak <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> özellik filtresini uygulayın.</span><span class="sxs-lookup"><span data-stu-id="42c9b-163">Alternatively, you can filter items in a <xref:System.Windows.Controls.DataGrid> by creating a method that provides the filtering logic and setting the <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> property to apply the filter.</span></span> <span data-ttu-id="42c9b-164">Bu yöntemin bir örnek için bkz [görünümünde filtre veri](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span><span class="sxs-lookup"><span data-stu-id="42c9b-164">To see an example of this method, see [Filter Data in a View](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="42c9b-165">Örnek</span><span class="sxs-lookup"><span data-stu-id="42c9b-165">Example</span></span>  
 <span data-ttu-id="42c9b-166">Aşağıdaki örnek, gruplandırma, sıralama ve filtreleme gösterir `Task` verileri bir <xref:System.Windows.Data.CollectionViewSource> ve sıralanmış ve filtre uygulanmış gruplandırılmış, görüntüleme `Task` verileri bir <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="42c9b-166">The following example demonstrates grouping, sorting, and filtering `Task` data in a <xref:System.Windows.Data.CollectionViewSource> and displaying the grouped, sorted, and filtered `Task` data in a <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="42c9b-167"><xref:System.Windows.Data.CollectionViewSource> Olarak kullanılan <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> için <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="42c9b-167">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="42c9b-168">Gruplandırma, sıralama ve filtreleme üzerinde gerçekleştirilir <xref:System.Windows.Data.CollectionViewSource> ve görüntülenen <xref:System.Windows.Controls.DataGrid> UI.</span><span class="sxs-lookup"><span data-stu-id="42c9b-168">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="42c9b-169">Bu örneği test etmek için proje adı ile eşleşmesi için DGGroupSortFilterExample adı ayarlamak gerekir.</span><span class="sxs-lookup"><span data-stu-id="42c9b-169">To test this example, you will need to adjust the DGGroupSortFilterExample name to match your project name.</span></span> <span data-ttu-id="42c9b-170">Visual Basic kullanıyorsanız, sınıf adını değiştirmeniz gerekir <xref:System.Windows.Window> şu.</span><span class="sxs-lookup"><span data-stu-id="42c9b-170">If you are using Visual Basic, you will need to change the class name for <xref:System.Windows.Window> to the following.</span></span>  
  
 `<Window x:Class="MainWindow"`  
  
 [!code-xaml[DataGrid_GroupSortFilter#000](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]  
  
 [!code-csharp[DataGrid_GroupSortFilter#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
 [!code-vb[DataGrid_GroupSortFilter#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="42c9b-171">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="42c9b-171">Compiling the Code</span></span>  
  
-  
  
## <a name="robust-programming"></a><span data-ttu-id="42c9b-172">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="42c9b-172">Robust Programming</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="42c9b-173">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="42c9b-173">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42c9b-174">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="42c9b-174">See Also</span></span>  
 [<span data-ttu-id="42c9b-175">Veri bağlama genel bakış</span><span class="sxs-lookup"><span data-stu-id="42c9b-175">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="42c9b-176">Oluşturun ve ObservableCollection bağlayın</span><span class="sxs-lookup"><span data-stu-id="42c9b-176">Create and Bind to an ObservableCollection</span></span>](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)  
 [<span data-ttu-id="42c9b-177">Bir görünümündeki verileri filtreleme</span><span class="sxs-lookup"><span data-stu-id="42c9b-177">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="42c9b-178">Bir görünümdeki verileri sıralama</span><span class="sxs-lookup"><span data-stu-id="42c9b-178">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="42c9b-179">XAML'de bir görünümü kullanarak Grup verileri sıralama ve</span><span class="sxs-lookup"><span data-stu-id="42c9b-179">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)