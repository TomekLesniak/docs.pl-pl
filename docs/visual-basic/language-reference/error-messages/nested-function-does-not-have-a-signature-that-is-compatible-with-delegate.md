---
title: Funkcja zagnieżdżona nie posiada podpisu zgodnego z delegatem „<delegatename>”.
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 0dde340164f1ba80d0e1d9fbb5d17ba6da0a5bc4
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160057"
---
# <a name="bc36532-nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a>BC36532: funkcja zagnieżdżona nie ma sygnatury zgodnej z delegatem " \<delegatename> "

Wyrażenie lambda zostało przypisane do delegata, który ma niezgodny podpis. Na przykład, w poniższym kodzie delegat `Del` ma dwa parametry Integer.

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

Błąd jest wywoływany, jeśli wyrażenie lambda z jednym argumentem jest zadeklarowane jako typ `Del` :

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

**Identyfikator błędu:** BC36532

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

Dostosuj definicję delegata lub przypisane wyrażenie lambda, aby podpisy były zgodne.

## <a name="see-also"></a>Zobacz też

- [Swobodna konwersja delegatów](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Wyrażenia lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
