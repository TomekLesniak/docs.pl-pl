---
description: '#endif — odwołanie w C#'
title: '#endif — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 0ccc00ceab2aa67c77140e3ef09907ba260d7e9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168637"
---
# <a name="endif-c-reference"></a><span data-ttu-id="b9b3e-103">#endif (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="b9b3e-103">#endif (C# Reference)</span></span>

<span data-ttu-id="b9b3e-104">`#endif` Określa koniec dyrektywy warunkowej, która zaczyna się od dyrektywy [#if](./preprocessor-if.md) .</span><span class="sxs-lookup"><span data-stu-id="b9b3e-104">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="b9b3e-105">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b9b3e-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="b9b3e-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b9b3e-106">Remarks</span></span>  

 <span data-ttu-id="b9b3e-107">Dyrektywa warunkowa, rozpoczynająca się od `#if` dyrektywy, musi zostać jawnie zakończona `#endif` dyrektywą.</span><span class="sxs-lookup"><span data-stu-id="b9b3e-107">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="b9b3e-108">Zobacz [#if](./preprocessor-if.md) , aby zapoznać się z przykładem sposobu korzystania z programu `#endif` .</span><span class="sxs-lookup"><span data-stu-id="b9b3e-108">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b3e-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b9b3e-109">See also</span></span>

- [<span data-ttu-id="b9b3e-110">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="b9b3e-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b9b3e-111">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="b9b3e-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b9b3e-112">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="b9b3e-112">C# Preprocessor Directives</span></span>](./index.md)
