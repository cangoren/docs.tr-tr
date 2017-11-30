---
title: "AutoSize Özelliğine Genel Bakış"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c8216880ebdede03bbd01fe53b622c14ca8c514d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="autosize-property-overview"></a><span data-ttu-id="87de1-102">AutoSize Özelliğine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="87de1-102">AutoSize Property Overview</span></span>
<span data-ttu-id="87de1-103"><xref:System.Windows.Forms.Control.AutoSize%2A> Özelliği tarafından belirtilen değeri elde etmek gerekirse, boyutunu değiştirmek bir denetim sağlar <xref:System.Windows.Forms.Control.PreferredSize%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-103">The <xref:System.Windows.Forms.Control.AutoSize%2A> property enables a control to change its size, if necessary, to attain the value specified by the <xref:System.Windows.Forms.Control.PreferredSize%2A> property.</span></span> <span data-ttu-id="87de1-104">Belirleyerek belirli denetimleri boyutlandırma davranışını ayarlama `AutoSizeMode` özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-104">You adjust the sizing behavior for specific controls by setting the `AutoSizeMode` property.</span></span>  
  
## <a name="autosize-behavior"></a><span data-ttu-id="87de1-105">AutoSize davranışı</span><span class="sxs-lookup"><span data-stu-id="87de1-105">AutoSize Behavior</span></span>  
 <span data-ttu-id="87de1-106">Yalnızca bazı denetimler Destek <xref:System.Windows.Forms.Control.AutoSize%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-106">Only some controls support the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="87de1-107">Ayrıca, bazı denetimler destekleyen <xref:System.Windows.Forms.Control.AutoSize%2A> özelliği de destek `AutoSizeMode` özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-107">In addition, some controls that support the <xref:System.Windows.Forms.Control.AutoSize%2A> property also support the `AutoSizeMode` property.</span></span>  
  
 <span data-ttu-id="87de1-108"><xref:System.Windows.Forms.Control.AutoSize%2A> Özelliği üreten belirli denetim türü ve değerine bağlı olarak biraz farklı bir davranış `AutoSizeMode` özellik varsa, özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-108">The <xref:System.Windows.Forms.Control.AutoSize%2A> property produces somewhat different behavior, depending on the specific control type and the value of the `AutoSizeMode` property, if the property exists.</span></span> <span data-ttu-id="87de1-109">Aşağıdaki tabloda, her zaman true davranışları açıklar ve her kısa bir açıklaması verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="87de1-109">The following table describes the behaviors that are always true and provides a brief description of each:</span></span>  
  
|<span data-ttu-id="87de1-110">Her zaman true davranışı</span><span class="sxs-lookup"><span data-stu-id="87de1-110">Always true behavior</span></span>|<span data-ttu-id="87de1-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="87de1-111">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="87de1-112">Otomatik boyutlandırma bir çalışma zamanı özelliğidir.</span><span class="sxs-lookup"><span data-stu-id="87de1-112">Automatic sizing is a run-time feature.</span></span>|<span data-ttu-id="87de1-113">Bu, hiçbir zaman büyüdükçe veya denetim küçültür ve ardından başka hiçbir etkisi olmaz anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="87de1-113">This means it never grows or shrinks a control and then has no further effect.</span></span>|  
|<span data-ttu-id="87de1-114">Bir denetim boyutu, değeri değişirse, <xref:System.Windows.Forms.Control.Location%2A> özelliği her zaman sabittir.</span><span class="sxs-lookup"><span data-stu-id="87de1-114">If a control changes size, the value of its <xref:System.Windows.Forms.Control.Location%2A> property always remains constant.</span></span>|<span data-ttu-id="87de1-115">Bir denetimin içeriği büyümesine neden olduğunda denetimi aşağı ve sağa doğru artar.</span><span class="sxs-lookup"><span data-stu-id="87de1-115">When a control's contents cause it to grow, the control grows toward the right and downward.</span></span> <span data-ttu-id="87de1-116">Denetimleri sola büyümesine değil.</span><span class="sxs-lookup"><span data-stu-id="87de1-116">Controls do not grow to the left.</span></span>|  
|<span data-ttu-id="87de1-117"><xref:System.Windows.Forms.Control.Dock%2A> Ve <xref:System.Windows.Forms.Control.Anchor%2A> özellikleri ne zaman kabul olan <xref:System.Windows.Forms.Control.AutoSize%2A> olan `true`.</span><span class="sxs-lookup"><span data-stu-id="87de1-117">The <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> properties are honored when <xref:System.Windows.Forms.Control.AutoSize%2A> is `true`.</span></span>|<span data-ttu-id="87de1-118">Denetimin değerini <xref:System.Windows.Forms.Control.Location%2A> özelliği doğru değerine ayarlanmış.</span><span class="sxs-lookup"><span data-stu-id="87de1-118">The value of the control's <xref:System.Windows.Forms.Control.Location%2A> property is adjusted to the correct value.</span></span><br /><br /> <span data-ttu-id="87de1-119">**Not** <xref:System.Windows.Forms.Label> bu kural için özel bir denetimdir.</span><span class="sxs-lookup"><span data-stu-id="87de1-119">**Note** The <xref:System.Windows.Forms.Label> control is the exception to this rule.</span></span> <span data-ttu-id="87de1-120">Bir yerleşik değeri ayarlandığında <xref:System.Windows.Forms.Label> denetimin <xref:System.Windows.Forms.Control.AutoSize%2A> özelliğine `true`, <xref:System.Windows.Forms.Label> denetimi uzamaz.</span><span class="sxs-lookup"><span data-stu-id="87de1-120">When you set the value of a docked <xref:System.Windows.Forms.Label> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`, the <xref:System.Windows.Forms.Label> control will not stretch.</span></span>|  
|<span data-ttu-id="87de1-121">Bir denetimin <xref:System.Windows.Forms.Control.MaximumSize%2A> ve <xref:System.Windows.Forms.Control.MinimumSize%2A> özellikleri her zaman korunur, değeri bağımsız olarak kendi <xref:System.Windows.Forms.Control.AutoSize%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-121">A control's <xref:System.Windows.Forms.Control.MaximumSize%2A> and <xref:System.Windows.Forms.Control.MinimumSize%2A> properties are always honored, regardless of the value of its <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span>|<span data-ttu-id="87de1-122"><xref:System.Windows.Forms.Control.MaximumSize%2A> Ve <xref:System.Windows.Forms.Control.MinimumSize%2A> özellikleri etkilenmez <xref:System.Windows.Forms.Control.AutoSize%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-122">The <xref:System.Windows.Forms.Control.MaximumSize%2A> and <xref:System.Windows.Forms.Control.MinimumSize%2A> properties are not affected by the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span>|  
|<span data-ttu-id="87de1-123">Varsayılan olarak ayarlanan en düşük boyut yoktur.</span><span class="sxs-lookup"><span data-stu-id="87de1-123">There is no minimum size set by default.</span></span>|<span data-ttu-id="87de1-124">Altında daraltmak için bir denetim ayarlarsanız buna <xref:System.Windows.Forms.Control.AutoSize%2A> ve hiç içerik değerini sahip kendi <xref:System.Windows.Forms.Control.Size%2A> 0,0 bir özelliktir.</span><span class="sxs-lookup"><span data-stu-id="87de1-124">This means that if a control is set to shrink under <xref:System.Windows.Forms.Control.AutoSize%2A> and it has no contents, the value of its <xref:System.Windows.Forms.Control.Size%2A> property is 0,0.</span></span> <span data-ttu-id="87de1-125">Bu durumda, denetiminiz bir noktasına küçülür ve kolaylıkla görünür olmaz.</span><span class="sxs-lookup"><span data-stu-id="87de1-125">In this case, your control will shrink to a point, and it will not be readily visible.</span></span>|  
|<span data-ttu-id="87de1-126">Bir denetim uygulamazsa <xref:System.Windows.Forms.Control.GetPreferredSize%2A> yöntemi, <xref:System.Windows.Forms.Control.GetPreferredSize%2A> yöntemi atanan son değeri döndürür <xref:System.Windows.Forms.Control.Size%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-126">If a control does not implement the <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method, the <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method returns last value assigned to the <xref:System.Windows.Forms.Control.Size%2A> property.</span></span>|<span data-ttu-id="87de1-127">Bu ayar yani <xref:System.Windows.Forms.Control.AutoSize%2A> için `true` hiçbir etkisi olmaz.</span><span class="sxs-lookup"><span data-stu-id="87de1-127">This means that setting <xref:System.Windows.Forms.Control.AutoSize%2A> to `true` will have no effect.</span></span>|  
|<span data-ttu-id="87de1-128">Bir denetimde bir <xref:System.Windows.Forms.TableLayoutPanel> hücre her zaman kadar hücresindeki sığacak şekilde küçültür kendi <xref:System.Windows.Forms.Control.MinimumSize%2A> ulaşıldı.</span><span class="sxs-lookup"><span data-stu-id="87de1-128">A control in a <xref:System.Windows.Forms.TableLayoutPanel> cell always shrinks to fit in the cell until its <xref:System.Windows.Forms.Control.MinimumSize%2A> is reached.</span></span>|<span data-ttu-id="87de1-129">Bu boyut sınırını uygulanır.</span><span class="sxs-lookup"><span data-stu-id="87de1-129">This size is enforced as a maximum size.</span></span> <span data-ttu-id="87de1-130">Hücrenin parçası olduğunda bu şekilde değilse bir <xref:System.Windows.Forms.SizeType.AutoSize> satır veya sütun.</span><span class="sxs-lookup"><span data-stu-id="87de1-130">This is not the case when the cell is part of an <xref:System.Windows.Forms.SizeType.AutoSize> row or column.</span></span>|  
  
## <a name="autosizemode-property"></a><span data-ttu-id="87de1-131">AutoSizeMode özelliği</span><span class="sxs-lookup"><span data-stu-id="87de1-131">AutoSizeMode Property</span></span>  
 <span data-ttu-id="87de1-132">`AutoSizeMode` Özelliği, varsayılan üzerinde daha ayrıntılı denetim sağlar <xref:System.Windows.Forms.Control.AutoSize%2A> davranışı.</span><span class="sxs-lookup"><span data-stu-id="87de1-132">The `AutoSizeMode` property provides more fine-grained control over the default <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span> <span data-ttu-id="87de1-133">`AutoSizeMode` Özelliği, nasıl bir denetim kendisini içeriğine boyutları belirtir.</span><span class="sxs-lookup"><span data-stu-id="87de1-133">The `AutoSizeMode` property specifies how a control sizes itself to its content.</span></span> <span data-ttu-id="87de1-134">İçerik, örneğin, metnini olabilir bir <xref:System.Windows.Forms.Button> denetim veya alt denetimleri için bir kapsayıcı.</span><span class="sxs-lookup"><span data-stu-id="87de1-134">The content, for example, could be the text for a <xref:System.Windows.Forms.Button> control or the child controls for a container.</span></span>  
  
 <span data-ttu-id="87de1-135">Aşağıdaki tabloda <xref:System.Windows.Forms.AutoSizeMode> ayarları ve davranışı açıklamasını her ayar verilmesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="87de1-135">The following table shows the <xref:System.Windows.Forms.AutoSizeMode> settings and a description of the behavior each setting elicits.</span></span>  
  
|<span data-ttu-id="87de1-136">AutoSizeMode ayarı</span><span class="sxs-lookup"><span data-stu-id="87de1-136">AutoSizeMode setting</span></span>|<span data-ttu-id="87de1-137">Davranış</span><span class="sxs-lookup"><span data-stu-id="87de1-137">Behavior</span></span>|  
|--------------------------|--------------|  
|<span data-ttu-id="87de1-138">GrowAndShrink</span><span class="sxs-lookup"><span data-stu-id="87de1-138">GrowAndShrink</span></span>|<span data-ttu-id="87de1-139">Denetim büyüdüğünde veya küçüldüğünde içeriğinin kapsayacak şekilde.</span><span class="sxs-lookup"><span data-stu-id="87de1-139">The control grows or shrinks to encompass its contents.</span></span><br /><br /> <span data-ttu-id="87de1-140"><xref:System.Windows.Forms.Control.MinimumSize%2A> Ve <xref:System.Windows.Forms.Control.MaximumSize%2A> değerlerini dikkate alınır, geçerli değeri <xref:System.Windows.Forms.Control.Size%2A> özelliği yoksayılır.</span><span class="sxs-lookup"><span data-stu-id="87de1-140">The <xref:System.Windows.Forms.Control.MinimumSize%2A> and <xref:System.Windows.Forms.Control.MaximumSize%2A> values are honored, but the current value of the <xref:System.Windows.Forms.Control.Size%2A> property is ignored.</span></span><br /><br /> <span data-ttu-id="87de1-141">Denetimler ile aynı davranışı budur <xref:System.Windows.Forms.Control.AutoSize%2A> özelliği ve Hayır `AutoSizeMode` özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-141">This is the same behavior as controls with the <xref:System.Windows.Forms.Control.AutoSize%2A> property and no `AutoSizeMode` property.</span></span>|  
|<span data-ttu-id="87de1-142">GrowOnly</span><span class="sxs-lookup"><span data-stu-id="87de1-142">GrowOnly</span></span>|<span data-ttu-id="87de1-143">Denetim içeriğinin kapsayacak şekilde gerektiği kadar büyür, ancak bunu tarafından belirtilen değerden daha küçük küçültme olmayacağı kendi <xref:System.Windows.Forms.Control.Size%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-143">The control grows as much as necessary to encompass its contents, but it will not shrink smaller than the value specified by its <xref:System.Windows.Forms.Control.Size%2A> property.</span></span><br /><br /> <span data-ttu-id="87de1-144">İçin varsayılan değer budur `AutoSizeMode`.</span><span class="sxs-lookup"><span data-stu-id="87de1-144">This is the default value for `AutoSizeMode`.</span></span>|  
  
## <a name="controls-that-support-the-autosize-property"></a><span data-ttu-id="87de1-145">AutoSize özelliği destekleyen denetimleri</span><span class="sxs-lookup"><span data-stu-id="87de1-145">Controls That Support the AutoSize Property</span></span>  
 <span data-ttu-id="87de1-146">Destekleyen denetimleri aşağıdaki tabloda listelenmektedir <xref:System.Windows.Forms.Control.AutoSize%2A> ve `AutoSizeMode` özellikleri.</span><span class="sxs-lookup"><span data-stu-id="87de1-146">The following table lists the controls that support the <xref:System.Windows.Forms.Control.AutoSize%2A> and `AutoSizeMode` properties.</span></span>  
  
|<span data-ttu-id="87de1-147">AutoSize desteği</span><span class="sxs-lookup"><span data-stu-id="87de1-147">AutoSize support</span></span>|<span data-ttu-id="87de1-148">Denetim türü</span><span class="sxs-lookup"><span data-stu-id="87de1-148">Control type</span></span>|  
|----------------------|------------------|  
|<span data-ttu-id="87de1-149">-   <xref:System.Windows.Forms.Control.AutoSize%2A>desteklenen özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-149">-   <xref:System.Windows.Forms.Control.AutoSize%2A> property supported.</span></span><br /><span data-ttu-id="87de1-150">-Hiçbir `AutoSizeMode` özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-150">-   No `AutoSizeMode` property.</span></span>|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <span data-ttu-id="87de1-151"><xref:System.Windows.Forms.MaskedTextBox>(<xref:System.Windows.Forms.TextBox> temel)</span><span class="sxs-lookup"><span data-stu-id="87de1-151"><xref:System.Windows.Forms.MaskedTextBox> (<xref:System.Windows.Forms.TextBox> base)</span></span><br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|  
|<span data-ttu-id="87de1-152">-   <xref:System.Windows.Forms.Control.AutoSize%2A>desteklenen özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-152">-   <xref:System.Windows.Forms.Control.AutoSize%2A> property supported.</span></span><br /><span data-ttu-id="87de1-153">-   `AutoSizeMode`desteklenen özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-153">-   `AutoSizeMode` property supported.</span></span>|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|  
|<span data-ttu-id="87de1-154">-Hiçbir <xref:System.Windows.Forms.Control.AutoSize%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-154">-   No <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span>|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|  
  
## <a name="autosize-in-the-design-environment"></a><span data-ttu-id="87de1-155">Tasarım ortamında AutoSize</span><span class="sxs-lookup"><span data-stu-id="87de1-155">AutoSize in the Design Environment</span></span>  
 <span data-ttu-id="87de1-156">Aşağıdaki tabloda, değerine göre tasarım zamanında denetimi boyutlandırma davranışını tanımlar, <xref:System.Windows.Forms.Control.AutoSize%2A> ve `AutoSizeMode` özellikleri.</span><span class="sxs-lookup"><span data-stu-id="87de1-156">The following table describes the sizing behavior of a control at design time, based on the value of its <xref:System.Windows.Forms.Control.AutoSize%2A> and `AutoSizeMode` properties.</span></span>  
  
 <span data-ttu-id="87de1-157">Geçersiz kılma <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> belirli bir denetim kullanıcı yeniden boyutlandırılabilir bir durumda olup olmadığını belirlemek için özellik.</span><span class="sxs-lookup"><span data-stu-id="87de1-157">Override the <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> property to determine whether a given control is in a user-resizable state.</span></span> <span data-ttu-id="87de1-158">Aşağıdaki tabloda, "anlamına gelir olamaz" <xref:System.Windows.Forms.Design.SelectionRules.Moveable> yalnızca "anlamına gelir olabilir" <xref:System.Windows.Forms.Design.SelectionRules.AllSizeable> ve <xref:System.Windows.Forms.Design.SelectionRules.Moveable>.</span><span class="sxs-lookup"><span data-stu-id="87de1-158">In the following table, "cannot" means <xref:System.Windows.Forms.Design.SelectionRules.Moveable> only, "can" means <xref:System.Windows.Forms.Design.SelectionRules.AllSizeable> and <xref:System.Windows.Forms.Design.SelectionRules.Moveable>.</span></span>  
  
|<span data-ttu-id="87de1-159">AutoSize ayarları</span><span class="sxs-lookup"><span data-stu-id="87de1-159">AutoSize settings</span></span>|<span data-ttu-id="87de1-160">Tasarım zamanı boyutlandırma hareketi</span><span class="sxs-lookup"><span data-stu-id="87de1-160">Design-time sizing gesture</span></span>|  
|-----------------------|---------------------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br /><span data-ttu-id="87de1-161">-Hiçbir `AutoSizeMode` özelliği.</span><span class="sxs-lookup"><span data-stu-id="87de1-161">-   No `AutoSizeMode` property.</span></span>|<span data-ttu-id="87de1-162">Kullanıcı denetimi aşağıdaki denetimleri dışında tasarım zamanında boyutlandırılamıyor:</span><span class="sxs-lookup"><span data-stu-id="87de1-162">The user cannot resize the control at design time, except for the following controls:</span></span><br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>|<span data-ttu-id="87de1-163">Kullanıcı denetimi tasarım zamanında boyutlandırılamaz.</span><span class="sxs-lookup"><span data-stu-id="87de1-163">The user cannot resize the control at design time.</span></span>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>|<span data-ttu-id="87de1-164">Kullanıcı denetimi tasarım zamanında genişletebilir.</span><span class="sxs-lookup"><span data-stu-id="87de1-164">The user can resize the control at design time.</span></span> <span data-ttu-id="87de1-165">Zaman <xref:System.Windows.Forms.Control.Size%2A> özelliği ayarlanmışsa, kullanıcı yalnızca denetimi boyutunu artırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="87de1-165">When the <xref:System.Windows.Forms.Control.Size%2A> property is set, the user can only increase the size of the control.</span></span>|  
|<span data-ttu-id="87de1-166">-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `false`, veya <xref:System.Windows.Forms.Control.AutoSize%2A> özelliği gizlenir.</span><span class="sxs-lookup"><span data-stu-id="87de1-166">-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `false`, or <xref:System.Windows.Forms.Control.AutoSize%2A> property is hidden.</span></span>|<span data-ttu-id="87de1-167">Kullanıcı denetimi tasarım zamanında genişletebilir.</span><span class="sxs-lookup"><span data-stu-id="87de1-167">User can resize the control at design time.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="87de1-168">Windows Form Tasarımcısı gölgeleri üretkenliği en üst düzeye çıkarmak için <xref:System.Windows.Forms.Control.AutoSize%2A> özelliği için <xref:System.Windows.Forms.Form> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="87de1-168">To maximize productivity, the Windows Forms Designer shadows the <xref:System.Windows.Forms.Control.AutoSize%2A> property for the <xref:System.Windows.Forms.Form> class.</span></span> <span data-ttu-id="87de1-169">Tasarım zamanında form olarak ancak davranır <xref:System.Windows.Forms.Control.AutoSize%2A> özelliği ayarlanmış `false`ne olursa olsun, gerçek ayarı.</span><span class="sxs-lookup"><span data-stu-id="87de1-169">At design time, the form behaves as though the <xref:System.Windows.Forms.Control.AutoSize%2A> property is set to `false`, regardless of its actual setting.</span></span> <span data-ttu-id="87de1-170">Hiçbir özel Konaklama çalışma zamanında yapılmış ve <xref:System.Windows.Forms.Control.AutoSize%2A> özelliği uygulanır özellik ayarı tarafından belirtildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="87de1-170">At runtime, no special accommodation is made, and the <xref:System.Windows.Forms.Control.AutoSize%2A> property is applied as specified by the property setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87de1-171">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="87de1-171">See Also</span></span>  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.Control.PreferredSize%2A>  
 <xref:System.Windows.Forms.Control.GetPreferredSize%2A>