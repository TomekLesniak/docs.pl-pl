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
# <a name="error-c-reference"></a><span data-ttu-id="5a586-102">#error (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="5a586-102">#error (C# Reference)</span></span>

<span data-ttu-id="5a586-103">`#error` umożliwia wygenerowanie [CS1029](../compiler-messages/cs1029.md) błędu zdefiniowanego przez użytkownika z określonej lokalizacji w kodzie.</span><span class="sxs-lookup"><span data-stu-id="5a586-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="5a586-104">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="5a586-104">For example:</span></span>

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> <span data-ttu-id="5a586-105">Kompilator traktuje `#error version` się w specjalny sposób i zgłasza błąd kompilatora, CS8304 z komunikatem zawierającym używane wersje kompilatora i języka.</span><span class="sxs-lookup"><span data-stu-id="5a586-105">The compiler treats `#error version` in a special way and reports a compiler error, CS8304, with a message containing the used compiler and language versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a586-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5a586-106">Remarks</span></span>

<span data-ttu-id="5a586-107">Typowym zastosowaniem `#error` jest w dyrektywie warunkowej.</span><span class="sxs-lookup"><span data-stu-id="5a586-107">A common use of `#error` is in a conditional directive.</span></span>

<span data-ttu-id="5a586-108">Istnieje również możliwość wygenerowania ostrzeżenia zdefiniowanego przez użytkownika za pomocą [#warning](./preprocessor-warning.md).</span><span class="sxs-lookup"><span data-stu-id="5a586-108">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>

## <a name="example"></a><span data-ttu-id="5a586-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="5a586-109">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5a586-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5a586-110">See also</span></span>

- [<span data-ttu-id="5a586-111">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="5a586-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5a586-112">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="5a586-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5a586-113">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="5a586-113">C# Preprocessor Directives</span></span>](./index.md)
