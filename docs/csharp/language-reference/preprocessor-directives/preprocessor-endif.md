---
description: '#endif — odwołanie w C#'
title: '#endif — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 8068a6e437145178fd5c88763c86692a8700c349
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138166"
---
# <a name="endif-c-reference"></a><span data-ttu-id="de261-103">#endif (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="de261-103">#endif (C# Reference)</span></span>
<span data-ttu-id="de261-104">`#endif` Określa koniec dyrektywy warunkowej, która zaczyna się od dyrektywy [#if](./preprocessor-if.md) .</span><span class="sxs-lookup"><span data-stu-id="de261-104">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="de261-105">Przykład:</span><span class="sxs-lookup"><span data-stu-id="de261-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="de261-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="de261-106">Remarks</span></span>  
 <span data-ttu-id="de261-107">Dyrektywa warunkowa, rozpoczynająca się od `#if` dyrektywy, musi zostać jawnie zakończona `#endif` dyrektywą.</span><span class="sxs-lookup"><span data-stu-id="de261-107">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="de261-108">Zobacz [#if](./preprocessor-if.md) , aby zapoznać się z przykładem sposobu korzystania z programu `#endif` .</span><span class="sxs-lookup"><span data-stu-id="de261-108">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de261-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="de261-109">See also</span></span>

- [<span data-ttu-id="de261-110">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="de261-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="de261-111">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="de261-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="de261-112">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="de261-112">C# Preprocessor Directives</span></span>](./index.md)
