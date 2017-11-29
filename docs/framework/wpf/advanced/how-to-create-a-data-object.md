---
title: "Nasıl yapılır: Veri Nesnesi Oluşturma"
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
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7b002e1c7a9eea2592de58aac3b838b9f6f982ce
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="70466-102">Nasıl yapılır: Veri Nesnesi Oluşturma</span><span class="sxs-lookup"><span data-stu-id="70466-102">How to: Create a Data Object</span></span>
<span data-ttu-id="70466-103">Aşağıdaki örnekler tarafından sağlanan oluşturucuları kullanarak bir veri nesnesi oluşturmak için çeşitli şekillerde <xref:System.Windows.DataObject> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="70466-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70466-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="70466-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="70466-105">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70466-105">Description</span></span>  
 <span data-ttu-id="70466-106">Aşağıdaki örnek kod yeni bir veri nesnesi oluşturur ve aşırı yüklü oluşturucular birini kullanır (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) veri nesnesini bir dize ile başlatılamadı.</span><span class="sxs-lookup"><span data-stu-id="70466-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="70466-107">Bu durumda, uygun veri biçimi saklanan veri türüne göre otomatik olarak belirlenir ve depolanan veri için otomatik dönüştürme, varsayılan olarak izin verilir.</span><span class="sxs-lookup"><span data-stu-id="70466-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="70466-108">Kod</span><span class="sxs-lookup"><span data-stu-id="70466-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="70466-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70466-109">Description</span></span>  
 <span data-ttu-id="70466-110">Aşağıdaki kod örneği, yukarıda gösterilen koddan, sıkıştırılmış bir sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="70466-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="70466-111">Kod</span><span class="sxs-lookup"><span data-stu-id="70466-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="70466-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="70466-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="70466-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70466-113">Description</span></span>  
 <span data-ttu-id="70466-114">Aşağıdaki örnek kod yeni bir veri nesnesi oluşturur ve aşırı yüklü oluşturucular birini kullanır (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) veri nesnesini bir dize ve belirtilen veri biçimi ile başlatılamadı.</span><span class="sxs-lookup"><span data-stu-id="70466-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="70466-115">Bu durumda veri biçimi dizesi tarafından belirtilir; <xref:System.Windows.DataFormats> sınıfı türü önceden tanımlanmış dizeler kümesi sağlar.</span><span class="sxs-lookup"><span data-stu-id="70466-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="70466-116">Depolanan veriler için otomatik dönüştürme, varsayılan olarak izin verilir.</span><span class="sxs-lookup"><span data-stu-id="70466-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="70466-117">Kod</span><span class="sxs-lookup"><span data-stu-id="70466-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="70466-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70466-118">Description</span></span>  
 <span data-ttu-id="70466-119">Aşağıdaki kod örneği, yukarıda gösterilen koddan, sıkıştırılmış bir sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="70466-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="70466-120">Kod</span><span class="sxs-lookup"><span data-stu-id="70466-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="70466-121">Örnek</span><span class="sxs-lookup"><span data-stu-id="70466-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="70466-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70466-122">Description</span></span>  
 <span data-ttu-id="70466-123">Aşağıdaki örnek kod yeni bir veri nesnesi oluşturur ve aşırı yüklü oluşturucular birini kullanır (<xref:System.Windows.DataObject.%23ctor%2A>) veri nesnesini bir dize ve belirtilen veri biçimi ile başlatılamadı.</span><span class="sxs-lookup"><span data-stu-id="70466-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="70466-124">Bu durumda veri biçimi tarafından belirtilen bir <xref:System.Type> parametresi.</span><span class="sxs-lookup"><span data-stu-id="70466-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="70466-125">Depolanan veriler için otomatik dönüştürme, varsayılan olarak izin verilir.</span><span class="sxs-lookup"><span data-stu-id="70466-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="70466-126">Kod</span><span class="sxs-lookup"><span data-stu-id="70466-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="70466-127">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70466-127">Description</span></span>  
 <span data-ttu-id="70466-128">Aşağıdaki kod örneği, yukarıda gösterilen koddan, sıkıştırılmış bir sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="70466-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="70466-129">Kod</span><span class="sxs-lookup"><span data-stu-id="70466-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="70466-130">Örnek</span><span class="sxs-lookup"><span data-stu-id="70466-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="70466-131">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70466-131">Description</span></span>  
 <span data-ttu-id="70466-132">Aşağıdaki örnek kod yeni bir veri nesnesi oluşturur ve aşırı yüklü oluşturucular birini kullanır (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) veri nesnesini bir dize ve belirtilen veri biçimi ile başlatılamadı.</span><span class="sxs-lookup"><span data-stu-id="70466-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="70466-133">Bu durumda veri biçimi dizesi tarafından belirtilir; <xref:System.Windows.DataFormats> sınıfı türü önceden tanımlanmış dizeler kümesi sağlar.</span><span class="sxs-lookup"><span data-stu-id="70466-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="70466-134">Bu belirli oluşturucu aşırı çağıran otomatik dönüştürmeye izin verilip verilmediğini belirtmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="70466-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="70466-135">Kod</span><span class="sxs-lookup"><span data-stu-id="70466-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="70466-136">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70466-136">Description</span></span>  
 <span data-ttu-id="70466-137">Aşağıdaki kod örneği, yukarıda gösterilen koddan, sıkıştırılmış bir sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="70466-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="70466-138">Kod</span><span class="sxs-lookup"><span data-stu-id="70466-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="70466-139">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="70466-139">See Also</span></span>  
 <xref:System.Windows.IDataObject>