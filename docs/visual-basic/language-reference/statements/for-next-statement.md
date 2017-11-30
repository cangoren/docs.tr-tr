---
title: For...Next Deyimi (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
caps.latest.revision: "64"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 009c5a383cc3296f7f92888a344fa265547f1077
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="558ac-102">For...Next Deyimi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="558ac-102">For...Next Statement (Visual Basic)</span></span>
<span data-ttu-id="558ac-103">Bir grup ifadeleri, belirtilen sayıda yineler.</span><span class="sxs-lookup"><span data-stu-id="558ac-103">Repeats a group of statements a specified number of times.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="558ac-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="558ac-104">Syntax</span></span>  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## <a name="parts"></a><span data-ttu-id="558ac-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="558ac-105">Parts</span></span>  
  
|<span data-ttu-id="558ac-106">Bölümü</span><span class="sxs-lookup"><span data-stu-id="558ac-106">Part</span></span>|<span data-ttu-id="558ac-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="558ac-107">Description</span></span>|  
|----------|-----------------|  
|`counter`|<span data-ttu-id="558ac-108">Gerekli `For` deyimi.</span><span class="sxs-lookup"><span data-stu-id="558ac-108">Required in the `For` statement.</span></span> <span data-ttu-id="558ac-109">Sayısal değişkeni.</span><span class="sxs-lookup"><span data-stu-id="558ac-109">Numeric variable.</span></span> <span data-ttu-id="558ac-110">For döngüsü denetim değişkeni.</span><span class="sxs-lookup"><span data-stu-id="558ac-110">The control variable for the loop.</span></span> <span data-ttu-id="558ac-111">Daha fazla bilgi için bkz: [sayaç bağımsız değişkeni](#BKMK_Counter) bu konuda daha sonra.</span><span class="sxs-lookup"><span data-stu-id="558ac-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`datatype`|<span data-ttu-id="558ac-112">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="558ac-112">Optional.</span></span> <span data-ttu-id="558ac-113">Veri türü `counter`.</span><span class="sxs-lookup"><span data-stu-id="558ac-113">Data type of `counter`.</span></span> <span data-ttu-id="558ac-114">Daha fazla bilgi için bkz: [sayaç bağımsız değişkeni](#BKMK_Counter) bu konuda daha sonra.</span><span class="sxs-lookup"><span data-stu-id="558ac-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`start`|<span data-ttu-id="558ac-115">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="558ac-115">Required.</span></span> <span data-ttu-id="558ac-116">Sayısal ifade.</span><span class="sxs-lookup"><span data-stu-id="558ac-116">Numeric expression.</span></span> <span data-ttu-id="558ac-117">Başlangıç değeri `counter`.</span><span class="sxs-lookup"><span data-stu-id="558ac-117">The initial value of `counter`.</span></span>|  
|`end`|<span data-ttu-id="558ac-118">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="558ac-118">Required.</span></span> <span data-ttu-id="558ac-119">Sayısal ifade.</span><span class="sxs-lookup"><span data-stu-id="558ac-119">Numeric expression.</span></span> <span data-ttu-id="558ac-120">Son değerini `counter`.</span><span class="sxs-lookup"><span data-stu-id="558ac-120">The final value of `counter`.</span></span>|  
|`step`|<span data-ttu-id="558ac-121">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="558ac-121">Optional.</span></span> <span data-ttu-id="558ac-122">Sayısal ifade.</span><span class="sxs-lookup"><span data-stu-id="558ac-122">Numeric expression.</span></span> <span data-ttu-id="558ac-123">Miktarda `counter` her döngü artırılır.</span><span class="sxs-lookup"><span data-stu-id="558ac-123">The amount by which `counter` is incremented each time through the loop.</span></span>|  
|`statements`|<span data-ttu-id="558ac-124">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="558ac-124">Optional.</span></span> <span data-ttu-id="558ac-125">Bir veya daha fazla deyimleri arasında `For` ve `Next` belirtilen sayıda çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="558ac-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|  
|`Continue For`|<span data-ttu-id="558ac-126">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="558ac-126">Optional.</span></span> <span data-ttu-id="558ac-127">Sonraki döngü tekrarında aktarımları denetimi.</span><span class="sxs-lookup"><span data-stu-id="558ac-127">Transfers control to the next loop iteration.</span></span>|  
|`Exit For`|<span data-ttu-id="558ac-128">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="558ac-128">Optional.</span></span> <span data-ttu-id="558ac-129">Denetimin dışarı aktarır `For` döngü.</span><span class="sxs-lookup"><span data-stu-id="558ac-129">Transfers control out of the `For` loop.</span></span>|  
|`Next`|<span data-ttu-id="558ac-130">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="558ac-130">Required.</span></span> <span data-ttu-id="558ac-131">Tanımını sonlandırır `For` döngü.</span><span class="sxs-lookup"><span data-stu-id="558ac-131">Terminates the definition of the `For` loop.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="558ac-132">`To` Sayaç aralığını belirtmek için bu deyim içinde anahtar sözcüğü kullanılır.</span><span class="sxs-lookup"><span data-stu-id="558ac-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="558ac-133">Bu anahtar sözcük de kullanabilirsiniz [seçin... Case deyimi](../../../visual-basic/language-reference/statements/select-case-statement.md) ve dizi bildirimleri.</span><span class="sxs-lookup"><span data-stu-id="558ac-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="558ac-134">Dizi bildirimleri hakkında daha fazla bilgi için bkz: [Dim deyimi](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="558ac-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="simple-examples"></a><span data-ttu-id="558ac-135">Basit örnekler</span><span class="sxs-lookup"><span data-stu-id="558ac-135">Simple Examples</span></span>  
 <span data-ttu-id="558ac-136">Kullandığınız bir `For`... `Next` yapısı deyimleri kümesi kümesi birkaç kez yineleyin istediğinizde.</span><span class="sxs-lookup"><span data-stu-id="558ac-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>  
  
 <span data-ttu-id="558ac-137">Aşağıdaki örnekte, `index` değişkeni 1 değeri ile başlar ve değeri sonra bitiş döngünün her yinelemesinden ile artırılır `index` 5 ulaşır.</span><span class="sxs-lookup"><span data-stu-id="558ac-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_1.vb)]  
  
 <span data-ttu-id="558ac-138">Aşağıdaki örnekte, `number` değişkeni 2'de başlar ve 0,25 değeri sonra bitiş döngünün her yinelemesinden üzerinde daha az `number` 0 ulaşır.</span><span class="sxs-lookup"><span data-stu-id="558ac-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="558ac-139">`Step` Bağımsız değişkeni `-.25` her döngü tekrarında üzerinde 0,25 tarafından değeri azaltır.</span><span class="sxs-lookup"><span data-stu-id="558ac-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  <span data-ttu-id="558ac-140">A [sırada... End While deyimi](../../../visual-basic/language-reference/statements/while-end-while-statement.md) veya [yapın... Döngü deyimi](../../../visual-basic/language-reference/statements/do-loop-statement.md) ne zaman önceden deyimleri döngüde çalıştırılacak kaç kez tanımadığınız iyi çalışır.</span><span class="sxs-lookup"><span data-stu-id="558ac-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="558ac-141">Ancak, ne zaman beklediğiniz zaman, belirli sayıda döngüsü çalıştırmak bir `For`... `Next` döngü daha iyi bir seçimdir.</span><span class="sxs-lookup"><span data-stu-id="558ac-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="558ac-142">Döngü ilk girdiğinizde yineleme sayısını belirler.</span><span class="sxs-lookup"><span data-stu-id="558ac-142">You determine the number of iterations when you first enter the loop.</span></span>  
  
## <a name="nesting-loops"></a><span data-ttu-id="558ac-143">Döngüler iç içe geçme</span><span class="sxs-lookup"><span data-stu-id="558ac-143">Nesting Loops</span></span>  
 <span data-ttu-id="558ac-144">Geçirebilmenize `For` döngüler içinde başka bir döngü koyarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="558ac-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="558ac-145">Aşağıdaki örnek, iç içe geçmiş gösterir `For`... `Next` farklı adım değerlere sahip yapıları.</span><span class="sxs-lookup"><span data-stu-id="558ac-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="558ac-146">Dış döngü her döngü için bir dize oluşturur.</span><span class="sxs-lookup"><span data-stu-id="558ac-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="558ac-147">Her döngü için bir döngü sayacı değişkeni iç döngü azaltır.</span><span class="sxs-lookup"><span data-stu-id="558ac-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_3.vb)]  
  
 <span data-ttu-id="558ac-148">Döngüler iç içe geçme, her döngü benzersiz olmalıdır `counter` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="558ac-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>  
  
 <span data-ttu-id="558ac-149">Ayrıca, farklı denetim yapıları birbirine içinde yerleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="558ac-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="558ac-150">Daha fazla bilgi için bkz: [iç içe geçmiş denetim yapıları](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="558ac-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-for-and-continue-for"></a><span data-ttu-id="558ac-151">İçin çıkın ve devam etmek için</span><span class="sxs-lookup"><span data-stu-id="558ac-151">Exit For and Continue For</span></span>  
 <span data-ttu-id="558ac-152">`Exit For` Deyimi hemen çıkar `For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="558ac-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="558ac-153">aşağıdaki deyim döngü ve aktarımları denetimine `Next` deyimi.</span><span class="sxs-lookup"><span data-stu-id="558ac-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>  
  
 <span data-ttu-id="558ac-154">`Continue For` Deyimi aktarır denetim hemen sonraki döngü için.</span><span class="sxs-lookup"><span data-stu-id="558ac-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="558ac-155">Daha fazla bilgi için bkz: [devam deyimi](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="558ac-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
 <span data-ttu-id="558ac-156">Aşağıdaki örnek kullanımını göstermektedir `Continue For` ve `Exit For` deyimleri.</span><span class="sxs-lookup"><span data-stu-id="558ac-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_4.vb)]  
  
 <span data-ttu-id="558ac-157">Herhangi bir sayıda koyabilirsiniz `Exit For` deyimlerinde bir `For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="558ac-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="558ac-158">Döngü.</span><span class="sxs-lookup"><span data-stu-id="558ac-158">loop.</span></span> <span data-ttu-id="558ac-159">Kullanıldığında içinde iç içe geçmiş `For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="558ac-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="558ac-160">Döngüler, `Exit For` en içteki döngüden çıkılıp ve iç içe geçme sonraki yüksek düzeyde denetim aktarır.</span><span class="sxs-lookup"><span data-stu-id="558ac-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="558ac-161">`Exit For`Bazı koşulunu sonra çoğunlukla kullanılır (örneğin, bir `If`... `Then`... `Else` yapısı).</span><span class="sxs-lookup"><span data-stu-id="558ac-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="558ac-162">Kullanmak istediğiniz `Exit For` aşağıdaki koşulları için:</span><span class="sxs-lookup"><span data-stu-id="558ac-162">You might want to use `Exit For` for the following conditions:</span></span>  
  
-   <span data-ttu-id="558ac-163">Yinelemek etmeden gereksiz veya mümkün değil.</span><span class="sxs-lookup"><span data-stu-id="558ac-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="558ac-164">Bu durum, hatalı bir değer veya bir sonlandırma isteği oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="558ac-164">An erroneous value or a termination request might create this condition.</span></span>  
  
-   <span data-ttu-id="558ac-165">A `Try`... `Catch`... `Finally` deyimi bir özel durum yakalar.</span><span class="sxs-lookup"><span data-stu-id="558ac-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="558ac-166">Kullanabileceğinize `Exit For` sonunda `Finally` bloğu.</span><span class="sxs-lookup"><span data-stu-id="558ac-166">You might use `Exit For` at the end of the `Finally` block.</span></span>  
  
-   <span data-ttu-id="558ac-167">Bir büyük veya hatta sonsuz sayıda çalışacak bir döngü sonsuz bir döngüde var.</span><span class="sxs-lookup"><span data-stu-id="558ac-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="558ac-168">Böyle bir durum tespit ederse kullanabileceğiniz `Exit For` döngü kaçınmak için.</span><span class="sxs-lookup"><span data-stu-id="558ac-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="558ac-169">Daha fazla bilgi için bkz: [yapın... Loop deyimi](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="558ac-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="558ac-170">Teknik Uygulama</span><span class="sxs-lookup"><span data-stu-id="558ac-170">Technical Implementation</span></span>  
 <span data-ttu-id="558ac-171">Zaman bir `For`... `Next` döngü başlatır, Visual Basic değerlendirir `start`, `end`, ve `step`.</span><span class="sxs-lookup"><span data-stu-id="558ac-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="558ac-172">Visual Basic, yalnızca bu zaman ve atar ardından bu değerleri değerlendirir `start` için `counter`.</span><span class="sxs-lookup"><span data-stu-id="558ac-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="558ac-173">Önce deyim bloğu çalışır, Visual Basic karşılaştırır `counter` için `end`.</span><span class="sxs-lookup"><span data-stu-id="558ac-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="558ac-174">Varsa `counter` zaten daha büyük `end` değeri (veya daha küçük `step` negatif), `For` döngü sona erer ve denetim geçişleri izleyen deyimine `Next` deyimi.</span><span class="sxs-lookup"><span data-stu-id="558ac-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="558ac-175">Aksi takdirde deyimi bloğu çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="558ac-175">Otherwise, the statement block runs.</span></span>  
  
 <span data-ttu-id="558ac-176">Visual Basic karşılaştığı her zaman `Next` deyimi, onu artırır `counter` tarafından `step` ve döndürür `For` deyimi.</span><span class="sxs-lookup"><span data-stu-id="558ac-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="558ac-177">Yeniden karşılaştırır `counter` için `end`, ve yeniden bloğu çalışır ya da sonucuna döngüden çıkılıp.</span><span class="sxs-lookup"><span data-stu-id="558ac-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="558ac-178">Bu işlemi kadar sürer `counter` geçirir `end` veya bir `Exit For` deyimi karşılaştı.</span><span class="sxs-lookup"><span data-stu-id="558ac-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>  
  
 <span data-ttu-id="558ac-179">Döngü kadar bitmez `counter` geçti `end`.</span><span class="sxs-lookup"><span data-stu-id="558ac-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="558ac-180">Varsa `counter` eşittir `end`, döngünün devam eder.</span><span class="sxs-lookup"><span data-stu-id="558ac-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="558ac-181">Blok çalıştırılıp çalıştırılmayacağını belirler karşılaştırma `counter`  <=  `end` varsa `step` pozitif ve `counter`  >=  `end` varsa `step` negatiftir.</span><span class="sxs-lookup"><span data-stu-id="558ac-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>  
  
 <span data-ttu-id="558ac-182">Değeri değiştirirseniz `counter` döngü sırasında içinde kodunuzu okuyun ve hata ayıklama daha zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="558ac-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="558ac-183">Değerinin değiştirilmesi `start`, `end`, veya `step` döngü ilk girildiğinde belirlenen yineleme değerleri etkilemez.</span><span class="sxs-lookup"><span data-stu-id="558ac-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>  
  
 <span data-ttu-id="558ac-184">Döngüler iç içe, derleyici bir hata durumunda bulduğu sinyalleri `Next` önce dış bir iç içe geçirme düzeyi deyiminin `Next` bir iç düzey ifadesi.</span><span class="sxs-lookup"><span data-stu-id="558ac-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="558ac-185">Ancak, derleyici bu hata yalnızca belirtirseniz, çakışan algılayabilir `counter` içinde her `Next` deyimi.</span><span class="sxs-lookup"><span data-stu-id="558ac-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>  
  
### <a name="step-argument"></a><span data-ttu-id="558ac-186">Adım bağımsız değişken</span><span class="sxs-lookup"><span data-stu-id="558ac-186">Step Argument</span></span>  
 <span data-ttu-id="558ac-187">Değeri `step` olumlu veya olumsuz olabilir.</span><span class="sxs-lookup"><span data-stu-id="558ac-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="558ac-188">Bu parametre, döngü işleme aşağıdaki tabloya göre belirler:</span><span class="sxs-lookup"><span data-stu-id="558ac-188">This parameter determines loop processing according to the following table:</span></span>  
  
|<span data-ttu-id="558ac-189">**Adım değeri**</span><span class="sxs-lookup"><span data-stu-id="558ac-189">**Step value**</span></span>|<span data-ttu-id="558ac-190">**Varsa döngü yürütür**</span><span class="sxs-lookup"><span data-stu-id="558ac-190">**Loop executes if**</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="558ac-191">Pozitif veya sıfır</span><span class="sxs-lookup"><span data-stu-id="558ac-191">Positive or zero</span></span>|`counter` <= `end`|  
|<span data-ttu-id="558ac-192">Negatif</span><span class="sxs-lookup"><span data-stu-id="558ac-192">Negative</span></span>|`counter` >= `end`|  
  
 <span data-ttu-id="558ac-193">Varsayılan değer olan `step` 1'dir.</span><span class="sxs-lookup"><span data-stu-id="558ac-193">The default value of `step` is 1.</span></span>  
  
###  <span data-ttu-id="558ac-194"><a name="BKMK_Counter"></a>Sayaç bağımsız değişken</span><span class="sxs-lookup"><span data-stu-id="558ac-194"><a name="BKMK_Counter"></a> Counter Argument</span></span>  
 <span data-ttu-id="558ac-195">Aşağıdaki tablo gösterir olup olmadığını `counter` tüm kapsamlıdır yeni bir yerel değişken tanımlar `For…Next` döngü.</span><span class="sxs-lookup"><span data-stu-id="558ac-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="558ac-196">Bu belirleme bağlıdır `datatype` mevcut olup `counter` zaten tanımlandı.</span><span class="sxs-lookup"><span data-stu-id="558ac-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>  
  
|<span data-ttu-id="558ac-197">Olan `datatype` var?</span><span class="sxs-lookup"><span data-stu-id="558ac-197">Is `datatype` present?</span></span>|<span data-ttu-id="558ac-198">Olan `counter` önceden tanımlanmış?</span><span class="sxs-lookup"><span data-stu-id="558ac-198">Is `counter` already defined?</span></span>|<span data-ttu-id="558ac-199">Sonuç (olup olmadığını `counter` tüm kapsamlıdır yeni bir yerel değişken tanımlar `For...Next` döngü)</span><span class="sxs-lookup"><span data-stu-id="558ac-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="558ac-200">Hayır</span><span class="sxs-lookup"><span data-stu-id="558ac-200">No</span></span>|<span data-ttu-id="558ac-201">Evet</span><span class="sxs-lookup"><span data-stu-id="558ac-201">Yes</span></span>|<span data-ttu-id="558ac-202">Hayır, çünkü `counter` zaten tanımlandı.</span><span class="sxs-lookup"><span data-stu-id="558ac-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="558ac-203">Varsa kapsamını `counter` yordamı için yerel olmayan bir derleme zamanı uyarı oluşur.</span><span class="sxs-lookup"><span data-stu-id="558ac-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|  
|<span data-ttu-id="558ac-204">Hayır</span><span class="sxs-lookup"><span data-stu-id="558ac-204">No</span></span>|<span data-ttu-id="558ac-205">Hayır</span><span class="sxs-lookup"><span data-stu-id="558ac-205">No</span></span>|<span data-ttu-id="558ac-206">Evet.</span><span class="sxs-lookup"><span data-stu-id="558ac-206">Yes.</span></span> <span data-ttu-id="558ac-207">Veri Türü alanından çıkarımı yapılan `start`, `end`, ve `step` ifadeler.</span><span class="sxs-lookup"><span data-stu-id="558ac-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="558ac-208">Tür çıkarımı hakkında daha fazla bilgi için bkz: [Option Infer deyimi](../../../visual-basic/language-reference/statements/option-infer-statement.md) ve [yerel türü çıkarımı](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="558ac-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|  
|<span data-ttu-id="558ac-209">Evet</span><span class="sxs-lookup"><span data-stu-id="558ac-209">Yes</span></span>|<span data-ttu-id="558ac-210">Evet</span><span class="sxs-lookup"><span data-stu-id="558ac-210">Yes</span></span>|<span data-ttu-id="558ac-211">Evet, ancak yalnızca varolan `counter` değişkeni yordamın dışında tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="558ac-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="558ac-212">Bu değişken ayrı kalır.</span><span class="sxs-lookup"><span data-stu-id="558ac-212">That variable remains separate.</span></span> <span data-ttu-id="558ac-213">Varsa mevcut kapsamını `counter` değişkenidir yordamı için yerel bir derleme zamanı hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="558ac-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="558ac-214">Evet</span><span class="sxs-lookup"><span data-stu-id="558ac-214">Yes</span></span>|<span data-ttu-id="558ac-215">Hayır</span><span class="sxs-lookup"><span data-stu-id="558ac-215">No</span></span>|<span data-ttu-id="558ac-216">Evet.</span><span class="sxs-lookup"><span data-stu-id="558ac-216">Yes.</span></span>|  
  
 <span data-ttu-id="558ac-217">Veri türü `counter` aşağıdaki türlerden biri olmalıdır yineleme türünü belirler:</span><span class="sxs-lookup"><span data-stu-id="558ac-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>  
  
-   <span data-ttu-id="558ac-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, veya `Double`.</span><span class="sxs-lookup"><span data-stu-id="558ac-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>  
  
-   <span data-ttu-id="558ac-219">Kullanarak bildirme bir numaralandırma bir [Enum deyimi](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="558ac-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
-   <span data-ttu-id="558ac-220">Bir `Object`.</span><span class="sxs-lookup"><span data-stu-id="558ac-220">An `Object`.</span></span>  
  
-   <span data-ttu-id="558ac-221">Bir tür `T` aşağıdaki işleçleri sahip olduğu `B` kullanılabilir bir tür bir `Boolean` ifade.</span><span class="sxs-lookup"><span data-stu-id="558ac-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 <span data-ttu-id="558ac-222">İsteğe bağlı olarak belirtebilirsiniz `counter` değişkeni `Next` deyimi.</span><span class="sxs-lookup"><span data-stu-id="558ac-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="558ac-223">Özellikle, iç içe geçmiş durumunda bu sözdizimi, programınızı okunabilirliğini artırır `For` döngüler.</span><span class="sxs-lookup"><span data-stu-id="558ac-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="558ac-224">İlgili görünür değişkeni belirtmeniz gerekir `For` deyimi.</span><span class="sxs-lookup"><span data-stu-id="558ac-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>  
  
 <span data-ttu-id="558ac-225">`start`, `end`, Ve `step` ifadeleri değerlendirme türü için widens herhangi bir veri türü için `counter`.</span><span class="sxs-lookup"><span data-stu-id="558ac-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="558ac-226">Kullanıcı tanımlı bir tür için kullanırsanız, `counter`, tanımlamak zorunda kalabilirsiniz `CType` türlerini dönüştürmek için dönüştürme işleci `start`, `end`, veya `step` türüne `counter`.</span><span class="sxs-lookup"><span data-stu-id="558ac-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="558ac-227">Örnek</span><span class="sxs-lookup"><span data-stu-id="558ac-227">Example</span></span>  
 <span data-ttu-id="558ac-228">Aşağıdaki örnek, genel bir listeden tüm öğeleri kaldırır.</span><span class="sxs-lookup"><span data-stu-id="558ac-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="558ac-229">Yerine bir [For Each... Sonraki deyim](../../../visual-basic/language-reference/statements/for-each-next-statement.md), örnekte gösterildiği bir `For`... `Next` azalan sırada tekrarlanan deyimi.</span><span class="sxs-lookup"><span data-stu-id="558ac-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="558ac-230">Örneğin bu tekniği kullanır, çünkü `removeAt` yöntemi bir alt dizin değerine sahip olacak şekilde kaldırılan öğeden sonra öğeleri neden olur.</span><span class="sxs-lookup"><span data-stu-id="558ac-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="558ac-231">Örnek</span><span class="sxs-lookup"><span data-stu-id="558ac-231">Example</span></span>  
 <span data-ttu-id="558ac-232">Aşağıdaki örnek kullanarak bildirilmiş bir numaralandırma dolaşır bir [Enum deyimi](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="558ac-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_6.vb)]  
  
## <a name="example"></a><span data-ttu-id="558ac-233">Örnek</span><span class="sxs-lookup"><span data-stu-id="558ac-233">Example</span></span>  
 <span data-ttu-id="558ac-234">Aşağıdaki örnekte, deyimi parametreleri için işleç aşırı yüklemeye sahip bir sınıf kullanma `+`, `-`, `>=`, ve `<=` işleçler.</span><span class="sxs-lookup"><span data-stu-id="558ac-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="558ac-235">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="558ac-235">See Also</span></span>  
 <xref:System.Collections.Generic.List%601>  
 [<span data-ttu-id="558ac-236">Döngü yapıları</span><span class="sxs-lookup"><span data-stu-id="558ac-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="558ac-237">While... End While deyimi</span><span class="sxs-lookup"><span data-stu-id="558ac-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="558ac-238">Yapın... Loop deyimi</span><span class="sxs-lookup"><span data-stu-id="558ac-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="558ac-239">İç içe geçmiş denetim yapıları</span><span class="sxs-lookup"><span data-stu-id="558ac-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="558ac-240">Exit deyimi</span><span class="sxs-lookup"><span data-stu-id="558ac-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="558ac-241">Koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="558ac-241">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)