---
title: Atrybut „Extension” można stosować tylko w deklaracjach „Module”, „Sub” lub „Function”
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: bd4d14721b93800831dbce897535b4f5956fe9c7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160753"
---
# <a name="bc36550-extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>BC36550: atrybut "Extension" może być stosowany tylko do deklaracji "module", "Sub" lub "Function"

Jedynym sposobem rozszerzania typu danych w Visual Basic jest zdefiniowanie metody rozszerzającej wewnątrz modułu standardowego. Metoda rozszerzenia może być `Sub` procedurą lub `Function` procedurą. Wszystkie metody rozszerzenia muszą być oznaczone atrybutem rozszerzenia, `<Extension()>` z <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> przestrzeni nazw. Opcjonalnie moduł, który zawiera metodę rozszerzenia, może być oznaczony w taki sam sposób. Żadne inne użycie atrybutu Extension nie jest prawidłowe.

**Identyfikator błędu:** BC36550

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Usuń atrybut rozszerzenia.

- Przeprojektowanie rozszerzenia jako metody zdefiniowanej w otaczającym module.

## <a name="example"></a>Przykład

W poniższym przykładzie zdefiniowano `Print` metodę dla `String` typu danych.

```vb
Imports StringUtility
Imports System.Runtime.CompilerServices
Namespace StringUtility
    <Extension()>
    Module StringExtensions
        <Extension()>
        Public Sub Print (ByVal str As String)
            Console.WriteLine(str)
        End Sub
    End Module
End Namespace
```

## <a name="see-also"></a>Zobacz też

- [Przegląd atrybutów](../../programming-guide/concepts/attributes/index.md)
- [Metody rozszerzające](../../programming-guide/language-features/procedures/extension-methods.md)
- [Module — Instrukcja](../statements/module-statement.md)
