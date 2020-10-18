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
# <a name="bc33107-first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>BC33107: pierwszy operand w binarnym wyrażeniu "If" musi dopuszczać wartość null lub typ referencyjny

`If`Wyrażenie może przyjmować dwa lub trzy argumenty. W przypadku wysyłania tylko dwóch argumentów pierwszy argument musi być typem referencyjnym lub typem wartości null. Jeśli pierwszy argument ma wartość inną niż `Nothing` , jest zwracana. Jeśli pierwszy argument ma wartość `Nothing` , drugi argument jest obliczany i zwracany.

 Na przykład poniższy kod zawiera dwa `If` wyrażenia, jeden z trzema argumentami i jeden z dwoma argumentami. Wyrażenia obliczają i zwracają tę samą wartość.

```vb
' firstChoice is a nullable value type.
Dim firstChoice? As Integer = Nothing
Dim secondChoice As Integer = 1128
' If expression with three arguments.
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))
' If expression with two arguments.
Console.WriteLine(If(firstChoice, secondChoice))
```

 Następujące wyrażenia powodują wystąpienie tego błędu:

```vb
Dim choice1 = 4
Dim choice2 = 5
Dim booleanVar = True

' Not valid.
'Console.WriteLine(If(choice1 < choice2, 1))
' Not valid.
'Console.WriteLine(If(booleanVar, "Test returns True."))
```

 **Identyfikator błędu:** BC33107

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Jeśli nie możesz zmienić kodu tak, aby pierwszy argument był typem wartości null lub typem referencyjnym, rozważ konwersję na wyrażenie z trzema argumentami `If` lub do `If...Then...Else` instrukcji.

```vb
Console.WriteLine(If(choice1 < choice2, 1, 2))
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))
```

## <a name="see-also"></a>Zobacz też

- [If, operator](../operators/if-operator.md)
- [If...Then...Else, instrukcja](../statements/if-then-else-statement.md)
- [Typy wartości null](../../programming-guide/language-features/data-types/nullable-value-types.md)
