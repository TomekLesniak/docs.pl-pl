---
title: 'Porady: definiowanie operatora konwersji'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 2fabcf6c6ceb38fe77d4eed4f02dcb5a5e447bf1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085675"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="804c3-102">Porady: definiowanie operatora konwersji (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="804c3-102">How to: Define a Conversion Operator (Visual Basic)</span></span>

<span data-ttu-id="804c3-103">Jeśli zdefiniowano klasę lub strukturę, można zdefiniować Operator konwersji typu między typem klasy lub struktury a innym typem danych (np `Integer` `Double` ., lub `String` ).</span><span class="sxs-lookup"><span data-stu-id="804c3-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="804c3-104">Zdefiniuj konwersję typu jako procedurę [funkcji CType](../../../language-reference/functions/ctype-function.md) w klasie lub strukturze.</span><span class="sxs-lookup"><span data-stu-id="804c3-104">Define the type conversion as a [CType Function](../../../language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="804c3-105">Wszystkie procedury konwersji muszą mieć `Public Shared` wartość, a każdy z nich musi określać [rozszerzanie](../../../language-reference/modifiers/widening.md) lub [zwężanie](../../../language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="804c3-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../language-reference/modifiers/widening.md) or [Narrowing](../../../language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="804c3-106">Definiowanie operatora w klasie lub strukturze jest również nazywane *przeciążeniem* operatora.</span><span class="sxs-lookup"><span data-stu-id="804c3-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="804c3-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="804c3-107">Example</span></span>  

 <span data-ttu-id="804c3-108">Poniższy przykład definiuje operatory konwersji między strukturą o nazwie `digit` i a `Byte` .</span><span class="sxs-lookup"><span data-stu-id="804c3-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="804c3-109">Możesz przetestować strukturę `digit` przy użyciu następującego kodu.</span><span class="sxs-lookup"><span data-stu-id="804c3-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="804c3-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="804c3-110">See also</span></span>

- [<span data-ttu-id="804c3-111">Procedury operatorów</span><span class="sxs-lookup"><span data-stu-id="804c3-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="804c3-112">Instrukcje: definiowanie operatora</span><span class="sxs-lookup"><span data-stu-id="804c3-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="804c3-113">Instrukcje: wywoływanie procedury operatora</span><span class="sxs-lookup"><span data-stu-id="804c3-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="804c3-114">Instrukcje: używanie klasy definiującej operatory</span><span class="sxs-lookup"><span data-stu-id="804c3-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="804c3-115">Operator — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="804c3-115">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="804c3-116">Structure — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="804c3-116">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="804c3-117">Instrukcje: Deklarowanie struktury</span><span class="sxs-lookup"><span data-stu-id="804c3-117">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="804c3-118">Konwersje jawne i niejawne</span><span class="sxs-lookup"><span data-stu-id="804c3-118">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="804c3-119">Rozszerzanie i zwężanie konwersji</span><span class="sxs-lookup"><span data-stu-id="804c3-119">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
