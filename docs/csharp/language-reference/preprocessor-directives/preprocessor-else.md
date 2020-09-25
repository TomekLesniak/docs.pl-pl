---
description: '#Odwołanie w języku C#'
title: '#Odwołanie w języku C#'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: f0dc8c34672c3e9e5a2207211794fbc8099640c5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168676"
---
# <a name="else-c-reference"></a><span data-ttu-id="1303e-103">#else (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="1303e-103">#else (C# Reference)</span></span>

<span data-ttu-id="1303e-104">`#else` umożliwia utworzenie złożonej dyrektywy warunkowej, tak aby w przypadku braku wyrażeń w powyższym [#if](./preprocessor-if.md) lub (opcjonalnie) [#elif](./preprocessor-elif.md) dyrektywy nie były oceniane do `true` , kompilator oceni cały kod między i po `#else` nim `#endif` .</span><span class="sxs-lookup"><span data-stu-id="1303e-104">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1303e-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1303e-105">Remarks</span></span>  

 <span data-ttu-id="1303e-106">[#endif](./preprocessor-endif.md) musi być następną dyrektywą preprocesora `#else` .</span><span class="sxs-lookup"><span data-stu-id="1303e-106">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="1303e-107">Zobacz [#if](./preprocessor-if.md) , aby zapoznać się z przykładem sposobu korzystania z programu `#else` .</span><span class="sxs-lookup"><span data-stu-id="1303e-107">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1303e-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1303e-108">See also</span></span>

- [<span data-ttu-id="1303e-109">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="1303e-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1303e-110">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="1303e-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1303e-111">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="1303e-111">C# Preprocessor Directives</span></span>](./index.md)
