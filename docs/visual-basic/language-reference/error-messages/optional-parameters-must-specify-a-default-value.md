---
title: Parametry opcjonalne muszą określać wartość domyślną
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 3718fe5c42c8af0948f3b5cb0d120c6876c6f98f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162456"
---
# <a name="bc30812-optional-parameters-must-specify-a-default-value"></a>BC30812: parametry opcjonalne muszą określać wartość domyślną

Parametry opcjonalne muszą podawać wartości domyślne, których można użyć, jeśli żaden parametr nie jest dostarczany przez procedurę wywołującą.

**Identyfikator błędu:** BC30812

## <a name="example"></a>Przykład

Poniższy przykład generuje BC30812:

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

Określ wartości domyślne dla parametrów opcjonalnych:

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a>Zobacz też

- [Opcjonalne](../modifiers/optional.md)
