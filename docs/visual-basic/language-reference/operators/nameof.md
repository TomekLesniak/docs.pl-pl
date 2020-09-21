---
title: Operator NameOf
description: Dowiedz się, jak używać operatora NameOf w Visual Basic
ms.date: 10/27/2019
f1_keywords:
- NameOf
- vb.NameOf
helpviewer_keywords:
- NameOf operator [Visual Basic]
ms.openlocfilehash: 0e72c4cb0c10113e53067ea4a743ca5ee77bcc95
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828906"
---
# <a name="nameof-operator---visual-basic"></a>Operator NameOf — Visual Basic

`NameOf`Operator uzyskuje nazwę zmiennej, typu lub składowej jako stałą typu String:

```vb
Console.WriteLine(NameOf(System.Collections.Generic))  ' output: Generic
Console.WriteLine(NameOf(List(Of Integer)))  ' output: List
Console.WriteLine(NameOf(List(Of Integer).Count))  ' output: Count
Console.WriteLine(NameOf(List(Of Integer).Add))  ' output: Add

Dim numbers As New List(Of Integer) From { 1, 2, 3 }
Console.WriteLine(NameOf(numbers))  ' output: numbers
Console.WriteLine(NameOf(numbers.Count))  ' output: Count
Console.WriteLine(NameOf(numbers.Add))  ' output: Add
```

Jak pokazano w powyższym przykładzie, w przypadku typu i przestrzeni nazw, wygenerowana nazwa zazwyczaj nie jest w [pełni kwalifikowana](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

`NameOf`Operator jest oceniany w czasie kompilacji i nie ma wpływu na czas wykonywania.

Możesz użyć operatora, `NameOf` Aby kod sprawdzania argumentów był bardziej konserwowany:

```vb
Private _name As String

Public Property Name As String
    Get
        Return _name
    End Get
    Set
        If value Is Nothing Then
            Throw New ArgumentNullException(NameOf(value), $"{NameOf(name)} cannot be null.")
        End If
    End Set
End Property
```

`NameOf`Operator jest dostępny w Visual Basic 14 i nowszych.

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka Visual Basic](../index.md)
- [Operatory (Visual Basic)](index.md)
