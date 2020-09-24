---
description: '#undef — odwołanie w C#'
title: '#undef — odwołanie w C#'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 7db79be7ea9d8462e09b6ae874bf0ae7d265afe2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150560"
---
# <a name="undef-c-reference"></a><span data-ttu-id="6d86f-103">#undef (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="6d86f-103">#undef (C# Reference)</span></span>

<span data-ttu-id="6d86f-104">`#undef` umożliwia oddefiniowanie symbolu, takiego, że, przy użyciu symbolu jako wyrażenia w dyrektywie [#if](./preprocessor-if.md) , wyrażenie zwróci wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="6d86f-104">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](./preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="6d86f-105">Symbol można zdefiniować za pomocą dyrektywy [#define](./preprocessor-define.md) lub opcji [-define](../compiler-options/define-compiler-option.md) kompilatora.</span><span class="sxs-lookup"><span data-stu-id="6d86f-105">A symbol can be defined either with the [#define](./preprocessor-define.md) directive or the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="6d86f-106">`#undef`Dyrektywa musi znajdować się w pliku przed użyciem wszelkich instrukcji, które nie są również dyrektywami.</span><span class="sxs-lookup"><span data-stu-id="6d86f-106">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d86f-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="6d86f-107">Example</span></span>  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

<span data-ttu-id="6d86f-108">**Nie zdefiniowano debugowania**</span><span class="sxs-lookup"><span data-stu-id="6d86f-108">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="6d86f-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6d86f-109">See also</span></span>

- [<span data-ttu-id="6d86f-110">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="6d86f-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6d86f-111">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="6d86f-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6d86f-112">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="6d86f-112">C# Preprocessor Directives</span></span>](./index.md)
