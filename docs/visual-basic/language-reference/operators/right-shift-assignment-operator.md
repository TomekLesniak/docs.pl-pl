---
title: '>>= — Operator'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: a1c2331791644155504183d3cf5767470a3bf17b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873355"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="37210-102">>>= — operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37210-102">>>= Operator (Visual Basic)</span></span>

<span data-ttu-id="37210-103">Wykonuje arytmetyczne przesunięcie w prawo wartości zmiennej lub właściwości i przypisuje wynik z powrotem do zmiennej lub właściwości.</span><span class="sxs-lookup"><span data-stu-id="37210-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37210-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="37210-104">Syntax</span></span>  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="37210-105">Części</span><span class="sxs-lookup"><span data-stu-id="37210-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="37210-106">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="37210-106">Required.</span></span> <span data-ttu-id="37210-107">Zmienna lub właściwość typu całkowitego ( `SByte` , `Byte` ,,, `Short` , `UShort` `Integer` `UInteger` , `Long` lub `ULong` ).</span><span class="sxs-lookup"><span data-stu-id="37210-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="37210-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="37210-108">Required.</span></span> <span data-ttu-id="37210-109">Wyrażenie liczbowe typu danych, które jest poszerzane do `Integer` .</span><span class="sxs-lookup"><span data-stu-id="37210-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37210-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="37210-110">Remarks</span></span>  

 <span data-ttu-id="37210-111">Element po lewej stronie `>>=` operatora może być prostą zmienną skalarną, właściwością lub elementem tablicy.</span><span class="sxs-lookup"><span data-stu-id="37210-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="37210-112">Zmienna lub właściwość nie może być [tylko do odczytu](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="37210-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="37210-113">`>>=`Operator najpierw wykonuje arytmetyczne przesunięcie w prawo wartości zmiennej lub właściwości.</span><span class="sxs-lookup"><span data-stu-id="37210-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="37210-114">Następnie operator przypisuje wynik tej operacji z powrotem do zmiennej lub właściwości.</span><span class="sxs-lookup"><span data-stu-id="37210-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="37210-115">Przesunięcia arytmetyczne nie są cykliczne, co oznacza, że bity przesunięte poza jeden koniec wyniku nie są ponownie wprowadzane na drugim końcu.</span><span class="sxs-lookup"><span data-stu-id="37210-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="37210-116">W wyniku przesunięcia w prawo arytmetyczne bity przesunięte poza skrajną prawą pozycję bitu są odrzucane, a bit z lewej strony jest propagowany do pozycji bitowych opuszczone w lewo.</span><span class="sxs-lookup"><span data-stu-id="37210-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="37210-117">Oznacza to, że jeśli `variableorproperty` ma wartość ujemną, pozycje opuszczone są ustawione na jeden.</span><span class="sxs-lookup"><span data-stu-id="37210-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="37210-118">Jeśli `variableorproperty` jest wartością dodatnią lub jeśli jej typ danych jest typem bez znaku, pozycje opuszczone są ustawione na wartość zero.</span><span class="sxs-lookup"><span data-stu-id="37210-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="37210-119">Przeciążenie</span><span class="sxs-lookup"><span data-stu-id="37210-119">Overloading</span></span>  

 <span data-ttu-id="37210-120">[Operator>> ](right-shift-operator.md) może być *przeciążony*, co oznacza, że Klasa lub struktura może przedefiniować jej zachowanie, gdy operand ma typ tej klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="37210-120">The [>> Operator](right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="37210-121">Przeciążanie `>>` operatora ma wpływ na zachowanie `>>=` operatora.</span><span class="sxs-lookup"><span data-stu-id="37210-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="37210-122">Jeśli kod korzysta z `>>=` klasy lub struktury, która przeciążania `>>` , należy poznać jej ponownie zdefiniowane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="37210-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="37210-123">Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="37210-123">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37210-124">Przykład</span><span class="sxs-lookup"><span data-stu-id="37210-124">Example</span></span>  

 <span data-ttu-id="37210-125">Poniższy przykład używa operatora, `>>=` Aby przesunąć wzorzec bitowy `Integer` zmiennej bezpośrednio o określoną wartość i przypisać wynik do zmiennej.</span><span class="sxs-lookup"><span data-stu-id="37210-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="37210-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="37210-126">See also</span></span>

- [<span data-ttu-id="37210-127"> Operator>> </span><span class="sxs-lookup"><span data-stu-id="37210-127">>> Operator</span></span>](right-shift-operator.md)
- [<span data-ttu-id="37210-128">Operatory przypisania</span><span class="sxs-lookup"><span data-stu-id="37210-128">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="37210-129">Operatory Bit Shift</span><span class="sxs-lookup"><span data-stu-id="37210-129">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="37210-130">Kolejność wykonywania działań (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37210-130">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="37210-131">Operatory według funkcji</span><span class="sxs-lookup"><span data-stu-id="37210-131">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="37210-132">Instrukcje</span><span class="sxs-lookup"><span data-stu-id="37210-132">Statements</span></span>](../../programming-guide/language-features/statements.md)
