---
title: Wyrażenia lambda nie są prawidłowe w pierwszym wyrażeniu instrukcji „Select Case"
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 448a685a7c174ce212389842c31066f1c4557cdf
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162534"
---
# <a name="bc36635-lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a>BC36635: wyrażenia lambda nie są prawidłowe w pierwszym wyrażeniu instrukcji "Select Case"

Nie można użyć wyrażenia lambda dla wyrażenia testowego w `Select Case` instrukcji. Wyrażenia lambda zwracają funkcje, a wyrażenie testowe `Select Case` instrukcji musi być podstawowym typem danych.

 Następujący kod powoduje wystąpienie tego błędu:

```vb
' Select Case (Function(arg) arg Is Nothing)
    ' List of the cases.
' End Select
```

 **Identyfikator błędu:** BC36635

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Sprawdź swój kod, aby określić, czy inna, warunkowa konstrukcja, taka jak `If...Then...Else` instrukcja, będzie działała.

- Być może zaplanowano wywołanie funkcji, jak pokazano w poniższym kodzie:

```vb
Dim num? As Integer
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))
    ' List of the cases
End Select
```

## <a name="see-also"></a>Zobacz też

- [Wyrażenia lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [If...Then...Else, instrukcja](../statements/if-then-else-statement.md)
- [Select...Case, instrukcja](../statements/select-case-statement.md)
