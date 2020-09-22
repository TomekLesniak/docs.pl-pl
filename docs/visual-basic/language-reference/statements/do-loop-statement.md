---
title: Do...Loop, instrukcja
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: 86a702aefeea1e5e359a579a3f29e9c06f1c619c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865932"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="49ec2-102">Do...Loop — Instrukcja (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49ec2-102">Do...Loop Statement (Visual Basic)</span></span>

<span data-ttu-id="49ec2-103">Powtarza blok instrukcji, gdy `Boolean` warunek jest `True` lub do momentu, aż stanie się `True` .</span><span class="sxs-lookup"><span data-stu-id="49ec2-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49ec2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="49ec2-104">Syntax</span></span>  
  
```vb  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
' -or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="49ec2-105">Części</span><span class="sxs-lookup"><span data-stu-id="49ec2-105">Parts</span></span>  
  
|<span data-ttu-id="49ec2-106">Termin</span><span class="sxs-lookup"><span data-stu-id="49ec2-106">Term</span></span>|<span data-ttu-id="49ec2-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="49ec2-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="49ec2-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="49ec2-108">Required.</span></span> <span data-ttu-id="49ec2-109">Uruchamia definicję `Do` pętli.</span><span class="sxs-lookup"><span data-stu-id="49ec2-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="49ec2-110">Wymagane, chyba że `Until` jest używany.</span><span class="sxs-lookup"><span data-stu-id="49ec2-110">Required unless `Until` is used.</span></span> <span data-ttu-id="49ec2-111">Powtarzaj pętlę `condition` do `False` .</span><span class="sxs-lookup"><span data-stu-id="49ec2-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="49ec2-112">Wymagane, chyba że `While` jest używany.</span><span class="sxs-lookup"><span data-stu-id="49ec2-112">Required unless `While` is used.</span></span> <span data-ttu-id="49ec2-113">Powtarzaj pętlę `condition` do `True` .</span><span class="sxs-lookup"><span data-stu-id="49ec2-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="49ec2-114">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="49ec2-114">Optional.</span></span> <span data-ttu-id="49ec2-115">`Boolean` wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="49ec2-115">`Boolean` expression.</span></span> <span data-ttu-id="49ec2-116">Jeśli `condition` jest `Nothing` , Visual Basic traktuje go jako `False` .</span><span class="sxs-lookup"><span data-stu-id="49ec2-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="49ec2-117">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="49ec2-117">Optional.</span></span> <span data-ttu-id="49ec2-118">Co najmniej jedna instrukcja, która jest powtarzana w czasie lub do, `condition` jest `True` .</span><span class="sxs-lookup"><span data-stu-id="49ec2-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="49ec2-119">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="49ec2-119">Optional.</span></span> <span data-ttu-id="49ec2-120">Przenosi formant do następnej iteracji `Do` pętli.</span><span class="sxs-lookup"><span data-stu-id="49ec2-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="49ec2-121">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="49ec2-121">Optional.</span></span> <span data-ttu-id="49ec2-122">Przenosi kontrolę z `Do` pętli.</span><span class="sxs-lookup"><span data-stu-id="49ec2-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="49ec2-123">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="49ec2-123">Required.</span></span> <span data-ttu-id="49ec2-124">Kończy definicję `Do` pętli.</span><span class="sxs-lookup"><span data-stu-id="49ec2-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49ec2-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="49ec2-125">Remarks</span></span>  

 <span data-ttu-id="49ec2-126">Użyj `Do...Loop` struktury, gdy chcesz powtórzyć zestaw instrukcji przez nieokreśloną liczbę razy, aż warunek zostanie spełniony.</span><span class="sxs-lookup"><span data-stu-id="49ec2-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="49ec2-127">Jeśli chcesz powtórzyć instrukcje określoną liczbę razy, [dla... Kolejną instrukcją](for-next-statement.md) jest zwykle lepszy wybór.</span><span class="sxs-lookup"><span data-stu-id="49ec2-127">If you want to repeat the statements a set number of times, the [For...Next Statement](for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="49ec2-128">Możesz użyć albo `While` `Until` , aby określić `condition` , ale nie oba jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="49ec2-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="49ec2-129">Można testować `condition` tylko jeden raz, na początku lub na końcu pętli.</span><span class="sxs-lookup"><span data-stu-id="49ec2-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="49ec2-130">Jeśli testujesz `condition` na początku pętli (w `Do` instrukcji), pętla może nie działać nawet jeden raz.</span><span class="sxs-lookup"><span data-stu-id="49ec2-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="49ec2-131">Jeśli testujesz na końcu pętli (w `Loop` instrukcji), pętla zawsze jest uruchamiana co najmniej jeden raz.</span><span class="sxs-lookup"><span data-stu-id="49ec2-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="49ec2-132">Warunek zazwyczaj wynika z porównania dwóch wartości, ale może to być dowolne wyrażenie, które daje w wyniku wartość [typu Boolean](../data-types/boolean-data-type.md) ( `True` lub `False` ).</span><span class="sxs-lookup"><span data-stu-id="49ec2-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="49ec2-133">Obejmuje to wartości innych typów danych, takich jak typy liczbowe, które zostały przekonwertowane na `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="49ec2-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="49ec2-134">Pętle można zagnieżdżać `Do` , umieszczając jedną pętlę w innej.</span><span class="sxs-lookup"><span data-stu-id="49ec2-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="49ec2-135">Można również zagnieżdżać różne rodzaje struktur kontroli w obrębie siebie.</span><span class="sxs-lookup"><span data-stu-id="49ec2-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="49ec2-136">Aby uzyskać więcej informacji, zobacz [struktury formantów zagnieżdżonych](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="49ec2-136">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49ec2-137">`Do...Loop`Struktura zapewnia większą elastyczność niż [while... Instrukcja End while](while-end-while-statement.md) , ponieważ umożliwia podjęcie decyzji, czy przerwać pętlę, gdy zostanie ona `condition` zatrzymana `True` `True` .</span><span class="sxs-lookup"><span data-stu-id="49ec2-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="49ec2-138">Umożliwia również przetestowanie `condition` na początku lub na końcu pętli.</span><span class="sxs-lookup"><span data-stu-id="49ec2-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="49ec2-139">Zakończ działanie</span><span class="sxs-lookup"><span data-stu-id="49ec2-139">Exit Do</span></span>  

 <span data-ttu-id="49ec2-140">Instrukcja [exiter](exit-statement.md) może zapewnić alternatywny sposób wyjścia `Do…Loop` .</span><span class="sxs-lookup"><span data-stu-id="49ec2-140">The [Exit Do](exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="49ec2-141">`Exit Do` natychmiast przenosi kontrolę do instrukcji, która następuje po `Loop` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="49ec2-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="49ec2-142">`Exit Do` jest często używany po ocenie pewnego warunku, na przykład w `If...Then...Else` strukturze.</span><span class="sxs-lookup"><span data-stu-id="49ec2-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="49ec2-143">Możesz chcieć zakończyć pętlę, jeśli wykryjesz warunek, który sprawia, że nie jest to konieczne lub niemożliwe do kontynuowania iteracji, na przykład błędnej wartości lub żądania zakończenia.</span><span class="sxs-lookup"><span data-stu-id="49ec2-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="49ec2-144">Jednym z nich `Exit Do` jest przetestowanie stanu, który może spowodować nieskończoną *pętlę*, która jest pętlą, która może uruchamiać dużą lub nawet nieskończoną liczbę razy.</span><span class="sxs-lookup"><span data-stu-id="49ec2-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="49ec2-145">Możesz użyć, `Exit Do` Aby wyjść z pętli.</span><span class="sxs-lookup"><span data-stu-id="49ec2-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="49ec2-146">Możesz dołączyć dowolną liczbę `Exit Do` instrukcji w dowolnym miejscu `Do…Loop` .</span><span class="sxs-lookup"><span data-stu-id="49ec2-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="49ec2-147">W przypadku użycia wewnątrz `Do` pętli zagnieżdżonych, program `Exit Do` przenosi kontrolę z wewnętrznej pętli i na następny wyższy poziom zagnieżdżenia.</span><span class="sxs-lookup"><span data-stu-id="49ec2-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49ec2-148">Przykład</span><span class="sxs-lookup"><span data-stu-id="49ec2-148">Example</span></span>  

 <span data-ttu-id="49ec2-149">W poniższym przykładzie instrukcje w pętli są nadal wykonywane, dopóki `index` zmienna nie będzie większa niż 10.</span><span class="sxs-lookup"><span data-stu-id="49ec2-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="49ec2-150">`Until`Klauzula znajduje się na końcu pętli.</span><span class="sxs-lookup"><span data-stu-id="49ec2-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a><span data-ttu-id="49ec2-151">Przykład</span><span class="sxs-lookup"><span data-stu-id="49ec2-151">Example</span></span>  

 <span data-ttu-id="49ec2-152">W poniższym przykładzie jest używana `While` klauzula zamiast `Until` klauzuli i `condition` jest testowana na początku pętli, a nie na końcu.</span><span class="sxs-lookup"><span data-stu-id="49ec2-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a><span data-ttu-id="49ec2-153">Przykład</span><span class="sxs-lookup"><span data-stu-id="49ec2-153">Example</span></span>  

 <span data-ttu-id="49ec2-154">W poniższym przykładzie, `condition` zatrzymanie pętli, gdy `index` zmienna jest większa niż 100.</span><span class="sxs-lookup"><span data-stu-id="49ec2-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="49ec2-155">`If`Instrukcja w pętli, jednak powoduje `Exit Do` zatrzymanie pętli, gdy zmienna indeksu jest większa niż 10.</span><span class="sxs-lookup"><span data-stu-id="49ec2-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="49ec2-156">Przykład</span><span class="sxs-lookup"><span data-stu-id="49ec2-156">Example</span></span>  

 <span data-ttu-id="49ec2-157">Poniższy przykład odczytuje wszystkie wiersze w pliku tekstowym.</span><span class="sxs-lookup"><span data-stu-id="49ec2-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="49ec2-158"><xref:System.IO.File.OpenText%2A>Metoda otwiera plik i zwraca <xref:System.IO.StreamReader> , który odczytuje znaki.</span><span class="sxs-lookup"><span data-stu-id="49ec2-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="49ec2-159">W `Do...Loop` warunku <xref:System.IO.StreamReader.Peek%2A> Metoda określa, czy istnieją `StreamReader` dodatkowe znaki.</span><span class="sxs-lookup"><span data-stu-id="49ec2-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a><span data-ttu-id="49ec2-160">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="49ec2-160">See also</span></span>

- [<span data-ttu-id="49ec2-161">Struktury pętli</span><span class="sxs-lookup"><span data-stu-id="49ec2-161">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="49ec2-162">For...Next, instrukcja</span><span class="sxs-lookup"><span data-stu-id="49ec2-162">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="49ec2-163">Boolean, typ danych</span><span class="sxs-lookup"><span data-stu-id="49ec2-163">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)
- [<span data-ttu-id="49ec2-164">Zagnieżdżone struktury sterujące</span><span class="sxs-lookup"><span data-stu-id="49ec2-164">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="49ec2-165">Exit, instrukcja</span><span class="sxs-lookup"><span data-stu-id="49ec2-165">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="49ec2-166">While...End While, instrukcja</span><span class="sxs-lookup"><span data-stu-id="49ec2-166">While...End While Statement</span></span>](while-end-while-statement.md)
