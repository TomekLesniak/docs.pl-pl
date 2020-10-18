---
title: Typem pierwszego operandu w binarnym wyrażeniu „If” musi być typ zerowalny lub typ referencyjny
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: bca9b74a68815b4e5a3bb2dc114b9031cdf24099
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162742"
---
# <a name="bc33107-first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="0a9a0-102">BC33107: pierwszy operand w binarnym wyrażeniu "If" musi dopuszczać wartość null lub typ referencyjny</span><span class="sxs-lookup"><span data-stu-id="0a9a0-102">BC33107: First operand in a binary 'If' expression must be nullable or a reference type</span></span>

<span data-ttu-id="0a9a0-103">`If`Wyrażenie może przyjmować dwa lub trzy argumenty.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="0a9a0-104">W przypadku wysyłania tylko dwóch argumentów pierwszy argument musi być typem referencyjnym lub typem wartości null.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-104">When you send only two arguments, the first argument must be a reference type or a nullable value type.</span></span> <span data-ttu-id="0a9a0-105">Jeśli pierwszy argument ma wartość inną niż `Nothing` , jest zwracana.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="0a9a0-106">Jeśli pierwszy argument ma wartość `Nothing` , drugi argument jest obliczany i zwracany.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>

 <span data-ttu-id="0a9a0-107">Na przykład poniższy kod zawiera dwa `If` wyrażenia, jeden z trzema argumentami i jeden z dwoma argumentami.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="0a9a0-108">Wyrażenia obliczają i zwracają tę samą wartość.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-108">The expressions calculate and return the same value.</span></span>

```vb
' firstChoice is a nullable value type.
Dim firstChoice? As Integer = Nothing
Dim secondChoice As Integer = 1128
' If expression with three arguments.
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))
' If expression with two arguments.
Console.WriteLine(If(firstChoice, secondChoice))
```

 <span data-ttu-id="0a9a0-109">Następujące wyrażenia powodują wystąpienie tego błędu:</span><span class="sxs-lookup"><span data-stu-id="0a9a0-109">The following expressions cause this error:</span></span>

```vb
Dim choice1 = 4
Dim choice2 = 5
Dim booleanVar = True

' Not valid.
'Console.WriteLine(If(choice1 < choice2, 1))
' Not valid.
'Console.WriteLine(If(booleanVar, "Test returns True."))
```

 <span data-ttu-id="0a9a0-110">**Identyfikator błędu:** BC33107</span><span class="sxs-lookup"><span data-stu-id="0a9a0-110">**Error ID:** BC33107</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0a9a0-111">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="0a9a0-111">To correct this error</span></span>

- <span data-ttu-id="0a9a0-112">Jeśli nie możesz zmienić kodu tak, aby pierwszy argument był typem wartości null lub typem referencyjnym, rozważ konwersję na wyrażenie z trzema argumentami `If` lub do `If...Then...Else` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="0a9a0-112">If you cannot change the code so that the first argument is a nullable value type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>

```vb
Console.WriteLine(If(choice1 < choice2, 1, 2))
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))
```

## <a name="see-also"></a><span data-ttu-id="0a9a0-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0a9a0-113">See also</span></span>

- [<span data-ttu-id="0a9a0-114">If, operator</span><span class="sxs-lookup"><span data-stu-id="0a9a0-114">If Operator</span></span>](../operators/if-operator.md)
- [<span data-ttu-id="0a9a0-115">If...Then...Else, instrukcja</span><span class="sxs-lookup"><span data-stu-id="0a9a0-115">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="0a9a0-116">Typy wartości null</span><span class="sxs-lookup"><span data-stu-id="0a9a0-116">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
