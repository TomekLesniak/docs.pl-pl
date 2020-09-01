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
# <a name="error-c-reference"></a><span data-ttu-id="259a2-103">#error (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="259a2-103">#error (C# Reference)</span></span>

<span data-ttu-id="259a2-104">`#error` umożliwia wygenerowanie [CS1029](../compiler-messages/cs1029.md) błędu zdefiniowanego przez użytkownika z określonej lokalizacji w kodzie.</span><span class="sxs-lookup"><span data-stu-id="259a2-104">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="259a2-105">Przykład:</span><span class="sxs-lookup"><span data-stu-id="259a2-105">For example:</span></span>

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> <span data-ttu-id="259a2-106">Kompilator traktuje `#error version` się w specjalny sposób i zgłasza błąd kompilatora, CS8304 z komunikatem zawierającym używane wersje kompilatora i języka.</span><span class="sxs-lookup"><span data-stu-id="259a2-106">The compiler treats `#error version` in a special way and reports a compiler error, CS8304, with a message containing the used compiler and language versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="259a2-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="259a2-107">Remarks</span></span>

<span data-ttu-id="259a2-108">Typowym zastosowaniem `#error` jest w dyrektywie warunkowej.</span><span class="sxs-lookup"><span data-stu-id="259a2-108">A common use of `#error` is in a conditional directive.</span></span>

<span data-ttu-id="259a2-109">Istnieje również możliwość wygenerowania ostrzeżenia zdefiniowanego przez użytkownika za pomocą [#warning](./preprocessor-warning.md).</span><span class="sxs-lookup"><span data-stu-id="259a2-109">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>

## <a name="example"></a><span data-ttu-id="259a2-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="259a2-110">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="259a2-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="259a2-111">See also</span></span>

- [<span data-ttu-id="259a2-112">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="259a2-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="259a2-113">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="259a2-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="259a2-114">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="259a2-114">C# Preprocessor Directives</span></span>](./index.md)
