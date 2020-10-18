---
title: Parametrów typu nie można używać jako kwalifikatorów
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 14e6094b0cc129eba86db1808c0f0575955f5e75
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161195"
---
# <a name="bc32098-type-parameters-cannot-be-used-as-qualifiers"></a>BC32098: parametry typu nie mogą być używane jako kwalifikatory

Element programistyczny jest kwalifikowana za pomocą ciągu kwalifikacji, który zawiera parametr typu.

Parametr typu reprezentuje wymaganie dla typu, który ma zostać dostarczony podczas konstruowania typu ogólnego. Nie reprezentuje określonego zdefiniowanego typu. Ciąg kwalifikacji musi zawierać tylko elementy, które są zdefiniowane w czasie kompilacji.

Następujący kod może generować ten błąd:

```vb
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean

    Dim saveText As c.Text
    ' Insert code to look for badText within saveText.
End Function
```

 **Identyfikator błędu:** BC32098

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Usuń parametr typu z ciągu kwalifikacji lub zastąp go zdefiniowanym typem.

2. Jeśli musisz użyć skonstruowanego typu do zlokalizowania kwalifikowanego elementu programistycznego, musisz użyć dodatkowej logiki programu.

## <a name="see-also"></a>Zobacz też

- [Odwołania do elementów zadeklarowanych](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Typy ogólne w Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Lista typów](../statements/type-list.md)
