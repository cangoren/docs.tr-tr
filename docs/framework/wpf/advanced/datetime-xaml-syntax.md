---
title: "DateTime XAML Sözdizimi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55e261018e6c7b9fea9ad449c5e92a131df40807
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="datetime-xaml-syntax"></a><span data-ttu-id="7586c-102">DateTime XAML Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7586c-102">DateTime XAML Syntax</span></span>
<span data-ttu-id="7586c-103">Gibi bazı denetimleri <xref:System.Windows.Controls.Calendar> ve <xref:System.Windows.Controls.DatePicker>, kullanın özelliklere sahip <xref:System.DateTime> türü.</span><span class="sxs-lookup"><span data-stu-id="7586c-103">Some controls, such as <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>, have properties that use the <xref:System.DateTime> type.</span></span> <span data-ttu-id="7586c-104">Genellikle bir ilk tarih veya saat bu denetimleri için arka plan kodu çalışma zamanında belirttiğiniz karşın, bir başlangıç tarih veya saat XAML'de belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7586c-104">Although you typically specify an initial date or time for these controls in the code-behind at run time, you can specify an initial date or time in XAML.</span></span> <span data-ttu-id="7586c-105">WPF XAML ayrıştırıcısı ayrıştırılmasını işler <xref:System.DateTime> değerlerini yerleşik XAML metin sözdizimini kullanarak.</span><span class="sxs-lookup"><span data-stu-id="7586c-105">The WPF XAML parser handles parsing of <xref:System.DateTime> values using a built-in XAML text syntax.</span></span> <span data-ttu-id="7586c-106">Bu konuda, özelliklerini açıklanmaktadır <xref:System.DateTime> XAML metin sözdizimi.</span><span class="sxs-lookup"><span data-stu-id="7586c-106">This topic describes the specifics of the <xref:System.DateTime> XAML text syntax.</span></span>  
  
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a><span data-ttu-id="7586c-107">DateTime XAML sözdiziminin kullanıldığı durumlar</span><span class="sxs-lookup"><span data-stu-id="7586c-107">When To Use DateTime XAML Syntax</span></span>  
 <span data-ttu-id="7586c-108">XAML'de tarihleri ayarlamak her zaman gerekli değildir ve hatta tercih edilebilir değil.</span><span class="sxs-lookup"><span data-stu-id="7586c-108">Setting dates in XAML is not always necessary and may not even be desirable.</span></span> <span data-ttu-id="7586c-109">Örneğin, kullanabilirsiniz <xref:System.DateTime.Now%2A?displayProperty=nameWithType> çalıştırma veya bir tarihte başlatmak için özellik yapmak tüm tarih ayarlamaları Takvim kullanıcı girişini temel alarak arka plan kod içinde.</span><span class="sxs-lookup"><span data-stu-id="7586c-109">For example, you could use the <xref:System.DateTime.Now%2A?displayProperty=nameWithType> property to initialize a date at run time, or you could do all your date adjustments for a calendar in the code-behind based on user input.</span></span> <span data-ttu-id="7586c-110">Ancak, burada isteyebilirsiniz kod sabit tarihler senaryolar vardır bir <xref:System.Windows.Controls.Calendar> ve <xref:System.Windows.Controls.DatePicker> bir denetim şablonu içinde.</span><span class="sxs-lookup"><span data-stu-id="7586c-110">However, there are scenarios where you may want to hard-code dates into a <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker> in a control template.</span></span> <span data-ttu-id="7586c-111"><xref:System.DateTime> XAML sözdizimi bu senaryoları için kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="7586c-111">The <xref:System.DateTime> XAML syntax must be used for these scenarios.</span></span>  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a><span data-ttu-id="7586c-112">DateTime XAML sözdizimi yerel bir davranıştır</span><span class="sxs-lookup"><span data-stu-id="7586c-112">DateTime XAML Syntax is a Native Behavior</span></span>  
 <span data-ttu-id="7586c-113"><xref:System.DateTime>CLR temel sınıf kitaplıklarında tanımlı bir sınıftır.</span><span class="sxs-lookup"><span data-stu-id="7586c-113"><xref:System.DateTime> is a class that is defined in the base class libraries of the CLR.</span></span> <span data-ttu-id="7586c-114">Taban sınıf kitaplıkları CLR geri kalanı için ne ilişkili nedeniyle, bu uygulamak mümkün değildir <xref:System.ComponentModel.TypeConverterAttribute> sınıfı ve kullanımına XAML dizelerden işlemek ve bunlara dönüştürmek için tür dönüştürücüsünü <xref:System.DateTime> çalışma zamanı nesne modeli.</span><span class="sxs-lookup"><span data-stu-id="7586c-114">Because of how the base class libraries relate to the rest of the CLR, it is not possible to apply <xref:System.ComponentModel.TypeConverterAttribute> to the class and use a type converter to process strings from XAML and convert them to <xref:System.DateTime> in the run time object model.</span></span> <span data-ttu-id="7586c-115">Yoktur hiçbir `DateTimeConverter` sınıfı dönüştürme davranış sağlar; bu konuda açıklanan dönüştürme WPF XAML ayrıştırıcısı yerel bir davranıştır.</span><span class="sxs-lookup"><span data-stu-id="7586c-115">There is no `DateTimeConverter` class that provides the conversion behavior; the conversion behavior described in this topic is native to the WPF XAML parser.</span></span>  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a><span data-ttu-id="7586c-116">DateTime XAML için biçim dizeleri</span><span class="sxs-lookup"><span data-stu-id="7586c-116">Format Strings for DateTime XAML Syntax</span></span>  
 <span data-ttu-id="7586c-117">Biçimi belirtebilirsiniz bir <xref:System.DateTime> ile bir biçim dizesi.</span><span class="sxs-lookup"><span data-stu-id="7586c-117">You can specify the format of a <xref:System.DateTime> with a format string.</span></span> <span data-ttu-id="7586c-118">Biçim dizeleri bir değer oluşturmak için kullanılan metin sözdizimini resmileştirin.</span><span class="sxs-lookup"><span data-stu-id="7586c-118">Format strings formalize the text syntax that can be used to create a value.</span></span> <span data-ttu-id="7586c-119"><xref:System.DateTime>tarih bileşenlerini genellikle yalnızca varolan WPF denetimleri için değerleri <xref:System.DateTime> ve zaman bileşenlerini değil.</span><span class="sxs-lookup"><span data-stu-id="7586c-119"><xref:System.DateTime> values for the existing WPF controls generally only use the date components of <xref:System.DateTime> and not the time components.</span></span>  
  
 <span data-ttu-id="7586c-120">Belirtirken bir <xref:System.DateTime> XAML içinde herhangi bir biçim dizeleri birbirinin yerine kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7586c-120">When specifying a <xref:System.DateTime> in XAML, you can use any of the format strings interchangeably.</span></span>  
  
 <span data-ttu-id="7586c-121">Biçimleri ve bu konuda özellikle gösterilmeyen biçim dizeleri de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7586c-121">You can also use formats and format strings that are not specifically shown in this topic.</span></span> <span data-ttu-id="7586c-122">Teknik olarak, herhangi bir için XAML <xref:System.DateTime> belirtilen ve daha sonra WPF XAML tarafından ayrıştırılan değeri bir iç çağrısı kullanır <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, bu nedenle kabul eden herhangi bir dize kullanabilirsiniz <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> XAML girişiniz için.</span><span class="sxs-lookup"><span data-stu-id="7586c-122">Technically, the XAML for any <xref:System.DateTime> value that is specified and then parsed by the WPF XAML parser uses an internal  call to <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, therefore you could use any string accepted by <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> for your XAML input.</span></span> <span data-ttu-id="7586c-123">Daha fazla bilgi için bkz. <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7586c-123">For more information, see <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7586c-124">DateTime XAML sözdizimi her zaman kullanır `en-us` olarak <xref:System.Globalization.CultureInfo> kendi yerel dönüşümü için.</span><span class="sxs-lookup"><span data-stu-id="7586c-124">The DateTime XAML syntax always uses `en-us` as the <xref:System.Globalization.CultureInfo> for its native conversion.</span></span> <span data-ttu-id="7586c-125">Bu tarafından etkilenir değil <xref:System.Windows.FrameworkElement.Language%2A> değeri veya `xml:lang` XAML öznitelik düzeyi tür dönüştürme bu bağlam olmaksızın davrandığından XAML'de değeri.</span><span class="sxs-lookup"><span data-stu-id="7586c-125">This is not influenced by <xref:System.Windows.FrameworkElement.Language%2A> value or `xml:lang` value in the XAML, because XAML attribute-level type conversion acts without that context.</span></span> <span data-ttu-id="7586c-126">Ay ve gün görünme sırasını gibi kültürel farklılıkları nedeniyle burada gösterilen biçim dizeleri kesinti denemeyin.</span><span class="sxs-lookup"><span data-stu-id="7586c-126">Do not attempt to interpolate the format strings shown here due to cultural variations, such as the order in which day and month appear.</span></span> <span data-ttu-id="7586c-127">Burada gösterilen biçim dizeleri diğer kültür ayarlarından bağımsız olarak XAML ayrıştırılırken kullanılan tam biçim dizelerdir.</span><span class="sxs-lookup"><span data-stu-id="7586c-127">The format strings shown here are the exact format strings used when parsing the XAML regardless of other culture settings.</span></span>  
  
 <span data-ttu-id="7586c-128">Aşağıdaki bölümlerde bazı yaygın açıklanmaktadır <xref:System.DateTime> biçim dizeleri.</span><span class="sxs-lookup"><span data-stu-id="7586c-128">The following sections describe some of the common <xref:System.DateTime> format strings.</span></span>  
  
### <a name="short-date-pattern-d"></a><span data-ttu-id="7586c-129">Kısa tarih deseni ("d")</span><span class="sxs-lookup"><span data-stu-id="7586c-129">Short Date Pattern ("d")</span></span>  
 <span data-ttu-id="7586c-130">Aşağıdaki kısa tarih biçiminde gösteren bir <xref:System.DateTime> XAML'de:</span><span class="sxs-lookup"><span data-stu-id="7586c-130">The following shows the short date format for a <xref:System.DateTime> in XAML:</span></span>  
  
 `M/d/YYYY`  
  
 <span data-ttu-id="7586c-131">Bu, tipik kullanımlar için gerekli tüm bilgileri WPF denetimleri tarafından belirtir ve yanlışlıkla saat dilimi kaymasını ile saat bileşeni tarafından etkilenmez ve bu nedenle diğer biçimlere göre önerilen en basit biçimidir.</span><span class="sxs-lookup"><span data-stu-id="7586c-131">This is the simplest form that specifies all necessary information for typical usages by WPF controls, and cannot be influenced by accidental time zone offsets versus a time component, and is therefore recommended over the other formats.</span></span>  
  
 <span data-ttu-id="7586c-132">Örneğin, 1 Haziran 2010 tarihini belirtmek için aşağıdaki dizeyi kullanın:</span><span class="sxs-lookup"><span data-stu-id="7586c-132">For example, to specify the date of June 1, 2010, use the following string:</span></span>  
  
 `3/1/2010`  
  
 <span data-ttu-id="7586c-133">Daha fazla bilgi için bkz. <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7586c-133">For more information, see <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="sortable-datetime-pattern-s"></a><span data-ttu-id="7586c-134">Sıralanabilir DateTime modeli ("s")</span><span class="sxs-lookup"><span data-stu-id="7586c-134">Sortable DateTime Pattern ("s")</span></span>  
 <span data-ttu-id="7586c-135">Aşağıdaki sıralanabilir gösterir <xref:System.DateTime> XAML desende:</span><span class="sxs-lookup"><span data-stu-id="7586c-135">The following shows the sortable <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 <span data-ttu-id="7586c-136">Örneğin, 1 Haziran 2010 tarihini belirtmek için aşağıdaki dizeyi (zamanı bileşenleri tüm 0 olarak girilir) kullanın:</span><span class="sxs-lookup"><span data-stu-id="7586c-136">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a><span data-ttu-id="7586c-137">RFC1123 modeli ("r")</span><span class="sxs-lookup"><span data-stu-id="7586c-137">RFC1123 Pattern ("r")</span></span>  
 <span data-ttu-id="7586c-138">Ayrıca kültür nedenleri için RFC1123 modeli kullanan diğer tarih oluşturucuları dize girişten olabileceğinden RFC1123 modeli yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="7586c-138">The RFC1123 pattern is useful because it could be a string input from other date generators that also use the RFC1123 pattern for culture invariant reasons.</span></span> <span data-ttu-id="7586c-139">Aşağıdaki RFC1123 gösterir <xref:System.DateTime> XAML desende:</span><span class="sxs-lookup"><span data-stu-id="7586c-139">The following shows the RFC1123 <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 <span data-ttu-id="7586c-140">Örneğin, 1 Haziran 2010 tarihini belirtmek için aşağıdaki dizeyi (zamanı bileşenleri tüm 0 olarak girilir) kullanın:</span><span class="sxs-lookup"><span data-stu-id="7586c-140">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a><span data-ttu-id="7586c-141">Diğer biçimler ve modeller</span><span class="sxs-lookup"><span data-stu-id="7586c-141">Other Formats and Patterns</span></span>  
 <span data-ttu-id="7586c-142">Önceden belirtildiği gibi bir <xref:System.DateTime> XAML'de kabul edilebilir olan herhangi bir dize belirtilmesi için giriş olarak <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7586c-142">As stated previously, a <xref:System.DateTime> in XAML can be specified as any string that is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7586c-143">Bu, diğer şekillendirilmiş biçimleri içerir (örneğin <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) ve belirli bir HTTP'dir değil biçimleri <xref:System.Globalization.DateTimeFormatInfo> formu.</span><span class="sxs-lookup"><span data-stu-id="7586c-143">This includes other formalized formats (for example <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), and formats that are not formalized as a particular <xref:System.Globalization.DateTimeFormatInfo> form.</span></span> <span data-ttu-id="7586c-144">Örneğin, form `YYYY/mm/dd` kabul edilebilir için giriş olarak <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7586c-144">For example, the form `YYYY/mm/dd` is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7586c-145">Bu konu, çalışan ve bunun yerine standart bir yöntem olarak kısa tarih düzeni önerir tüm olası biçimleri açıklamaya denemez.</span><span class="sxs-lookup"><span data-stu-id="7586c-145">This topic does not attempt to describe all possible formats that work, and instead recommends the short date pattern as a standard practice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7586c-146">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7586c-146">See Also</span></span>  
 [<span data-ttu-id="7586c-147">XAML genel bakış (WPF)</span><span class="sxs-lookup"><span data-stu-id="7586c-147">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)