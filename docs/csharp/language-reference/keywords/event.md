---
title: "event (C# Başvurusu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
helpviewer_keywords: event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f7e7f9f96714f8988eb91d77c63cc4f017d040f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="event-c-reference"></a><span data-ttu-id="d1f80-102">event (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="d1f80-102">event (C# Reference)</span></span>
<span data-ttu-id="d1f80-103">`event` Anahtar sözcüğü bir yayımcı sınıfı bir olayı bildirmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="d1f80-103">The `event` keyword is used to declare an event in a publisher class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1f80-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="d1f80-104">Example</span></span>  
 <span data-ttu-id="d1f80-105">Aşağıdaki örnek bildirme ve kullandığı bir olayı gösterilmektedir <xref:System.EventHandler> temel temsilci türü.</span><span class="sxs-lookup"><span data-stu-id="d1f80-105">The following example shows how to declare and raise an event that uses <xref:System.EventHandler> as the underlying delegate type.</span></span> <span data-ttu-id="d1f80-106">Ayrıca genel kullanmayı gösterir tam kod örneği için <xref:System.EventHandler%601> temsilci türü ve bir olaya abone ve bir olay işleyicisi yöntemi oluşturma, bkz: [nasıl yapılır: yayımlama olayları için .NET Framework yönergeleriyle bu Uydur](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="d1f80-106">For the complete code example that also shows how to use the generic <xref:System.EventHandler%601> delegate type and how to subscribe to an event and create an event handler method, see [How to: Publish Events that Conform to .NET Framework Guidelines](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]  
  
 <span data-ttu-id="d1f80-107">Yalnızca gelen sınıf veya yapı içinde çağrılabilir çok noktaya yayın temsilci özel bir tür (yayımcı sınıfı) burada bildirilen olaylardır.</span><span class="sxs-lookup"><span data-stu-id="d1f80-107">Events are a special kind of multicast delegate that can only be invoked from within the class or struct where they are declared (the publisher class).</span></span> <span data-ttu-id="d1f80-108">Diğer sınıflar ya da yapının olaya abone olursanız, yayımcı sınıfı olayını olduğunda olay işleyicisi yöntemleriyle çağrılır.</span><span class="sxs-lookup"><span data-stu-id="d1f80-108">If other classes or structs subscribe to the event, their event handler methods will be called when the publisher class raises the event.</span></span> <span data-ttu-id="d1f80-109">Daha fazla bilgi ve kod örnekleri için bkz: [olayları](../../../csharp/programming-guide/events/index.md) ve [Temsilciler](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="d1f80-109">For more information and code examples, see [Events](../../../csharp/programming-guide/events/index.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
 <span data-ttu-id="d1f80-110">Olayları işaretlenir olarak [ortak](../../../csharp/language-reference/keywords/public.md), [özel](../../../csharp/language-reference/keywords/private.md), [korumalı](../../../csharp/language-reference/keywords/protected.md), [iç](../../../csharp/language-reference/keywords/internal.md), [iç korumalı](../../../csharp/language-reference/keywords/protected-internal.md) veya [korumalı özel](../../../csharp/language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="d1f80-110">Events can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) or [private protected](../../../csharp/language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="d1f80-111">Bu erişim değiştiricileri sınıfı kullanıcılarının olay nasıl erişebileceğinizi tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="d1f80-111">These access modifiers define how users of the class can access the event.</span></span> <span data-ttu-id="d1f80-112">Daha fazla bilgi için bkz: [erişim değiştiricileri](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="d1f80-112">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="keywords-and-events"></a><span data-ttu-id="d1f80-113">Anahtar sözcükler ve olaylar</span><span class="sxs-lookup"><span data-stu-id="d1f80-113">Keywords and Events</span></span>  
 <span data-ttu-id="d1f80-114">Aşağıdaki anahtar sözcükler olaylarına uygulanır.</span><span class="sxs-lookup"><span data-stu-id="d1f80-114">The following keywords apply to events.</span></span>  
  
|<span data-ttu-id="d1f80-115">Anahtar sözcüğü</span><span class="sxs-lookup"><span data-stu-id="d1f80-115">Keyword</span></span>|<span data-ttu-id="d1f80-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="d1f80-116">Description</span></span>|<span data-ttu-id="d1f80-117">Daha fazla bilgi için</span><span class="sxs-lookup"><span data-stu-id="d1f80-117">For more information</span></span>|  
|-------------|-----------------|--------------------------|  
|[<span data-ttu-id="d1f80-118">statik</span><span class="sxs-lookup"><span data-stu-id="d1f80-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)|<span data-ttu-id="d1f80-119">Sınıfının hiçbir örneği varsa bile olay arayanlara herhangi bir zamanda kullanılabilmesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="d1f80-119">Makes the event available to callers at any time, even if no instance of the class exists.</span></span>|[<span data-ttu-id="d1f80-120">Statik sınıflar ve statik sınıf üyeleri</span><span class="sxs-lookup"><span data-stu-id="d1f80-120">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[<span data-ttu-id="d1f80-121">sanal</span><span class="sxs-lookup"><span data-stu-id="d1f80-121">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="d1f80-122">Kullanarak olay davranışını geçersiz kılmak türetilen sınıflar sağlar [geçersiz kılma](../../../csharp/language-reference/keywords/override.md) anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="d1f80-122">Allows derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span>|[<span data-ttu-id="d1f80-123">Devralma</span><span class="sxs-lookup"><span data-stu-id="d1f80-123">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[<span data-ttu-id="d1f80-124">korumalı</span><span class="sxs-lookup"><span data-stu-id="d1f80-124">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)|<span data-ttu-id="d1f80-125">İçin türetilen sınıflar, artık sanal olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="d1f80-125">Specifies that for derived classes it is no longer virtual.</span></span>||  
|[<span data-ttu-id="d1f80-126">Özet</span><span class="sxs-lookup"><span data-stu-id="d1f80-126">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="d1f80-127">Derleyici değil oluşturacak `add` ve `remove` olay erişimci blokları ve bu nedenle türetilen sınıflar, kendi uygulama sağlamalıdır.</span><span class="sxs-lookup"><span data-stu-id="d1f80-127">The compiler will not generate the `add` and `remove` event accessor blocks and therefore derived classes must provide their own implementation.</span></span>||  
  
 <span data-ttu-id="d1f80-128">Bir olay kullanarak statik bir olay olarak bildirilmelidir [statik](../../../csharp/language-reference/keywords/static.md) anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="d1f80-128">An event may be declared as a static event by using the [static](../../../csharp/language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="d1f80-129">Sınıfının hiçbir örneği mevcut olsa bile bu olay arayanlara herhangi bir zamanda kullanılabilmesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="d1f80-129">This makes the event available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="d1f80-130">Daha fazla bilgi için bkz: [statik sınıflar ve statik sınıf üyeleri](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="d1f80-130">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="d1f80-131">Bir olay kullanarak sanal bir olay olarak işaretlenebilir [sanal](../../../csharp/language-reference/keywords/virtual.md) anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="d1f80-131">An event can be marked as a virtual event by using the [virtual](../../../csharp/language-reference/keywords/virtual.md) keyword.</span></span> <span data-ttu-id="d1f80-132">Bu kullanarak olay davranışını geçersiz kılmak türetilen sınıflar sağlar [geçersiz kılma](../../../csharp/language-reference/keywords/override.md) anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="d1f80-132">This enables derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span> <span data-ttu-id="d1f80-133">Daha fazla bilgi için bkz: [devralma](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="d1f80-133">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span> <span data-ttu-id="d1f80-134">Sanal bir olay geçersiz kılma bir olay da olabilir [korumalı](../../../csharp/language-reference/keywords/sealed.md), için türetilen sınıflar, artık sanal olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="d1f80-134">An event overriding a virtual event can also be [sealed](../../../csharp/language-reference/keywords/sealed.md), which specifies that for derived classes it is no longer virtual.</span></span> <span data-ttu-id="d1f80-135">Son olarak, bir olay bildirilebilir [soyut](../../../csharp/language-reference/keywords/abstract.md), derleyici değil oluşturacak anlamına `add` ve `remove` olay erişimci engeller.</span><span class="sxs-lookup"><span data-stu-id="d1f80-135">Lastly, an event can be declared [abstract](../../../csharp/language-reference/keywords/abstract.md), which means that the compiler will not generate the `add` and `remove` event accessor blocks.</span></span> <span data-ttu-id="d1f80-136">Bu nedenle türetilen sınıflar, kendi uygulama sağlaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="d1f80-136">Therefore derived classes must provide their own implementation.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d1f80-137">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="d1f80-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d1f80-138">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d1f80-138">See Also</span></span>  
 [<span data-ttu-id="d1f80-139">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="d1f80-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d1f80-140">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="d1f80-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d1f80-141">C# anahtar sözcükleri</span><span class="sxs-lookup"><span data-stu-id="d1f80-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d1f80-142">ekleme</span><span class="sxs-lookup"><span data-stu-id="d1f80-142">add</span></span>](../../../csharp/language-reference/keywords/add.md)  
 [<span data-ttu-id="d1f80-143">Kaldır</span><span class="sxs-lookup"><span data-stu-id="d1f80-143">remove</span></span>](../../../csharp/language-reference/keywords/remove.md)  
 [<span data-ttu-id="d1f80-144">Değiştiriciler</span><span class="sxs-lookup"><span data-stu-id="d1f80-144">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="d1f80-145">Nasıl yapılır: temsilcileri (çok noktaya yayın temsilcileri) birleştirme</span><span class="sxs-lookup"><span data-stu-id="d1f80-145">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)