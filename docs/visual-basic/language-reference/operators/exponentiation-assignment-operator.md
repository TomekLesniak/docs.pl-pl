---
title: Operator ^=
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: a956ffdaa3456ed09443f25c3383b6aab52fb5bf
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867058"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="54ae2-102">^= — Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54ae2-102">^= Operator (Visual Basic)</span></span>

<span data-ttu-id="54ae2-103">Podnosi wartość zmiennej lub właściwości do potęgi wyrażenia i przypisuje wynik z powrotem do zmiennej lub właściwości.</span><span class="sxs-lookup"><span data-stu-id="54ae2-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54ae2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="54ae2-104">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="54ae2-105">Części</span><span class="sxs-lookup"><span data-stu-id="54ae2-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="54ae2-106">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="54ae2-106">Required.</span></span> <span data-ttu-id="54ae2-107">Dowolna zmienna lub właściwość numeryczna.</span><span class="sxs-lookup"><span data-stu-id="54ae2-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="54ae2-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="54ae2-108">Required.</span></span> <span data-ttu-id="54ae2-109">Dowolne wyrażenie liczbowe.</span><span class="sxs-lookup"><span data-stu-id="54ae2-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54ae2-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="54ae2-110">Remarks</span></span>  

 <span data-ttu-id="54ae2-111">Element po lewej stronie `^=` operatora może być prostą zmienną skalarną, właściwością lub elementem tablicy.</span><span class="sxs-lookup"><span data-stu-id="54ae2-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="54ae2-112">Zmienna lub właściwość nie może być [tylko do odczytu](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="54ae2-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="54ae2-113">`^=`Operator najpierw wywołuje wartość zmiennej lub właściwości (po lewej stronie operatora) do potęgi wartości wyrażeniu (po prawej stronie operatora), aby wykonać akcję.</span><span class="sxs-lookup"><span data-stu-id="54ae2-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="54ae2-114">Następnie operator przypisuje wynik tej operacji z powrotem do zmiennej lub właściwości.</span><span class="sxs-lookup"><span data-stu-id="54ae2-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="54ae2-115">Visual Basic zawsze wykonuje potęgowanie w [podwójnym typie danych](../data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="54ae2-115">Visual Basic always performs exponentiation in the [Double Data Type](../data-types/double-data-type.md).</span></span> <span data-ttu-id="54ae2-116">Operandy dowolnego typu są konwertowane na `Double` , a wynik jest zawsze `Double` .</span><span class="sxs-lookup"><span data-stu-id="54ae2-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="54ae2-117">Wartość `expression` może być ułamkowa, ujemna lub obie.</span><span class="sxs-lookup"><span data-stu-id="54ae2-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="54ae2-118">Przeciążenie</span><span class="sxs-lookup"><span data-stu-id="54ae2-118">Overloading</span></span>  

 <span data-ttu-id="54ae2-119">[Operator ^](exponentiation-operator.md) może być *przeciążony*, co oznacza, że Klasa lub struktura może przedefiniować jej zachowanie, gdy operand ma typ tej klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="54ae2-119">The [^ Operator](exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="54ae2-120">Przeciążanie `^` operatora ma wpływ na zachowanie `^=` operatora.</span><span class="sxs-lookup"><span data-stu-id="54ae2-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="54ae2-121">Jeśli kod korzysta z `^=` klasy lub struktury, która przeciążania `^` , należy poznać jej ponownie zdefiniowane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="54ae2-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="54ae2-122">Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="54ae2-122">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="54ae2-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="54ae2-123">Example</span></span>  

 <span data-ttu-id="54ae2-124">Poniższy przykład używa operatora, `^=` Aby podnieść wartość jednej `Integer` zmiennej do potęgi drugiej zmiennej i przypisać wynik do pierwszej zmiennej.</span><span class="sxs-lookup"><span data-stu-id="54ae2-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="54ae2-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="54ae2-125">See also</span></span>

- [<span data-ttu-id="54ae2-126">^ — Operator</span><span class="sxs-lookup"><span data-stu-id="54ae2-126">^ Operator</span></span>](exponentiation-operator.md)
- [<span data-ttu-id="54ae2-127">Operatory przypisania</span><span class="sxs-lookup"><span data-stu-id="54ae2-127">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="54ae2-128">Operatory arytmetyczne</span><span class="sxs-lookup"><span data-stu-id="54ae2-128">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="54ae2-129">Kolejność wykonywania działań (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54ae2-129">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="54ae2-130">Operatory według funkcji</span><span class="sxs-lookup"><span data-stu-id="54ae2-130">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="54ae2-131">Instrukcje</span><span class="sxs-lookup"><span data-stu-id="54ae2-131">Statements</span></span>](../../programming-guide/language-features/statements.md)
