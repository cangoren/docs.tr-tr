---
title: "Öznitelik Listesi (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adfb980380bb787280715ca0185950657e174eb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="321b6-102">Öznitelik Listesi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="321b6-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="321b6-103">Bildirilen bir programlama öğesi uygulanacak özniteliklerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="321b6-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="321b6-104">Birden çok öznitelik virgülle ayrılır.</span><span class="sxs-lookup"><span data-stu-id="321b6-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="321b6-105">Aşağıdaki bir öznitelik sözdizimi aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="321b6-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="321b6-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="321b6-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="321b6-107">Bölümler</span><span class="sxs-lookup"><span data-stu-id="321b6-107">Parts</span></span>  
 `attributemodifier`  
 <span data-ttu-id="321b6-108">Bir kaynak dosyasının başında uygulanan öznitelikleri için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="321b6-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="321b6-109">Olabilir [derleme](../../../visual-basic/language-reference/modifiers/assembly.md) veya [Modülü](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="321b6-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>  
  
 `attributename`  
 <span data-ttu-id="321b6-110">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="321b6-110">Required.</span></span> <span data-ttu-id="321b6-111">Özniteliğin adı.</span><span class="sxs-lookup"><span data-stu-id="321b6-111">Name of the attribute.</span></span>  
  
 `attributearguments`  
 <span data-ttu-id="321b6-112">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="321b6-112">Optional.</span></span> <span data-ttu-id="321b6-113">Bu öznitelik için konumsal bağımsız değişkenler listesi.</span><span class="sxs-lookup"><span data-stu-id="321b6-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="321b6-114">Birden çok bağımsız değişkenleri virgülle ayrılır.</span><span class="sxs-lookup"><span data-stu-id="321b6-114">Multiple arguments are separated by commas.</span></span>  
  
 `attributeinitializer`  
 <span data-ttu-id="321b6-115">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="321b6-115">Optional.</span></span> <span data-ttu-id="321b6-116">Bu öznitelik için değişkenin veya özelliğin başlatıcıları listesi.</span><span class="sxs-lookup"><span data-stu-id="321b6-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="321b6-117">Birden çok başlatıcıları virgülle ayrılır.</span><span class="sxs-lookup"><span data-stu-id="321b6-117">Multiple initializers are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="321b6-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="321b6-118">Remarks</span></span>  
 <span data-ttu-id="321b6-119">Neredeyse tüm programlama öğeye (türleri, yordamlar, özellikleri ve benzeri) bir veya daha fazla öznitelik uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="321b6-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="321b6-120">Öznitelikleri, derlemenin meta verilerde görünür ve kodunuzu açıklama veya belirli bir programlama öğesinin nasıl kullanılacağını belirtmek yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="321b6-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="321b6-121">Visual Basic ve .NET Framework tarafından tanımlanan öznitelikleri uygulayabilirsiniz ve kendi özniteliklerini tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="321b6-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="321b6-122">Zaman öznitelikleri kullanılacağı hakkında daha fazla bilgi için bkz: [öznitelikleri genel bakış](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="321b6-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="321b6-123">Öznitelik adları hakkında daha fazla bilgi için bkz: [bildirilen öğe adları](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="321b6-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="321b6-124">Kurallar</span><span class="sxs-lookup"><span data-stu-id="321b6-124">Rules</span></span>  
  
-   <span data-ttu-id="321b6-125">**Yerleştirme.**</span><span class="sxs-lookup"><span data-stu-id="321b6-125">**Placement.**</span></span> <span data-ttu-id="321b6-126">Öznitelikleri en bildirilen programlama öğelerine uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="321b6-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="321b6-127">Bir veya daha fazla öznitelik uygulamak için yerleştirdiğiniz bir *öznitelik blok* öğe bildirimi başındaki.</span><span class="sxs-lookup"><span data-stu-id="321b6-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="321b6-128">Öznitelik listesindeki her giriş uygulanmasını istediğiniz bir öznitelik ve değiştirici ve bağımsız değişkenler, bu öznitelik çağırma için kullanmakta olduğunuz belirtir.</span><span class="sxs-lookup"><span data-stu-id="321b6-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="321b6-129">**Açılı ayraçları.**</span><span class="sxs-lookup"><span data-stu-id="321b6-129">**Angle Brackets.**</span></span> <span data-ttu-id="321b6-130">Bir öznitelik listesi sağlarsanız, açılı ayraçlar içine gerekir ("`<`"ve"`>`").</span><span class="sxs-lookup"><span data-stu-id="321b6-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="321b6-131">**Bildirim bölümü.**</span><span class="sxs-lookup"><span data-stu-id="321b6-131">**Part of the Declaration.**</span></span> <span data-ttu-id="321b6-132">Öznitelik öğe bildiriminin, ayrı bir deyimi bir parçası olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="321b6-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="321b6-133">Satır devamlılığı sırası kullanabilirsiniz (" `_`") bildirim deyiminin birden fazla kaynak kodu satır üzerine genişletmek için.</span><span class="sxs-lookup"><span data-stu-id="321b6-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="321b6-134">**Değiştirici.**</span><span class="sxs-lookup"><span data-stu-id="321b6-134">**Modifiers.**</span></span> <span data-ttu-id="321b6-135">Bir öznitelik değiştiricisi (`Assembly` veya `Module`) bir programlama öğesi bir kaynak dosyasının başında uygulanan her bir özniteliği gereklidir.</span><span class="sxs-lookup"><span data-stu-id="321b6-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="321b6-136">Öznitelik değiştiricileri kaynak dosyasının başında olmayan öğelere uygulanan öznitelikleri izin verilmez.</span><span class="sxs-lookup"><span data-stu-id="321b6-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="321b6-137">**Bağımsız değişkenler.**</span><span class="sxs-lookup"><span data-stu-id="321b6-137">**Arguments.**</span></span> <span data-ttu-id="321b6-138">Bir öznitelik için tüm konumsal bağımsız değişken veya özellik başlatıcıları gelmelidir.</span><span class="sxs-lookup"><span data-stu-id="321b6-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="321b6-139">Örnek</span><span class="sxs-lookup"><span data-stu-id="321b6-139">Example</span></span>  
 <span data-ttu-id="321b6-140">Aşağıdaki örnek uygular <xref:System.Runtime.InteropServices.DllImportAttribute> özniteliği bir iskelet tanımına bir `Function` yordamı.</span><span class="sxs-lookup"><span data-stu-id="321b6-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <span data-ttu-id="321b6-141"><xref:System.Runtime.InteropServices.DllImportAttribute>Öznitelikli yordamı yönetilmeyen bir dinamik bağlantı kitaplığı (DLL) bir giriş noktası temsil ettiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="321b6-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="321b6-142">Öznitelik konumsal bağımsız değişkeni olarak DLL adı ve diğer bilgileri değişken başlatıcılar olarak sağlar.</span><span class="sxs-lookup"><span data-stu-id="321b6-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="321b6-143">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="321b6-143">See Also</span></span>  
 [<span data-ttu-id="321b6-144">Derleme</span><span class="sxs-lookup"><span data-stu-id="321b6-144">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [<span data-ttu-id="321b6-145">Modül \<anahtar sözcüğü ></span><span class="sxs-lookup"><span data-stu-id="321b6-145">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="321b6-146">Öznitelikler genel bakış</span><span class="sxs-lookup"><span data-stu-id="321b6-146">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="321b6-147">Nasıl yapılır: kodda deyimleri bölme ve birleştirme</span><span class="sxs-lookup"><span data-stu-id="321b6-147">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)