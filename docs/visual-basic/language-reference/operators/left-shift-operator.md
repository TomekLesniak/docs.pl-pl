---
title: <<, operator
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 77bf26d4e6bb068f9130deed5eb1ecbaee62afce
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866790"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="6af69-102">\<\< Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6af69-102">\<\< Operator (Visual Basic)</span></span>

<span data-ttu-id="6af69-103">Wykonuje arytmetyczne przesunięcie w lewo na wzorcu bitowym.</span><span class="sxs-lookup"><span data-stu-id="6af69-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6af69-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6af69-104">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="6af69-105">Części</span><span class="sxs-lookup"><span data-stu-id="6af69-105">Parts</span></span>  

 `result`  
 <span data-ttu-id="6af69-106">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="6af69-106">Required.</span></span> <span data-ttu-id="6af69-107">Całkowita wartość liczbowa.</span><span class="sxs-lookup"><span data-stu-id="6af69-107">Integral numeric value.</span></span> <span data-ttu-id="6af69-108">Wynik przesunięcia wzorca bitowego.</span><span class="sxs-lookup"><span data-stu-id="6af69-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="6af69-109">Typ danych jest taki sam jak w przypadku programu `pattern` .</span><span class="sxs-lookup"><span data-stu-id="6af69-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="6af69-110">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="6af69-110">Required.</span></span> <span data-ttu-id="6af69-111">Całkowite wyrażenie liczbowe.</span><span class="sxs-lookup"><span data-stu-id="6af69-111">Integral numeric expression.</span></span> <span data-ttu-id="6af69-112">Wzorzec bitowy, który ma zostać przesunięty.</span><span class="sxs-lookup"><span data-stu-id="6af69-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="6af69-113">Typ danych musi być typem całkowitym (,,,,, `SByte` `Byte` `Short` `UShort` `Integer` `UInteger` , `Long` lub `ULong` ).</span><span class="sxs-lookup"><span data-stu-id="6af69-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="6af69-114">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="6af69-114">Required.</span></span> <span data-ttu-id="6af69-115">Wyrażenie liczbowe.</span><span class="sxs-lookup"><span data-stu-id="6af69-115">Numeric expression.</span></span> <span data-ttu-id="6af69-116">Liczba bitów do przesunięcia wzorca bitowego.</span><span class="sxs-lookup"><span data-stu-id="6af69-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="6af69-117">Typ danych musi być `Integer` lub być rozszerzony do `Integer` .</span><span class="sxs-lookup"><span data-stu-id="6af69-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6af69-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6af69-118">Remarks</span></span>  

 <span data-ttu-id="6af69-119">Przesunięcia arytmetyczne nie są cykliczne, co oznacza, że bity przesunięte poza jeden koniec wyniku nie są ponownie wprowadzane na drugim końcu.</span><span class="sxs-lookup"><span data-stu-id="6af69-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="6af69-120">W przypadku przesunięcia w lewo po lewej stronie bity przesunięte poza zakres typu danych wynik są odrzucane, a pozycje bitowe opuszczone po prawej stronie są ustawione na wartość zero.</span><span class="sxs-lookup"><span data-stu-id="6af69-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="6af69-121">Aby zapobiec przesunięciu przez więcej bitów niż w wyniku, Visual Basic maskuje wartość `amount` z maską rozmiaru odpowiadającą typowi danych `pattern` .</span><span class="sxs-lookup"><span data-stu-id="6af69-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="6af69-122">Wartość binarna i z tych wartości są używane na potrzeby przesunięcia.</span><span class="sxs-lookup"><span data-stu-id="6af69-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="6af69-123">Maski rozmiaru są następujące:</span><span class="sxs-lookup"><span data-stu-id="6af69-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="6af69-124">Typ danych `pattern`</span><span class="sxs-lookup"><span data-stu-id="6af69-124">Data type of `pattern`</span></span>|<span data-ttu-id="6af69-125">Maska rozmiaru (dziesiętna)</span><span class="sxs-lookup"><span data-stu-id="6af69-125">Size mask (decimal)</span></span>|<span data-ttu-id="6af69-126">Maska rozmiaru (szesnastkowo)</span><span class="sxs-lookup"><span data-stu-id="6af69-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="6af69-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="6af69-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="6af69-128">7</span><span class="sxs-lookup"><span data-stu-id="6af69-128">7</span></span>|<span data-ttu-id="6af69-129">&H00000007</span><span class="sxs-lookup"><span data-stu-id="6af69-129">&H00000007</span></span>|  
|<span data-ttu-id="6af69-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="6af69-130">`Short`, `UShort`</span></span>|<span data-ttu-id="6af69-131">15</span><span class="sxs-lookup"><span data-stu-id="6af69-131">15</span></span>|<span data-ttu-id="6af69-132">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="6af69-132">&H0000000F</span></span>|  
|<span data-ttu-id="6af69-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="6af69-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="6af69-134">31</span><span class="sxs-lookup"><span data-stu-id="6af69-134">31</span></span>|<span data-ttu-id="6af69-135">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="6af69-135">&H0000001F</span></span>|  
|<span data-ttu-id="6af69-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="6af69-136">`Long`, `ULong`</span></span>|<span data-ttu-id="6af69-137">63</span><span class="sxs-lookup"><span data-stu-id="6af69-137">63</span></span>|<span data-ttu-id="6af69-138">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="6af69-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="6af69-139">Jeśli `amount` jest równa zero, wartość `result` jest taka sama jak wartość `pattern` .</span><span class="sxs-lookup"><span data-stu-id="6af69-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="6af69-140">Jeśli `amount` jest ujemna, jest traktowana jako wartość bez znaku i zamaskowany przy odpowiedniej masce rozmiaru.</span><span class="sxs-lookup"><span data-stu-id="6af69-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="6af69-141">Przesunięcia arytmetyczne nigdy nie generują wyjątków przepełnienia.</span><span class="sxs-lookup"><span data-stu-id="6af69-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6af69-142">`<<`Operator może być *przeciążony*, co oznacza, że Klasa lub struktura może przedefiniować jej zachowanie, gdy operand ma typ tej klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="6af69-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="6af69-143">Jeśli kod używa tego operatora dla takiej klasy lub struktury, upewnij się, że rozumiesz jego ponownie zdefiniowane zachowanie.</span><span class="sxs-lookup"><span data-stu-id="6af69-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="6af69-144">Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6af69-144">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6af69-145">Przykład</span><span class="sxs-lookup"><span data-stu-id="6af69-145">Example</span></span>  

 <span data-ttu-id="6af69-146">Poniższy przykład używa operatora, `<<` Aby przeprowadzić arytmetyczne przesunięcie w lewo na wartościach całkowitych.</span><span class="sxs-lookup"><span data-stu-id="6af69-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="6af69-147">Wynik zawsze ma ten sam typ danych co w przypadku przesunięcia wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="6af69-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="6af69-148">Wyniki poprzedniego przykładu są następujące:</span><span class="sxs-lookup"><span data-stu-id="6af69-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="6af69-149">`result1` jest 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="6af69-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="6af69-150">`result2` jest 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="6af69-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="6af69-151">`result3` is-32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="6af69-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="6af69-152">`result4` jest 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="6af69-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="6af69-153">`result5` jest 0 (przesunięte 15 miejsc w lewo).</span><span class="sxs-lookup"><span data-stu-id="6af69-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="6af69-154">Wartość przesunięcia dla `result4` jest obliczana jako 17 i 15, która jest równa 1.</span><span class="sxs-lookup"><span data-stu-id="6af69-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af69-155">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6af69-155">See also</span></span>

- [<span data-ttu-id="6af69-156">Operatory Bit Shift</span><span class="sxs-lookup"><span data-stu-id="6af69-156">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="6af69-157">Operatory przypisania</span><span class="sxs-lookup"><span data-stu-id="6af69-157">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="6af69-158"><<= — operator</span><span class="sxs-lookup"><span data-stu-id="6af69-158"><<= Operator</span></span>](left-shift-assignment-operator.md)
- [<span data-ttu-id="6af69-159">Kolejność wykonywania działań (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6af69-159">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="6af69-160">Operatory według funkcji</span><span class="sxs-lookup"><span data-stu-id="6af69-160">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="6af69-161">Operatory arytmetyczne w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6af69-161">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
