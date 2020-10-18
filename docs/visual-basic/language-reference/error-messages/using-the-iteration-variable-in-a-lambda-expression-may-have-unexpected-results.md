---
title: Użycie zmiennej iteracyjnej w wyrażeniu lambda może spowodować nieoczekiwane wyniki
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: d0deea94084565ea91debe2b6db30def4cd9e00e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161494"
---
# <a name="bc42324-using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="bc0b2-102">BC42324: użycie zmiennej iteracji w wyrażeniu lambda może mieć nieoczekiwane wyniki</span><span class="sxs-lookup"><span data-stu-id="bc0b2-102">BC42324: Using the iteration variable in a lambda expression may have unexpected results</span></span>

<span data-ttu-id="bc0b2-103">Użycie zmiennej iteracji w wyrażeniu lambda może mieć nieoczekiwane wyniki.</span><span class="sxs-lookup"><span data-stu-id="bc0b2-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="bc0b2-104">Zamiast tego należy utworzyć zmienną lokalną wewnątrz pętli i przypisać ją do wartości zmiennej iteracji.</span><span class="sxs-lookup"><span data-stu-id="bc0b2-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>

 <span data-ttu-id="bc0b2-105">To ostrzeżenie jest wyświetlane, gdy w wyrażeniu lambda, który jest zadeklarowany wewnątrz pętli, jest używana zmienna iteracji pętli.</span><span class="sxs-lookup"><span data-stu-id="bc0b2-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="bc0b2-106">Na przykład poniższy przykład powoduje wyświetlenie ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="bc0b2-106">For example, the following example causes the warning to appear.</span></span>

```vb
For i As Integer = 1 To 10
    ' The warning is given for the use of i.
    Dim exampleFunc As Func(Of Integer) = Function() i
Next
```

 <span data-ttu-id="bc0b2-107">Poniższy przykład pokazuje nieoczekiwane wyniki, które mogą wystąpić.</span><span class="sxs-lookup"><span data-stu-id="bc0b2-107">The following example shows the unexpected results that might occur.</span></span>

```vb
Module Module1
    Sub Main()
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}

        For i As Integer = 0 To 4
            array1(i) = Function() i
        Next

        For Each funcElement In array1
            System.Console.WriteLine(funcElement())
        Next

    End Sub
End Module
```

 <span data-ttu-id="bc0b2-108">`For`Pętla tworzy tablicę wyrażeń lambda, z których każdy zwraca wartość zmiennej iteracji pętli `i` .</span><span class="sxs-lookup"><span data-stu-id="bc0b2-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="bc0b2-109">Gdy wyrażenia lambda są oceniane w `For Each` pętli, może się zdarzyć, że będą widoczne wartości 0, 1, 2, 3 i 4 `i` `For` .</span><span class="sxs-lookup"><span data-stu-id="bc0b2-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="bc0b2-110">Zamiast tego zobaczysz końcową wartość `i` wyświetlaną pięć razy:</span><span class="sxs-lookup"><span data-stu-id="bc0b2-110">Instead, you see the final value of `i` displayed five times:</span></span>

 `5`

 `5`

 `5`

 `5`

 `5`

 <span data-ttu-id="bc0b2-111">Domyślnie ten komunikat jest ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="bc0b2-111">By default, this message is a warning.</span></span> <span data-ttu-id="bc0b2-112">Aby uzyskać więcej informacji na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędów, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="bc0b2-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="bc0b2-113">**Identyfikator błędu:** BC42324</span><span class="sxs-lookup"><span data-stu-id="bc0b2-113">**Error ID:** BC42324</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="bc0b2-114">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="bc0b2-114">To correct this error</span></span>

- <span data-ttu-id="bc0b2-115">Przypisz wartość zmiennej iteracji do zmiennej lokalnej i Użyj zmiennej lokalnej w wyrażeniu lambda.</span><span class="sxs-lookup"><span data-stu-id="bc0b2-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>

```vb
Module Module1
    Sub Main()
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}

        For i As Integer = 0 To 4
            Dim j = i
            array1(i) = Function() j
        Next

        For Each funcElement In array1
            System.Console.WriteLine(funcElement())
        Next

    End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="bc0b2-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bc0b2-116">See also</span></span>

- [<span data-ttu-id="bc0b2-117">Wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="bc0b2-117">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
