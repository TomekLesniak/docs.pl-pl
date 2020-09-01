---
description: '#elif — odwołanie w C#'
title: '#elif — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: 3aa9082b392b352091b9fde74a85f9dd155ad7b1
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132290"
---
# <a name="elif-c-reference"></a><span data-ttu-id="4bb93-103">#elif (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="4bb93-103">#elif (C# Reference)</span></span>
<span data-ttu-id="4bb93-104">`#elif` umożliwia utworzenie złożonej dyrektywy warunkowej.</span><span class="sxs-lookup"><span data-stu-id="4bb93-104">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="4bb93-105">`#elif`Wyrażenie zostanie ocenione, jeśli żadna z powyższych [#if](./preprocessor-if.md) lub nie wszystkie poprzednie, opcjonalne wyrażenia dyrektywy nie będą oceniane `#elif` do `true` .</span><span class="sxs-lookup"><span data-stu-id="4bb93-105">The `#elif` expression will be evaluated if neither the preceding [#if](./preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="4bb93-106">Jeśli `#elif` wyrażenie daje w wyniku `true` , kompilator oblicza cały kod między `#elif` i następną dyrektywy warunkowej.</span><span class="sxs-lookup"><span data-stu-id="4bb93-106">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="4bb93-107">Przykład:</span><span class="sxs-lookup"><span data-stu-id="4bb93-107">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="4bb93-108">`==`Aby obliczyć wiele symboli, można użyć operatorów (równość), ( `!=` `&&` i), i `||` (lub).</span><span class="sxs-lookup"><span data-stu-id="4bb93-108">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="4bb93-109">Można również grupować symbole i operatory za pomocą nawiasów.</span><span class="sxs-lookup"><span data-stu-id="4bb93-109">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bb93-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4bb93-110">Remarks</span></span>  
 <span data-ttu-id="4bb93-111">`#elif` jest równoważne użyciu:</span><span class="sxs-lookup"><span data-stu-id="4bb93-111">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="4bb93-112">Użycie `#elif` jest prostsze, ponieważ każdy z nich `#if` wymaga [#endif](./preprocessor-endif.md), a `#elif` może być używany bez dopasowywania `#endif` .</span><span class="sxs-lookup"><span data-stu-id="4bb93-112">Using `#elif` is simpler, because each `#if` requires a [#endif](./preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="4bb93-113">Zobacz [#if](./preprocessor-if.md) , aby zapoznać się z przykładem sposobu korzystania z programu `#elif` .</span><span class="sxs-lookup"><span data-stu-id="4bb93-113">See [#if](./preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb93-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4bb93-114">See also</span></span>

- [<span data-ttu-id="4bb93-115">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="4bb93-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4bb93-116">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="4bb93-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4bb93-117">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="4bb93-117">C# Preprocessor Directives</span></span>](./index.md)
