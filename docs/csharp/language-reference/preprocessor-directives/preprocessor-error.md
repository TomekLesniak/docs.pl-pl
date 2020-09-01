---
description: '#błąd — odwołanie w C#'
title: '#błąd — odwołanie w C#'
ms.date: 08/24/2020
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 76325901c5e39f340545b186a0aa9546cd853ff8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138101"
---
# <a name="error-c-reference"></a>#error (odwołanie w C#)

`#error` umożliwia wygenerowanie [CS1029](../compiler-messages/cs1029.md) błędu zdefiniowanego przez użytkownika z określonej lokalizacji w kodzie. Przykład:

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> Kompilator traktuje `#error version` się w specjalny sposób i zgłasza błąd kompilatora, CS8304 z komunikatem zawierającym używane wersje kompilatora i języka.

## <a name="remarks"></a>Uwagi

Typowym zastosowaniem `#error` jest w dyrektywie warunkowej.

Istnieje również możliwość wygenerowania ostrzeżenia zdefiniowanego przez użytkownika za pomocą [#warning](./preprocessor-warning.md).

## <a name="example"></a>Przykład

```csharp
// preprocessor_error.cs
// CS1029 expected
#define DEBUG
class MainClass
{
    static void Main()
    {
#if DEBUG
#error DEBUG is defined
#endif
    }
}
```

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
