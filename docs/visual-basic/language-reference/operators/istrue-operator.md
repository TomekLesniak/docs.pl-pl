---
title: IsTrue, operator
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 2e67a4adabe58ab12d317ae6318c0a2fac29da7d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866950"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="0f6c5-102">IsTrue — Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f6c5-102">IsTrue Operator (Visual Basic)</span></span>

<span data-ttu-id="0f6c5-103">Określa, czy wyrażenie jest `True` .</span><span class="sxs-lookup"><span data-stu-id="0f6c5-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="0f6c5-104">Nie można `IsTrue` jawnie wywołać w kodzie, ale kompilator Visual Basic może użyć go do wygenerowania kodu z `OrElse` klauzul.</span><span class="sxs-lookup"><span data-stu-id="0f6c5-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="0f6c5-105">W przypadku zdefiniowania klasy lub struktury, a następnie użycia zmiennej tego typu w `OrElse` klauzuli, należy zdefiniować `IsTrue` dla tej klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="0f6c5-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="0f6c5-106">Kompilator traktuje `IsTrue` Operatory i `IsFalse` jako *pasującą parę*.</span><span class="sxs-lookup"><span data-stu-id="0f6c5-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="0f6c5-107">Oznacza to, że w przypadku zdefiniowania jednego z nich należy również zdefiniować drugi.</span><span class="sxs-lookup"><span data-stu-id="0f6c5-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="0f6c5-108">Użycie kompilatora IsTrue</span><span class="sxs-lookup"><span data-stu-id="0f6c5-108">Compiler Use of IsTrue</span></span>  

 <span data-ttu-id="0f6c5-109">Po zdefiniowaniu klasy lub struktury można użyć zmiennej tego typu w `For` `If` instrukcji,, `Else If` , lub `While` w `When` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="0f6c5-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="0f6c5-110">W takim przypadku kompilator wymaga operatora, który konwertuje typ na `Boolean` wartość, aby umożliwić przetestowanie warunku.</span><span class="sxs-lookup"><span data-stu-id="0f6c5-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="0f6c5-111">Wyszukuje odpowiedni operator w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="0f6c5-111">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="0f6c5-112">Rozszerzający Operator konwersji z klasy lub struktury do `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="0f6c5-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="0f6c5-113">Rozszerzający Operator konwersji z klasy lub struktury do `Boolean?` .</span><span class="sxs-lookup"><span data-stu-id="0f6c5-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="0f6c5-114">`IsTrue`Operator klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="0f6c5-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="0f6c5-115">Zawężanie konwersji na `Boolean?` , która nie obejmuje konwersji z `Boolean` do `Boolean?` .</span><span class="sxs-lookup"><span data-stu-id="0f6c5-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="0f6c5-116">Wąski Operator konwersji z klasy lub struktury do `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="0f6c5-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="0f6c5-117">Jeśli nie zdefiniowano żadnej konwersji do `Boolean` `IsTrue` operatora OR, kompilator sygnalizuje błąd.</span><span class="sxs-lookup"><span data-stu-id="0f6c5-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f6c5-118">`IsTrue`Operator może być *przeciążony*, co oznacza, że Klasa lub struktura może zmienić jego zachowanie, gdy jego operand ma typ tej klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="0f6c5-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="0f6c5-119">Jeśli Twój kod używa tego operatora dla takiej klasy lub struktury, pamiętaj o tym, aby zrozumieć jego ponownie zdefiniowane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="0f6c5-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0f6c5-120">Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0f6c5-120">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f6c5-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="0f6c5-121">Example</span></span>  

 <span data-ttu-id="0f6c5-122">Poniższy przykład kodu definiuje kontur struktury, która zawiera definicje `IsFalse` `IsTrue` operatorów i.</span><span class="sxs-lookup"><span data-stu-id="0f6c5-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="0f6c5-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0f6c5-123">See also</span></span>

- [<span data-ttu-id="0f6c5-124">IsFalse, operator</span><span class="sxs-lookup"><span data-stu-id="0f6c5-124">IsFalse Operator</span></span>](isfalse-operator.md)
- [<span data-ttu-id="0f6c5-125">Instrukcje: definiowanie operatora</span><span class="sxs-lookup"><span data-stu-id="0f6c5-125">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="0f6c5-126">OrElse, operator</span><span class="sxs-lookup"><span data-stu-id="0f6c5-126">OrElse Operator</span></span>](orelse-operator.md)
