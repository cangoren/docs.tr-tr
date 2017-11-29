---
title: Devralma Temelleri (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76813bb36c0bcf75791932a0fec081f0fc1958e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="4cfaf-102">Devralma Temelleri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cfaf-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="4cfaf-103">`Inherits` Deyimi adında yeni bir sınıf bildirmek için kullanılan bir *türetilmiş sınıf*, olarak bilinen varolan bir sınıfa göre bir *temel sınıfı*.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="4cfaf-104">Türetilen sınıflar devralır ve genişletebilir, özellikleri, yöntemleri, olayları, alanları ve taban sınıf içinde tanımlı sabitler.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="4cfaf-105">Aşağıdaki bölümde devralma kurallarını bazıları açıklanır ve yol sınıflarını değiştirmek için kullanabileceğiniz değiştiriciler devralır veya devralınan:</span><span class="sxs-lookup"><span data-stu-id="4cfaf-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
-   <span data-ttu-id="4cfaf-106">Varsayılan olarak, tüm sınıflar ile işaretlenen sürece devralınabilir `NotInheritable` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="4cfaf-107">Sınıfları projenizdeki diğer sınıflardan veya projenizin başvuran diğer derlemelerde sınıflardan devralabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
-   <span data-ttu-id="4cfaf-108">Birden çok devralma izin dilleri aksine [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sınıflarda; yalnızca tek devralma verir türetilen sınıflar yalnızca bir temel sınıf başka bir deyişle, olabilir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-108">Unlike languages that allow multiple inheritance, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="4cfaf-109">Birden çok devralma sınıflarda izin verilmez ancak sınıflar aynı uçları etkili bir şekilde gerçekleştirebilirsiniz birden çok arabirimleri uygulayabilir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
-   <span data-ttu-id="4cfaf-110">Bir taban sınıf kısıtlı öğelerde gösterilmesini önlemek için türetilmiş bir sınıf erişim türünü eşit veya onun temel sınıfı daha kısıtlayıcı olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="4cfaf-111">Örneğin, bir `Public` olamaz sınıf devralma bir `Friend` veya `Private` sınıfı ve bir `Friend` olamaz sınıf devralma bir `Private` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="4cfaf-112">Devralma değiştiricileri</span><span class="sxs-lookup"><span data-stu-id="4cfaf-112">Inheritance Modifiers</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="4cfaf-113">Aşağıdaki sınıf düzeyi ifadeleri ve devralma desteklemek için değiştiricileri sunar:</span><span class="sxs-lookup"><span data-stu-id="4cfaf-113"> introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
-   <span data-ttu-id="4cfaf-114">`Inherits`deyimi — temel sınıfı belirtir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-114">`Inherits` statement — Specifies the base class.</span></span>  
  
-   <span data-ttu-id="4cfaf-115">`NotInheritable`Değiştirici — programcıları sınıfın temel sınıf olarak kullanmalarını engeller.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
-   <span data-ttu-id="4cfaf-116">`MustInherit`Değiştirici — sınıfı yalnızca temel sınıf olarak kullanılmak üzere tasarlanmıştır belirtir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="4cfaf-117">Örneklerini `MustInherit` sınıfları doğrudan oluşturulamıyor; bunlar yalnızca türetilmiş bir sınıf olarak temel sınıf örneklerinin oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="4cfaf-118">(C++ ve C# gibi diğer programlama dilleri terim kullanın *soyut sınıf* böyle bir sınıfın açıklamak için.)</span><span class="sxs-lookup"><span data-stu-id="4cfaf-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="4cfaf-119">Geçersiz kılma özellikleri ve yöntemleri türetilmiş sınıflarda</span><span class="sxs-lookup"><span data-stu-id="4cfaf-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="4cfaf-120">Varsayılan olarak, türetilmiş bir sınıf kendi temel sınıfından özellikleri ve yöntemleri devralır.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="4cfaf-121">Devralınan özellik veya yöntem türetilen sınıfta farklı şekilde davranmasına içeriyorsa olabilir *geçersiz*.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="4cfaf-122">Diğer bir deyişle, yeni bir uygulama yönteminin türetilen sınıfta tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="4cfaf-123">Aşağıdaki değiştiricileri özellikleri ve yöntemleri nasıl geçersiz kılınır denetlemek için kullanılır:</span><span class="sxs-lookup"><span data-stu-id="4cfaf-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
-   <span data-ttu-id="4cfaf-124">`Overridable`— Türetilen bir sınıfta geçersiz kılınmak üzere bir sınıfta bir özellik veya yöntem sağlar.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
-   <span data-ttu-id="4cfaf-125">`Overrides`— Geçersiz kılar bir `Overridable` özellik veya yöntem temel sınıfında tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
-   <span data-ttu-id="4cfaf-126">`NotOverridable`— Türetilen bir sınıfta geçersiz bir özellik veya yöntem engeller.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="4cfaf-127">Varsayılan olarak, `Public` yöntemleri `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
-   <span data-ttu-id="4cfaf-128">`MustOverride`— Türetilmiş bir sınıf özellik veya yöntem geçersiz gerektirir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="4cfaf-129">Zaman `MustOverride` anahtar sözcüğü kullanılır, yöntem tanımı oluşan yalnızca `Sub`, `Function`, veya `Property` deyimi.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="4cfaf-130">Diğer bir deyime izin ve özellikle olmadığından hiçbir `End Sub` veya `End Function` deyimi.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="4cfaf-131">`MustOverride`yöntemleri bildirilmelidir `MustInherit` sınıfları.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="4cfaf-132">Bordro işlemek için sınıflar tanımlamak istediğinizi varsayalım.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="4cfaf-133">Genel tanımlayabilirsiniz `Payroll` içeren sınıf bir `RunPayroll` için tipik bir hafta Bordro hesaplar yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="4cfaf-134">Daha sonra kullanabilirsiniz `Payroll` daha özelleştirilmiş için temel sınıf olarak `BonusPayroll` çalışan ikramiyeler dağıtırken kullanılabilir sınıfı.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="4cfaf-135">`BonusPayroll` Sınıfı devralır ve geçersiz kılma, `PayEmployee` Bankası'nda tanımlanan yöntemi `Payroll` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="4cfaf-136">Aşağıdaki örnek, bir temel sınıf tanımlar `Payroll,` ve türetilmiş bir sınıf `BonusPayroll`, devralınan bir yöntemini geçersiz kılar `PayEmployee`.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="4cfaf-137">Yordamı, bir `RunPayroll`, oluşturur ve ardından geçirir bir `Payroll` nesne ve `BonusPayroll` bir işlev nesnesine `Pay`, yürütmelerinin `PayEmployee` yöntemi her iki nesne.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 [!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="4cfaf-138">MyBase anahtar sözcüğü</span><span class="sxs-lookup"><span data-stu-id="4cfaf-138">The MyBase Keyword</span></span>  
 <span data-ttu-id="4cfaf-139">`MyBase` Anahtar sözcüğü sınıfının geçerli örneği taban sınıfına başvuruyor bir nesne değişkeni gibi davranır.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="4cfaf-140">`MyBase`sık sık geçersiz kılınan veya türetilen bir sınıfta gölgeli taban sınıfı üyeleri erişmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="4cfaf-141">Özellikle, `MyBase.New` açıkça bir temel sınıf oluşturucu türetilmiş bir sınıf oluşturucudan çağırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="4cfaf-142">Örneğin, taban sınıfından devralınan bir yöntemini geçersiz kılar türetilmiş bir sınıf tasarlama varsayalım.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="4cfaf-143">Geçersiz kılınan yöntemi taban sınıf içinde yöntemini çağırın ve aşağıdaki kod parçasında gösterildiği gibi dönüş değerini değiştirin:</span><span class="sxs-lookup"><span data-stu-id="4cfaf-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 <span data-ttu-id="4cfaf-144">Aşağıdaki listede kullanarak kısıtlamaları açıklar `MyBase`:</span><span class="sxs-lookup"><span data-stu-id="4cfaf-144">The following list describes restrictions on using `MyBase`:</span></span>  
  
-   <span data-ttu-id="4cfaf-145">`MyBase`hemen temel sınıfını hem de devralınan üyeleri anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="4cfaf-146">Bu kullanılamaz erişimi `Private` sınıfı üyeleri.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-146">It cannot be used to access `Private` members in the class.</span></span>  
  
-   <span data-ttu-id="4cfaf-147">`MyBase`gerçek bir nesne bir anahtar sözcüktür.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="4cfaf-148">`MyBase`bir değişkene atanır, yordamlara geçirilen veya değiştirilemez kullanılan bir `Is` karşılaştırması.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="4cfaf-149">Yöntemi, `MyBase` niteleyen hemen taban sınıf içinde; tanımlanması gerekmez yerine dolaylı olarak devralınan bir taban sınıf içinde tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="4cfaf-150">Nitelenen başvurusu için sırayla `MyBase` doğru şekilde derlenmesi için bazı temel sınıf adını ve çağrıda görünen parametre türlerini eşleşen bir yöntem içermelidir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
-   <span data-ttu-id="4cfaf-151">Kullanamazsınız `MyBase` çağırmak için `MustOverride` taban sınıf yöntemlerini.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
-   <span data-ttu-id="4cfaf-152">`MyBase`kendisini nitelemek için kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="4cfaf-153">Bu nedenle, aşağıdaki kodu geçerli değil:</span><span class="sxs-lookup"><span data-stu-id="4cfaf-153">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   <span data-ttu-id="4cfaf-154">`MyBase`modülleri kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-154">`MyBase` cannot be used in modules.</span></span>  
  
-   <span data-ttu-id="4cfaf-155">`MyBase`olarak işaretlenmiş taban sınıfı üyeleri erişmek için kullanılamaz `Friend` temel sınıfı farklı bir derlemede ise.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="4cfaf-156">Daha fazla bilgi ve başka bir örnek için bkz: [nasıl yapılır: değişken gizli türetilmiş bir sınıf tarafından erişim](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="4cfaf-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="4cfaf-157">MyClass anahtar sözcüğü</span><span class="sxs-lookup"><span data-stu-id="4cfaf-157">The MyClass Keyword</span></span>  
 <span data-ttu-id="4cfaf-158">`MyClass` Anahtar sözcüğü olarak ilk olarak uygulanan bir sınıfın örneğini ifade geçerli bir nesne değişkeni gibi davranır.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="4cfaf-159">`MyClass`benzer `Me`, ancak her yöntem ve özellik çağrı üzerinde `MyClass` yöntemi veya özelliği değilmiş gibi davranılır [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="4cfaf-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="4cfaf-160">Bu nedenle, yöntemi veya özelliği türetilen bir sınıfta geçersiz kılarak etkilenmez.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
-   <span data-ttu-id="4cfaf-161">`MyClass`gerçek bir nesne bir anahtar sözcüktür.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="4cfaf-162">`MyClass`bir değişkene atanır, yordamlara geçirilen veya değiştirilemez kullanılan bir `Is` karşılaştırması.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="4cfaf-163">`MyClass`kapsayan sınıfı hem de devralınan üyeleri anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-163">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
-   <span data-ttu-id="4cfaf-164">`MyClass`Niteleyici için olarak kullanılan `Shared` üyeleri.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
-   <span data-ttu-id="4cfaf-165">`MyClass`içinde kullanılamaz bir `Shared` yöntemi, ancak paylaşılan bir sınıf üyesi erişmek için bir örnek yöntemi içinde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
-   <span data-ttu-id="4cfaf-166">`MyClass`Standart modüller kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-166">`MyClass` cannot be used in standard modules.</span></span>  
  
-   <span data-ttu-id="4cfaf-167">`MyClass`taban sınıf içinde tanımlanır ve bu sınıfta sağlanan yönteminin uygulaması olan bir yöntem nitelemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="4cfaf-168">Böyle bir başvuru olarak ile aynı anlamı taşır `MyBase.` *yöntemi*.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="4cfaf-169">Aşağıdaki örnek karşılaştırır `Me` ve `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-169">The following example compares `Me` and `MyClass`.</span></span>  
  
```vb
Class baseClass  
    Public Overridable Sub testMethod()  
        MsgBox("Base class string")  
    End Sub  
    Public Sub useMe()  
        ' The following call uses the calling class's method, even if   
        ' that method is an override.  
        Me.testMethod()  
    End Sub  
    Public Sub useMyClass()  
        ' The following call uses this instance's method and not any  
        ' override.  
        MyClass.testMethod()  
    End Sub  
End Class  
Class derivedClass : Inherits baseClass  
    Public Overrides Sub testMethod()  
        MsgBox("Derived class string")  
    End Sub  
End Class  
Class testClasses  
    Sub startHere()  
        Dim testObj As derivedClass = New derivedClass()  
        ' The following call displays "Derived class string".  
        testObj.useMe()  
        ' The following call displays "Base class string".  
        testObj.useMyClass()  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="4cfaf-170">Olsa bile `derivedClass` geçersiz kılmaları `testMethod`, `MyClass` anahtar sözcük `useMyClass` geçersiz kılma ve derleyici çözümler etkileri temel sınıf sürümü çağrısı nullifies `testMethod`.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cfaf-171">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4cfaf-171">See Also</span></span>  
 [<span data-ttu-id="4cfaf-172">Inherits deyimi</span><span class="sxs-lookup"><span data-stu-id="4cfaf-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="4cfaf-173">Me, My, MyBase ve MyClass</span><span class="sxs-lookup"><span data-stu-id="4cfaf-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)