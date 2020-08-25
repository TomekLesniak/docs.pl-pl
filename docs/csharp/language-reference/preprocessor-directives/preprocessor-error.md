---
title: '#błąd — odwołanie w C#'
ms.date: 08/24/2020
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: cc1e0640886e3f3c1c74a54f64961a56c8b030e4
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812370"
---
# <a name="error-c-reference"></a>#error (odwołanie w C#)

`#error` umożliwia wygenerowanie [CS1029](../compiler-messages/cs1029.md) błędu zdefiniowanego przez użytkownika z określonej lokalizacji w kodzie. Na przykład:

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
