---
title: Nie można wywnioskować typu elementu „<variablename>”, ponieważ granice pętli i zmienna step nie mogą zostać poszerzone do tego samego typu
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: 1330cbd6567b69df9bd811ced49c6df2e120a0b2
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161212"
---
# <a name="bc30982-type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>BC30982: \<variablename> nie można wywnioskować typu elementu "", ponieważ granice pętli i zmienna kroku nie są rozszerzane do tego samego typu

Zapisano `For...Next` pętlę, w której kompilator nie może wywnioskować typu danych dla zmiennej kontroli pętli, ponieważ spełnione są następujące warunki:

- Typ danych zmiennej sterującej pętli nie jest określony z `As` klauzulą.

- Granice pętli i zmienna kroku zawierają co najmniej dwa typy danych.

- Między typami danych nie istnieje żadna konwersja standardowa.

 W związku z tym kompilator nie może wywnioskować typu danych zmiennej sterującej pętli.

 W poniższym przykładzie zmienna kroku jest znakiem, a granice pętli są liczbami całkowitymi. Ponieważ nie istnieje standardowa konwersja między znakami i liczbami całkowitymi, ten błąd jest zgłaszany.

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

**Identyfikator błędu:** BC30982

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- W razie potrzeby zmień typy granic pętli i zmiennej krokowej, tak aby co najmniej jedna z nich została poszerzona. W poprzednim przykładzie Zmień typ `stepVar` na `Integer` .

  ```vb
  Dim stepVar = 1
  ```

  -lub-

  ```vb
  Dim stepVar As Integer = 1
  ```

- Użyj funkcji jawnej konwersji, aby przekonwertować granice pętli i zmienną krokową na odpowiednie typy. W poprzednim przykładzie Zastosuj `Val` funkcję do `stepVar` .

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [For...Next, instrukcja](../statements/for-next-statement.md)
- [Konwersje jawne i niejawne](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Wnioskowanie o typie lokalnym](../../programming-guide/language-features/variables/local-type-inference.md)
- [Option Infer — Instrukcja](../statements/option-infer-statement.md)
- [Funkcje konwersji typu](../functions/type-conversion-functions.md)
- [Rozszerzanie i zwężanie konwersji](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
