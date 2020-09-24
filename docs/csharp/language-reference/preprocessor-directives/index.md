---
description: Dyrektywy preprocesora języka C#
title: Dyrektywy preprocesora języka C#
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: 210a024a8062f5070b2a500384f51b37c9d802c0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157957"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="b2955-103">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="b2955-103">C# preprocessor directives</span></span>

<span data-ttu-id="b2955-104">Ta sekcja zawiera informacje o następujących dyrektywach preprocesora języka C#:</span><span class="sxs-lookup"><span data-stu-id="b2955-104">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="b2955-105">#if</span><span class="sxs-lookup"><span data-stu-id="b2955-105">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="b2955-106">#else</span><span class="sxs-lookup"><span data-stu-id="b2955-106">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="b2955-107">#elif</span><span class="sxs-lookup"><span data-stu-id="b2955-107">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="b2955-108">#endif</span><span class="sxs-lookup"><span data-stu-id="b2955-108">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="b2955-109">#define</span><span class="sxs-lookup"><span data-stu-id="b2955-109">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="b2955-110">#undef</span><span class="sxs-lookup"><span data-stu-id="b2955-110">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="b2955-111">#warning</span><span class="sxs-lookup"><span data-stu-id="b2955-111">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="b2955-112">#error</span><span class="sxs-lookup"><span data-stu-id="b2955-112">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="b2955-113">#line</span><span class="sxs-lookup"><span data-stu-id="b2955-113">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="b2955-114">#region</span><span class="sxs-lookup"><span data-stu-id="b2955-114">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="b2955-115">#endregion</span><span class="sxs-lookup"><span data-stu-id="b2955-115">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="b2955-116">#pragma</span><span class="sxs-lookup"><span data-stu-id="b2955-116">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="b2955-117">Ostrzeżenie #pragma</span><span class="sxs-lookup"><span data-stu-id="b2955-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="b2955-118">#pragma sum kontrolnych</span><span class="sxs-lookup"><span data-stu-id="b2955-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="b2955-119">Więcej informacji i przykłady można znaleźć w poszczególnych tematach.</span><span class="sxs-lookup"><span data-stu-id="b2955-119">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="b2955-120">Chociaż kompilator nie ma osobnego preprocesora, dyrektywy opisane w tej sekcji są przetwarzane tak, jakby były takie.</span><span class="sxs-lookup"><span data-stu-id="b2955-120">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="b2955-121">Są one używane do ułatwienia kompilacji warunkowej.</span><span class="sxs-lookup"><span data-stu-id="b2955-121">They are used to help in conditional compilation.</span></span> <span data-ttu-id="b2955-122">W przeciwieństwie do dyrektyw C i C++, nie można używać tych dyrektyw do tworzenia makr.</span><span class="sxs-lookup"><span data-stu-id="b2955-122">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="b2955-123">Dyrektywa preprocesora musi być jedyną instrukcją w wierszu.</span><span class="sxs-lookup"><span data-stu-id="b2955-123">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2955-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b2955-124">See also</span></span>

- [<span data-ttu-id="b2955-125">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="b2955-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b2955-126">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="b2955-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
