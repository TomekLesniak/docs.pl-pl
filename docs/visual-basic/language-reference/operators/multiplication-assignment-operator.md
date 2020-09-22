---
title: Operator *=
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 4e2f18fb2b8110d97390390b3934d3c1761baa35
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866730"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="70d4d-102">\*= — Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70d4d-102">\*= Operator (Visual Basic)</span></span>

<span data-ttu-id="70d4d-103">Mnoży wartość zmiennej lub właściwości przez wartość wyrażenia i przypisuje wynik do zmiennej lub właściwości.</span><span class="sxs-lookup"><span data-stu-id="70d4d-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70d4d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="70d4d-104">Syntax</span></span>  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="70d4d-105">Części</span><span class="sxs-lookup"><span data-stu-id="70d4d-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="70d4d-106">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="70d4d-106">Required.</span></span> <span data-ttu-id="70d4d-107">Dowolna zmienna lub właściwość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="70d4d-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="70d4d-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="70d4d-108">Required.</span></span> <span data-ttu-id="70d4d-109">Dowolne wyrażenie liczbowe.</span><span class="sxs-lookup"><span data-stu-id="70d4d-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70d4d-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="70d4d-110">Remarks</span></span>  

 <span data-ttu-id="70d4d-111">Element po lewej stronie `*=` operatora może być prostą zmienną skalarną, właściwością lub elementem tablicy.</span><span class="sxs-lookup"><span data-stu-id="70d4d-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="70d4d-112">Zmienna lub właściwość nie może być [tylko do odczytu](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="70d4d-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="70d4d-113">`*=`Operator najpierw mnoży wartość wyrażenia (po prawej stronie operatora) przez wartość zmiennej lub właściwości (po lewej stronie operatora), która jest domyślnie mnożona.</span><span class="sxs-lookup"><span data-stu-id="70d4d-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="70d4d-114">Następnie operator przypisuje wynik tej operacji do zmiennej lub właściwości.</span><span class="sxs-lookup"><span data-stu-id="70d4d-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="70d4d-115">Przeciążenie</span><span class="sxs-lookup"><span data-stu-id="70d4d-115">Overloading</span></span>  

 <span data-ttu-id="70d4d-116">[Operator \*](multiplication-operator.md) może być *przeciążony*, co oznacza, że Klasa lub struktura może przedefiniować jej zachowanie, gdy operand ma typ tej klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="70d4d-116">The [\* Operator](multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="70d4d-117">Przeciążanie `*` operatora ma wpływ na zachowanie `*=` operatora.</span><span class="sxs-lookup"><span data-stu-id="70d4d-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="70d4d-118">Jeśli kod korzysta z `*=` klasy lub struktury, która przeciążania `*` , należy poznać jej ponownie zdefiniowane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="70d4d-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="70d4d-119">Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="70d4d-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70d4d-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="70d4d-120">Example</span></span>  

 <span data-ttu-id="70d4d-121">Poniższy przykład używa operatora, `*=` Aby pomnożyć jedną `Integer` zmienną przez sekundę i przypisać wynik do pierwszej zmiennej.</span><span class="sxs-lookup"><span data-stu-id="70d4d-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="70d4d-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="70d4d-122">See also</span></span>

- [<span data-ttu-id="70d4d-123">\* — Operator</span><span class="sxs-lookup"><span data-stu-id="70d4d-123">\* Operator</span></span>](multiplication-operator.md)
- [<span data-ttu-id="70d4d-124">Operatory przypisania</span><span class="sxs-lookup"><span data-stu-id="70d4d-124">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="70d4d-125">Operatory arytmetyczne</span><span class="sxs-lookup"><span data-stu-id="70d4d-125">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="70d4d-126">Kolejność wykonywania działań (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70d4d-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="70d4d-127">Operatory według funkcji</span><span class="sxs-lookup"><span data-stu-id="70d4d-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="70d4d-128">Instrukcje</span><span class="sxs-lookup"><span data-stu-id="70d4d-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
