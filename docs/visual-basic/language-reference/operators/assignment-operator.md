---
title: = — Operator
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: eccea0b43564a4980778c9d1a5b8f9a8c2a9207d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874821"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="f7295-102">= — Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7295-102">= Operator (Visual Basic)</span></span>

<span data-ttu-id="f7295-103">Przypisuje wartość do zmiennej lub właściwości.</span><span class="sxs-lookup"><span data-stu-id="f7295-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7295-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f7295-104">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="f7295-105">Części</span><span class="sxs-lookup"><span data-stu-id="f7295-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="f7295-106">Dowolna zapisywalna zmienna lub Każda właściwość.</span><span class="sxs-lookup"><span data-stu-id="f7295-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="f7295-107">Dowolny literał, stała lub wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="f7295-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7295-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f7295-108">Remarks</span></span>  

 <span data-ttu-id="f7295-109">Element po lewej stronie znaku równości ( `=` ) może być prostą zmienną skalarną, właściwością lub elementem tablicy.</span><span class="sxs-lookup"><span data-stu-id="f7295-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="f7295-110">Zmienna lub właściwość nie może być [tylko do odczytu](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="f7295-110">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="f7295-111">`=`Operator przypisuje wartość po prawej stronie do zmiennej lub właściwości po jej lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="f7295-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f7295-112">`=`Operator jest również używany jako operator porównania.</span><span class="sxs-lookup"><span data-stu-id="f7295-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="f7295-113">Aby uzyskać szczegółowe informacje, zobacz [Operatory porównania](comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="f7295-113">For details, see [Comparison Operators](comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f7295-114">Przeciążenie</span><span class="sxs-lookup"><span data-stu-id="f7295-114">Overloading</span></span>  

 <span data-ttu-id="f7295-115">`=`Operator może być przeciążony tylko jako operator porównania relacyjnego, a nie jako operator przypisania.</span><span class="sxs-lookup"><span data-stu-id="f7295-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="f7295-116">Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f7295-116">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7295-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="f7295-117">Example</span></span>  

 <span data-ttu-id="f7295-118">Poniższy przykład demonstruje operator przypisania.</span><span class="sxs-lookup"><span data-stu-id="f7295-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="f7295-119">Wartość po prawej stronie jest przypisana do zmiennej po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="f7295-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="f7295-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f7295-120">See also</span></span>

- [<span data-ttu-id="f7295-121">&= — operator</span><span class="sxs-lookup"><span data-stu-id="f7295-121">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="f7295-122">Operator \* =</span><span class="sxs-lookup"><span data-stu-id="f7295-122">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="f7295-123">Operator + =</span><span class="sxs-lookup"><span data-stu-id="f7295-123">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="f7295-124">-= — Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7295-124">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="f7295-125">Operator/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7295-125">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="f7295-126">\\= — Operator</span><span class="sxs-lookup"><span data-stu-id="f7295-126">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="f7295-127">^ = — Operator</span><span class="sxs-lookup"><span data-stu-id="f7295-127">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="f7295-128">Instrukcje</span><span class="sxs-lookup"><span data-stu-id="f7295-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="f7295-129">Operatory porównania</span><span class="sxs-lookup"><span data-stu-id="f7295-129">Comparison Operators</span></span>](comparison-operators.md)
- [<span data-ttu-id="f7295-130">Trybie</span><span class="sxs-lookup"><span data-stu-id="f7295-130">ReadOnly</span></span>](../modifiers/readonly.md)
- [<span data-ttu-id="f7295-131">Wnioskowanie o typie lokalnym</span><span class="sxs-lookup"><span data-stu-id="f7295-131">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
