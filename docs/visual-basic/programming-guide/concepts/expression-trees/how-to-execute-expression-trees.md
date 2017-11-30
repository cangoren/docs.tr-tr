---
title: "Nasıl yapılır: ifade ağaçlarını (Visual Basic) yürütme"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45a13f13659472b7620b6df070815ace1d6fb0de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-execute-expression-trees-visual-basic"></a><span data-ttu-id="e0e5b-102">Nasıl yapılır: ifade ağaçlarını (Visual Basic) yürütme</span><span class="sxs-lookup"><span data-stu-id="e0e5b-102">How to: Execute Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="e0e5b-103">Bu konuda bir ifade ağacına yürütme gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="e0e5b-104">Bir ifade ağacına yürütülürken bir değer döndürebilir ya da yalnızca bir yöntemi çağırma gibi bir eylem gerçekleştirebilir.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="e0e5b-105">Lambda ifadeleri temsil eden ifade ağaçları çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="e0e5b-106">Lambda ifadeleri temsil ifade ağaçları türündedir <xref:System.Linq.Expressions.LambdaExpression> veya <xref:System.Linq.Expressions.Expression%601>.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="e0e5b-107">Bu ifade ağaçlarını yürütme çağrısı <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> yürütülebilir bir temsilci oluşturma ve temsilci çağırma yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0e5b-108">Temsilci türü bilinmiyor, diğer bir deyişle, lambda ifadesi türü ise <xref:System.Linq.Expressions.LambdaExpression> ve <xref:System.Linq.Expressions.Expression%601>, çağırmalısınız <xref:System.Delegate.DynamicInvoke%2A> doğrudan çağırma yerine temsilci yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="e0e5b-109">Bir ifade ağacına bir lambda ifadesi göstermiyor, özgün ifade ağacına çağırarak kendi gövdesi olarak sahip yeni bir lambda ifadesi oluşturabilirsiniz <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="e0e5b-110">Ardından, bu bölümde daha önce açıklandığı gibi lambda ifadesi yürütebilir.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0e5b-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="e0e5b-111">Example</span></span>  
 <span data-ttu-id="e0e5b-112">Aşağıdaki kod örneği, bir lambda ifadesi oluşturma ve yürütme güç sayıya oluşturma işlemi temsil eden bir ifade ağacına yürütmek gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="e0e5b-113">Yükseltilmiş numarasını gücünü temsil eder, sonuç görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
```vb  
' The expression tree to execute.  
Dim be As BinaryExpression = Expression.Power(Expression.Constant(2.0R), Expression.Constant(3.0R))  
  
' Create a lambda expression.  
Dim le As Expression(Of Func(Of Double)) = Expression.Lambda(Of Func(Of Double))(be)  
  
' Compile the lambda expression.  
Dim compiledExpression As Func(Of Double) = le.Compile()  
  
' Execute the lambda expression.  
Dim result As Double = compiledExpression()  
  
' Display the result.  
MsgBox(result)  
  
' This code produces the following output:  
' 8  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e0e5b-114">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="e0e5b-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="e0e5b-115">Zaten başvurulmayan varsa System.Core.dll proje başvurusu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-115">Add a project reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="e0e5b-116">System.Linq.Expressions ad alanı içerir.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e5b-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-117">See Also</span></span>  
 [<span data-ttu-id="e0e5b-118">İfade ağaçları (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0e5b-118">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)  
 [<span data-ttu-id="e0e5b-119">Nasıl yapılır: ifade ağaçlarını (Visual Basic) değiştirme</span><span class="sxs-lookup"><span data-stu-id="e0e5b-119">How to: Modify Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)