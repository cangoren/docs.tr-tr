---
title: "WindowsFormsHost Öğesi için Düzen Konusunda Dikkat Edilmesi Gereken Noktalar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element layout considerations [WPF]
- dynamic layout [WPF interoperability]
- device-independent pixels
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d21077e6012f8e48a1418f67e8f0d156d82003c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a><span data-ttu-id="01368-102">WindowsFormsHost Öğesi için Düzen Konusunda Dikkat Edilmesi Gereken Noktalar</span><span class="sxs-lookup"><span data-stu-id="01368-102">Layout Considerations for the WindowsFormsHost Element</span></span>
<span data-ttu-id="01368-103">Bu konuda açıklanmaktadır nasıl <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi etkileşime [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] düzen sistemi.</span><span class="sxs-lookup"><span data-stu-id="01368-103">This topic describes how the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element interacts with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout system.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="01368-104">ve [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] boyutlandırma ve bir form veya sayfa üzerinde öğeleri konumlandırma için farklı fakat benzer bir mantığı destekler.</span><span class="sxs-lookup"><span data-stu-id="01368-104"> and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] support different, but similar, logic for sizing and positioning elements on a form or page.</span></span> <span data-ttu-id="01368-105">Karma kullanıcı arabirimini (UI) barındıran oluşturduğunuzda [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimlerini [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi iki Düzen şeması tümleştirir.</span><span class="sxs-lookup"><span data-stu-id="01368-105">When you create a hybrid user interface (UI) that hosts [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element integrates the two layout schemes.</span></span>  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a><span data-ttu-id="01368-106">WPF ve Windows Forms arasındaki Düzen farkları</span><span class="sxs-lookup"><span data-stu-id="01368-106">Differences in Layout Between WPF and Windows Forms</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="01368-107">Çözümleme bağımsız düzenini kullanır.</span><span class="sxs-lookup"><span data-stu-id="01368-107"> uses resolution-independent layout.</span></span> <span data-ttu-id="01368-108">Tüm [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] düzen boyutları kullanarak belirtilen *aygıttan bağımsız piksel*.</span><span class="sxs-lookup"><span data-stu-id="01368-108">All [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout dimensions are specified using *device-independent pixels*.</span></span> <span data-ttu-id="01368-109">CİHAZDAN bağımsız piksel bir doksan altıncı inç boyutu ve çözümleme bağımsız olduğundan, 72 DPI İzleyici veya 19.200 DPI yazıcıya işleme bağımsız olarak benzer sonuçlar elde.</span><span class="sxs-lookup"><span data-stu-id="01368-109">A device-independent pixel is one ninety-sixth of an inch in size and resolution-independent, so you get similar results regardless of whether you are rendering to a 72-dpi monitor or a 19,200-dpi printer.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="01368-110">Ayrıca dayanır *dinamik düzen*.</span><span class="sxs-lookup"><span data-stu-id="01368-110"> is also based on *dynamic layout*.</span></span> <span data-ttu-id="01368-111">Bu, bir kullanıcı Arabirimi öğesi kendisini bir form veya sayfa içeriğini, üst düzen kapsayıcısına ve kullanılabilir ekran boyutuna göre düzenler olduğunu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="01368-111">This means that a UI element arranges itself on a form or page according to its content, its parent layout container, and the available screen size.</span></span> <span data-ttu-id="01368-112">Dinamik düzen içerdikleri dizeler uzunluğu değiştirdiğinde otomatik olarak kullanıcı Arabirimi öğeleri konumunu ve boyutunu ayarlayarak yerelleştirme kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="01368-112">Dynamic layout facilitates localization by automatically adjusting the size and position of UI elements when the strings they contain change length.</span></span>  
  
 <span data-ttu-id="01368-113">Düzende [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] aygıta bağımlı ve büyük olasılıkla statik olarak.</span><span class="sxs-lookup"><span data-stu-id="01368-113">Layout in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] is device-dependent and more likely to be static.</span></span> <span data-ttu-id="01368-114">Genellikle, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimleri konumlandırıldığı kesinlikle donanım piksel cinsinden belirtilen boyutlar kullanılarak bir form üzerinde.</span><span class="sxs-lookup"><span data-stu-id="01368-114">Typically, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls are positioned absolutely on a form using dimensions specified in hardware pixels.</span></span> <span data-ttu-id="01368-115">Ancak, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] bazı dinamik düzen özellikler aşağıdaki tabloda özetlendiği gibi desteklemiyor.</span><span class="sxs-lookup"><span data-stu-id="01368-115">However, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] does support some dynamic layout features, as summarized in the following table.</span></span>  
  
|<span data-ttu-id="01368-116">Düzeni özelliği</span><span class="sxs-lookup"><span data-stu-id="01368-116">Layout feature</span></span>|<span data-ttu-id="01368-117">Açıklama</span><span class="sxs-lookup"><span data-stu-id="01368-117">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="01368-118">Otomatik boyutlandırma</span><span class="sxs-lookup"><span data-stu-id="01368-118">Autosizing</span></span>|<span data-ttu-id="01368-119">Bazı [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimleri kendilerini içeriklerini düzgün görüntülemek için yeniden boyutlandırın.</span><span class="sxs-lookup"><span data-stu-id="01368-119">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls resize themselves to display their contents properly.</span></span> <span data-ttu-id="01368-120">Daha fazla bilgi için bkz: [AutoSize özelliğine genel bakış](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="01368-120">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>|  
|<span data-ttu-id="01368-121">Sabitleme ve yerleştirme</span><span class="sxs-lookup"><span data-stu-id="01368-121">Anchoring and docking</span></span>|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="01368-122">denetimleri konumlandırma ve üst kapsayıcı dayalı boyutlandırma destekler.</span><span class="sxs-lookup"><span data-stu-id="01368-122"> controls support positioning and sizing based on the parent container.</span></span> <span data-ttu-id="01368-123">Daha fazla bilgi için bkz. <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> ve <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="01368-123">For more information, see <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="01368-124">Otomatik ölçeklendirme</span><span class="sxs-lookup"><span data-stu-id="01368-124">Autoscaling</span></span>|<span data-ttu-id="01368-125">Kapsayıcı denetimleri kendilerini ve çıktı aygıtı veya piksel cinsinden varsayılan kapsayıcı yazı tipi boyutu çözümlenmesi göre bunların alt öğeleri yeniden boyutlandırın.</span><span class="sxs-lookup"><span data-stu-id="01368-125">Container controls resize themselves and their children based on the resolution of the output device or the size, in pixels, of the default container font.</span></span> <span data-ttu-id="01368-126">Daha fazla bilgi için bkz: [otomatik ölçeklendirmeyi Windows Forms'ta](../../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="01368-126">For more information, see [Automatic Scaling in Windows Forms](../../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md).</span></span>|  
|<span data-ttu-id="01368-127">Düzen kapsayıcıları</span><span class="sxs-lookup"><span data-stu-id="01368-127">Layout containers</span></span>|<span data-ttu-id="01368-128"><xref:System.Windows.Forms.FlowLayoutPanel> Ve <xref:System.Windows.Forms.TableLayoutPanel> denetimleri kendi alt denetimleri düzenlemek ve kendilerini içeriklerini göre boyutu.</span><span class="sxs-lookup"><span data-stu-id="01368-128">The <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel> controls arrange their child controls and size themselves according to their contents.</span></span>|  
  
## <a name="layout-limitations"></a><span data-ttu-id="01368-129">Düzen sınırlamaları</span><span class="sxs-lookup"><span data-stu-id="01368-129">Layout Limitations</span></span>  
 <span data-ttu-id="01368-130">Genel olarak, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimleri ölçeklendirilebilir ve mümkün ölçülere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01368-130">In general, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls cannot be scaled and transformed to the extent possible in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="01368-131">Aşağıdaki listede bilinen sınırlamaları açıklar olduğunda <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi çalışır barındırılan tümleştirmek [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] içine denetim [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] düzen sistemi.</span><span class="sxs-lookup"><span data-stu-id="01368-131">The following list describes the known limitations when the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element attempts to integrate its hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control into the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout system.</span></span>  
  
-   <span data-ttu-id="01368-132">Bazı durumlarda, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimleri yeniden boyutlandırılamaz ya da yalnızca belirli boyutlara boyutlandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="01368-132">In some cases, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls cannot be resized, or can be sized only to specific dimensions.</span></span> <span data-ttu-id="01368-133">Örneğin, bir [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> denetimi denetimin yazı tipi boyutu tarafından tanımlanan yalnızca tek bir yüksekliği destekler.</span><span class="sxs-lookup"><span data-stu-id="01368-133">For example, a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> control supports only a single height, which is defined by the control's font size.</span></span> <span data-ttu-id="01368-134">İçinde bir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] burada öğeleri uzatma dikey olarak barındırılan dinamik düzen <xref:System.Windows.Forms.ComboBox> denetimi beklendiği gibi uzamaz.</span><span class="sxs-lookup"><span data-stu-id="01368-134">In a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dynamic layout where elements can stretch vertically, a hosted <xref:System.Windows.Forms.ComboBox> control will not stretch as expected.</span></span>  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="01368-135">denetimleri Döndürülmüş veya eğri.</span><span class="sxs-lookup"><span data-stu-id="01368-135"> controls cannot be rotated or skewed.</span></span> <span data-ttu-id="01368-136"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Öğesi başlatır <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> eğme veya döndürme dönüşümü uyguladığınızda olay.</span><span class="sxs-lookup"><span data-stu-id="01368-136">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event if you apply a skew or rotation transformation.</span></span> <span data-ttu-id="01368-137">Değil işlemek, <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> olay, bir <xref:System.InvalidOperationException> tetiklenir.</span><span class="sxs-lookup"><span data-stu-id="01368-137">If you do not handle the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event, an <xref:System.InvalidOperationException> is raised.</span></span>  
  
-   <span data-ttu-id="01368-138">Çoğu durumda, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimleri orantılı ölçeklendirmeyi desteklemez.</span><span class="sxs-lookup"><span data-stu-id="01368-138">In most cases, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls do not support proportional scaling.</span></span> <span data-ttu-id="01368-139">Denetimin genel boyutlarının ölçeklendirilmesine rağmen alt denetimleri ve bileşen öğeleri denetiminin beklendiği gibi yeniden boyutlandırılabilir değil.</span><span class="sxs-lookup"><span data-stu-id="01368-139">Although the overall dimensions of the control will scale, child controls and component elements of the control may not resize as expected.</span></span> <span data-ttu-id="01368-140">Bu sınırlama ne kadar iyi her bağlıdır [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimi, ölçeklendirmeyi destekler.</span><span class="sxs-lookup"><span data-stu-id="01368-140">This limitation depends on how well each [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control supports scaling.</span></span> <span data-ttu-id="01368-141">Ayrıca, ölçekleme olamaz [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimleri 0 piksel boyutunun aşağı kaydırın.</span><span class="sxs-lookup"><span data-stu-id="01368-141">In addition, you cannot scale [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls down to a size of 0 pixels.</span></span>  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="01368-142">denetimleri form otomatik olarak kendisini ve yazı tipi boyutuna bağlı denetimlerini yeniden otomatik ölçeklendirmeyi destekler.</span><span class="sxs-lookup"><span data-stu-id="01368-142"> controls support autoscaling, in which the form will automatically resize itself and its controls based on the font size.</span></span> <span data-ttu-id="01368-143">İçinde bir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kullanıcı arabirimi, yazı tipi boyutunu değiştirme değil yeniden boyutlandırma tüm düzeni ayrı ayrı öğeler dinamik olarak yeniden boyutlandırma ancak.</span><span class="sxs-lookup"><span data-stu-id="01368-143">In a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] user interface, changing the font size does not resize the entire layout, although individual elements may dynamically resize.</span></span>  
  
### <a name="z-order"></a><span data-ttu-id="01368-144">Z düzeni</span><span class="sxs-lookup"><span data-stu-id="01368-144">Z-order</span></span>  
 <span data-ttu-id="01368-145">İçinde bir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kullanıcı arabirimi öğelerinin z düzenini çakışan davranışı denetlemek için değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="01368-145">In a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] user interface, you can change the z-order of elements to control overlapping behavior.</span></span> <span data-ttu-id="01368-146">Barındırılan [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimi, ayrı bir HWND içinde çizilir, her zaman üstünde çizilir nedenle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] öğeleri.</span><span class="sxs-lookup"><span data-stu-id="01368-146">A hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is drawn in a separate HWND, so it is always drawn on top of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements.</span></span>  
  
 <span data-ttu-id="01368-147">Barındırılan [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimi de çizilir herhangi üstünde <xref:System.Windows.Documents.Adorner> öğeleri.</span><span class="sxs-lookup"><span data-stu-id="01368-147">A hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is also drawn on top of any <xref:System.Windows.Documents.Adorner> elements.</span></span>  
  
## <a name="layout-behavior"></a><span data-ttu-id="01368-148">Düzen davranışı</span><span class="sxs-lookup"><span data-stu-id="01368-148">Layout Behavior</span></span>  
 <span data-ttu-id="01368-149">Aşağıdaki düzen davranışının belirli yönlerini barındırdığında bölümlerde [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimlerini [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01368-149">The following sections describe specific aspects of layout behavior when hosting [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
### <a name="scaling-unit-conversion-and-device-independence"></a><span data-ttu-id="01368-150">Ölçeklendirme, birim dönüştürme ve cihaz bağımsızlığı</span><span class="sxs-lookup"><span data-stu-id="01368-150">Scaling, Unit Conversion, and Device Independence</span></span>  
 <span data-ttu-id="01368-151">Her <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi ilgili işlemler gerçekleştirdiğinde [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ve [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] boyutları, iki koordinat sistemi söz konusu: aygıttan bağımsız piksel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ve donanım piksel [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01368-151">Whenever the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element performs operations involving [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] dimensions, two coordinate systems are involved: device-independent pixels for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] and hardware pixels for [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="01368-152">Bu nedenle, tutarlı bir yerleşim elde etmek için uygun birim ve ölçeklendirme dönüşümlerini uygulamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="01368-152">Therefore, you must apply proper unit and scaling conversions to achieve a consistent layout.</span></span>  
  
 <span data-ttu-id="01368-153">Koordinat sistemleri arasında dönüştürme bağımlıdır geçerli aygıt çözünürlüğü ve herhangi bir düzeni veya uygulanan Dönüşümlerin işleme <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi veya alt öğelerinden.</span><span class="sxs-lookup"><span data-stu-id="01368-153">Conversion between the coordinate systems depends on the current device resolution and any layout or rendering transforms applied to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element or to its ancestors.</span></span>  
  
 <span data-ttu-id="01368-154">Çıktı aygıtı 96 DPI'de olması ve hiçbir ölçeklendirme uygulandıktan <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi, bir CİHAZDAN bağımsız piksel bir donanım piksel eşit.</span><span class="sxs-lookup"><span data-stu-id="01368-154">If the output device is 96 dpi and no scaling has been applied to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, one device-independent pixel is equal to one hardware pixel.</span></span>  
  
 <span data-ttu-id="01368-155">Diğer tüm durumlarda koordinat sistemi ölçeklendirmesini gerektirir.</span><span class="sxs-lookup"><span data-stu-id="01368-155">All other cases require coordinate system scaling.</span></span> <span data-ttu-id="01368-156">Barındırılan denetim yeniden boyutlandırıldı değil.</span><span class="sxs-lookup"><span data-stu-id="01368-156">The hosted control is not resized.</span></span> <span data-ttu-id="01368-157">Bunun yerine, <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi barındırılan denetim ve tüm alt denetimlerindeki ölçekleme dener.</span><span class="sxs-lookup"><span data-stu-id="01368-157">Instead, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element attempts to scale the hosted control and all of its child controls.</span></span> <span data-ttu-id="01368-158">Çünkü [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ölçeklendirme, tam olarak desteklemez <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi ölçeklendirir belirli denetimler tarafından desteklenen derecede.</span><span class="sxs-lookup"><span data-stu-id="01368-158">Because [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] does not fully support scaling, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element scales to the degree supported by particular controls.</span></span>  
  
 <span data-ttu-id="01368-159">Geçersiz kılma <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> barındırılan için özel ölçeklendirme davranışı sağlamak için yöntemi [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] denetim.</span><span class="sxs-lookup"><span data-stu-id="01368-159">Override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> method to provide custom scaling behavior for the hosted [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] control.</span></span>  
  
 <span data-ttu-id="01368-160">Ölçeklendirme, ek olarak <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi aşağıdaki tabloda açıklandığı gibi yuvarlama ve taşma durumlarını işler.</span><span class="sxs-lookup"><span data-stu-id="01368-160">In addition to scaling, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles rounding and overflow cases as described in the following table.</span></span>  
  
|<span data-ttu-id="01368-161">Dönüştürme sorunu</span><span class="sxs-lookup"><span data-stu-id="01368-161">Conversion issue</span></span>|<span data-ttu-id="01368-162">Açıklama</span><span class="sxs-lookup"><span data-stu-id="01368-162">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="01368-163">Yuvarlama</span><span class="sxs-lookup"><span data-stu-id="01368-163">Rounding</span></span>|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="01368-164">CİHAZDAN bağımsız piksel boyutları olarak belirtilen `double`, ve [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] donanım piksel boyutları olarak belirtilen `int`.</span><span class="sxs-lookup"><span data-stu-id="01368-164"> device-independent pixel dimensions are specified as `double`, and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hardware pixel dimensions are specified as `int`.</span></span> <span data-ttu-id="01368-165">Durumlarda nerede `double`-tabanlı boyutlara dönüştürüldüğü `int`-boyutları, temel <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi standart yuvarlama kullanır, böylece 0,5'den az olan kesirli değerlerin 0 aşağı yuvarlanmasını.</span><span class="sxs-lookup"><span data-stu-id="01368-165">In cases where `double`-based dimensions are converted to `int`-based dimensions, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element uses standard rounding, so that fractional values less than 0.5 are rounded down to 0.</span></span>|  
|<span data-ttu-id="01368-166">Taşma</span><span class="sxs-lookup"><span data-stu-id="01368-166">Overflow</span></span>|<span data-ttu-id="01368-167">Zaman <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi dönüştürür `double` değerler `int` değerleri taşma mümkündür.</span><span class="sxs-lookup"><span data-stu-id="01368-167">When the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element converts from `double` values to `int` values, overflow is possible.</span></span> <span data-ttu-id="01368-168">Daha büyük olan değerleri <xref:System.Int32.MaxValue> ayarlanır <xref:System.Int32.MaxValue>.</span><span class="sxs-lookup"><span data-stu-id="01368-168">Values that are larger than <xref:System.Int32.MaxValue> are set to <xref:System.Int32.MaxValue>.</span></span>|  
  
### <a name="layout-related-properties"></a><span data-ttu-id="01368-169">Düzen ilgili Özellikler</span><span class="sxs-lookup"><span data-stu-id="01368-169">Layout-related Properties</span></span>  
 <span data-ttu-id="01368-170">İçindeki düzen davranışını denetleyen özellikler [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimleri ve [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] öğeleri tarafından uygun şekilde eşleştirilir <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi.</span><span class="sxs-lookup"><span data-stu-id="01368-170">Properties that control layout behavior in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements are mapped appropriately by the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="01368-171">Daha fazla bilgi için bkz: [Windows Forms ve WPF özellik eşlemesi](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="01368-171">For more information, see [Windows Forms and WPF Property Mapping](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).</span></span>  
  
### <a name="layout-changes-in-the-hosted-control"></a><span data-ttu-id="01368-172">Barındırılan denetimde düzen değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="01368-172">Layout Changes in the Hosted Control</span></span>  
 <span data-ttu-id="01368-173">Düzen değişiklikleri barındırılan [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetim yayılır [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Düzen güncelleştirmelerini tetiklemek için.</span><span class="sxs-lookup"><span data-stu-id="01368-173">Layout changes in the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control are propagated to [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to trigger layout updates.</span></span> <span data-ttu-id="01368-174"><xref:System.Windows.UIElement.InvalidateMeasure%2A> Yöntemi <xref:System.Windows.Forms.Integration.WindowsFormsHost> denetimden düzen değişiklikleri neden sağlar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] çalıştırmak için yerleşim altyapısı.</span><span class="sxs-lookup"><span data-stu-id="01368-174">The <xref:System.Windows.UIElement.InvalidateMeasure%2A> method on <xref:System.Windows.Forms.Integration.WindowsFormsHost> ensures that layout changes in the hosted control cause the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine to run.</span></span>  
  
### <a name="continuously-sized-windows-forms-controls"></a><span data-ttu-id="01368-175">Sürekli olarak boyutlandırılan Windows Forms denetimleri</span><span class="sxs-lookup"><span data-stu-id="01368-175">Continuously Sized Windows Forms Controls</span></span>  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="01368-176">sürekli tam olarak ölçeklendirmeyi destekleyen denetimleri etkileşimde [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] düzen sistemi.</span><span class="sxs-lookup"><span data-stu-id="01368-176"> controls that support continuous scaling fully interact with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout system.</span></span> <span data-ttu-id="01368-177"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Öğesini kullanan <xref:System.Windows.FrameworkElement.MeasureOverride%2A> ve <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> her zamanki gibi boyutlandırmak ve barındırılan düzenlemek için yöntemleri [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetim.</span><span class="sxs-lookup"><span data-stu-id="01368-177">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods as usual to size and arrange the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
### <a name="sizing-algorithm"></a><span data-ttu-id="01368-178">Boyutlandırma algoritması</span><span class="sxs-lookup"><span data-stu-id="01368-178">Sizing Algorithm</span></span>  
 <span data-ttu-id="01368-179"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Öğesi barındırılan denetimi boyutlandırmak için aşağıdaki yordamı kullanır:</span><span class="sxs-lookup"><span data-stu-id="01368-179">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element uses the following procedure to size the hosted control:</span></span>  
  
1.  <span data-ttu-id="01368-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Öğesi geçersiz kılmaları <xref:System.Windows.FrameworkElement.MeasureOverride%2A> ve <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="01368-180">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element overrides the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span>  
  
2.  <span data-ttu-id="01368-181">Barındırılan denetime boyutunu belirlemek için <xref:System.Windows.FrameworkElement.MeasureOverride%2A> yöntemini çağırır barındırılan denetimin <xref:System.Windows.Forms.Control.GetPreferredSize%2A> yöntemi kısıtlamasına sahip çevrilen geçirilen kısıtlaması gelen <xref:System.Windows.FrameworkElement.MeasureOverride%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="01368-181">To determine the size of the hosted control, the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> method calls the hosted control's <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method with a constraint translated from the constraint passed to the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> method.</span></span>  
  
3.  <span data-ttu-id="01368-182"><xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Yöntemi, barındırılan denetimi verilen boyut kısıtlamasına ayarlamaya çalışır.</span><span class="sxs-lookup"><span data-stu-id="01368-182">The <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> method attempts to set the hosted control to the given size constraint.</span></span>  
  
4.  <span data-ttu-id="01368-183">Varsa barındırılan denetimin <xref:System.Windows.Forms.Control.Size%2A> özelliği eşleşen belirtilen sınırlama, barındırılan denetim kısıtlamaya boyutlandırılır.</span><span class="sxs-lookup"><span data-stu-id="01368-183">If the hosted control's <xref:System.Windows.Forms.Control.Size%2A> property matches the specified constraint, the hosted control is sized to the constraint.</span></span>  
  
 <span data-ttu-id="01368-184">Varsa <xref:System.Windows.Forms.Control.Size%2A> özelliği, belirtilen sınırlama eşleşmiyor, barındırılan denetim sürekli boyutlandırmayı desteklemez.</span><span class="sxs-lookup"><span data-stu-id="01368-184">If the <xref:System.Windows.Forms.Control.Size%2A> property does not match the specified constraint, the hosted control does not support continuous sizing.</span></span> <span data-ttu-id="01368-185">Örneğin, <xref:System.Windows.Forms.MonthCalendar> yalnızca ayrı boyutlara izin verir.</span><span class="sxs-lookup"><span data-stu-id="01368-185">For example, the <xref:System.Windows.Forms.MonthCalendar> control allows only discrete sizes.</span></span> <span data-ttu-id="01368-186">Bu denetim için izin verilen boyutlar, yükseklik ve genişlik için tamsayılardan (ay sayısını temsil eden) oluşur.</span><span class="sxs-lookup"><span data-stu-id="01368-186">The permitted sizes for this control consist of integers (representing the number of months) for both height and width.</span></span> <span data-ttu-id="01368-187">Bu gibi durumlarda <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi aşağıdaki gibi davranır:</span><span class="sxs-lookup"><span data-stu-id="01368-187">In cases such as this, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element behaves as follows:</span></span>  
  
-   <span data-ttu-id="01368-188">Varsa <xref:System.Windows.Forms.Control.Size%2A> özelliği döndürür belirtilen sınırlama daha büyük boyutu <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi barındırılan denetimi kırpar.</span><span class="sxs-lookup"><span data-stu-id="01368-188">If the <xref:System.Windows.Forms.Control.Size%2A> property returns a larger size than the specified constraint, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element clips the hosted control.</span></span> <span data-ttu-id="01368-189">Barındırılan denetim herhangi bir yönde kırpılmış gibi şekilde yükseklik ve genişlik ayrı ayrı işlenir.</span><span class="sxs-lookup"><span data-stu-id="01368-189">Height and width are handled separately, so the hosted control may be clipped in either direction.</span></span>  
  
-   <span data-ttu-id="01368-190">Varsa <xref:System.Windows.Forms.Control.Size%2A> özelliği döndürür belirtilen sınırlama daha küçük bir boyut <xref:System.Windows.Forms.Integration.WindowsFormsHost> bu boyut değerini kabul eder ve değerine döndürür [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] düzen sistemi.</span><span class="sxs-lookup"><span data-stu-id="01368-190">If the <xref:System.Windows.Forms.Control.Size%2A> property returns a smaller size than the specified constraint, <xref:System.Windows.Forms.Integration.WindowsFormsHost> accepts this size value and returns the value to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01368-191">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="01368-191">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="01368-192">İzlenecek yol: WPF içinde Windows Forms denetimleri düzenleme</span><span class="sxs-lookup"><span data-stu-id="01368-192">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-arranging-windows-forms-controls-in-wpf.md)  
 [<span data-ttu-id="01368-193">WPF örnek Forms denetimlerini pencereleri düzenleme</span><span class="sxs-lookup"><span data-stu-id="01368-193">Arranging Windows Forms Controls in WPF Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [<span data-ttu-id="01368-194">Windows Forms ve WPF özellik eşlemesi</span><span class="sxs-lookup"><span data-stu-id="01368-194">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="01368-195">Geçiş ve birlikte çalışabilirlik</span><span class="sxs-lookup"><span data-stu-id="01368-195">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)