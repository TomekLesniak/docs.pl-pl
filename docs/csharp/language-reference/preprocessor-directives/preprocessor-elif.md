---
description: '#elif — odwołanie w C#'
title: '#elif — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: 383c143792a39bb3abcd255804360ad5e2f8ef74
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168702"
---
# <a name="elif-c-reference"></a><span data-ttu-id="21202-103">#elif (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="21202-103">#elif (C# Reference)</span></span>

<span data-ttu-id="21202-104">`#elif` umożliwia utworzenie złożonej dyrektywy warunkowej.</span><span class="sxs-lookup"><span data-stu-id="21202-104">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="21202-105">`#elif`Wyrażenie zostanie ocenione, jeśli żadna z powyższych [#if](./preprocessor-if.md) lub nie wszystkie poprzednie, opcjonalne wyrażenia dyrektywy nie będą oceniane `#elif` do `true` .</span><span class="sxs-lookup"><span data-stu-id="21202-105">The `#elif` expression will be evaluated if neither the preceding [#if](./preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="21202-106">Jeśli `#elif` wyrażenie daje w wyniku `true` , kompilator oblicza cały kod między `#elif` i następną dyrektywy warunkowej.</span><span class="sxs-lookup"><span data-stu-id="21202-106">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="21202-107">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="21202-107">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="21202-108">`==`Aby obliczyć wiele symboli, można użyć operatorów (równość), ( `!=` `&&` i), i `||` (lub).</span><span class="sxs-lookup"><span data-stu-id="21202-108">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="21202-109">Można również grupować symbole i operatory za pomocą nawiasów.</span><span class="sxs-lookup"><span data-stu-id="21202-109">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21202-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="21202-110">Remarks</span></span>  

 <span data-ttu-id="21202-111">`#elif` jest równoważne użyciu:</span><span class="sxs-lookup"><span data-stu-id="21202-111">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="21202-112">Użycie `#elif` jest prostsze, ponieważ każdy z nich `#if` wymaga [#endif](./preprocessor-endif.md), a `#elif` może być używany bez dopasowywania `#endif` .</span><span class="sxs-lookup"><span data-stu-id="21202-112">Using `#elif` is simpler, because each `#if` requires a [#endif](./preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="21202-113">Zobacz [#if](./preprocessor-if.md) , aby zapoznać się z przykładem sposobu korzystania z programu `#elif` .</span><span class="sxs-lookup"><span data-stu-id="21202-113">See [#if](./preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21202-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="21202-114">See also</span></span>

- [<span data-ttu-id="21202-115">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="21202-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="21202-116">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="21202-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="21202-117">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="21202-117">C# Preprocessor Directives</span></span>](./index.md)
