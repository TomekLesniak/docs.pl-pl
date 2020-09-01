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
ms.openlocfilehash: a7ffca8b39f1bd9f05193bccbb6d90e67fa262c9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132368"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="e3d7a-103">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="e3d7a-103">C# preprocessor directives</span></span>
<span data-ttu-id="e3d7a-104">Ta sekcja zawiera informacje o następujących dyrektywach preprocesora języka C#:</span><span class="sxs-lookup"><span data-stu-id="e3d7a-104">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="e3d7a-105">#if</span><span class="sxs-lookup"><span data-stu-id="e3d7a-105">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="e3d7a-106">#else</span><span class="sxs-lookup"><span data-stu-id="e3d7a-106">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="e3d7a-107">#elif</span><span class="sxs-lookup"><span data-stu-id="e3d7a-107">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="e3d7a-108">#endif</span><span class="sxs-lookup"><span data-stu-id="e3d7a-108">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="e3d7a-109">#define</span><span class="sxs-lookup"><span data-stu-id="e3d7a-109">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="e3d7a-110">#undef</span><span class="sxs-lookup"><span data-stu-id="e3d7a-110">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="e3d7a-111">#warning</span><span class="sxs-lookup"><span data-stu-id="e3d7a-111">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="e3d7a-112">#error</span><span class="sxs-lookup"><span data-stu-id="e3d7a-112">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="e3d7a-113">#line</span><span class="sxs-lookup"><span data-stu-id="e3d7a-113">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="e3d7a-114">#region</span><span class="sxs-lookup"><span data-stu-id="e3d7a-114">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="e3d7a-115">#endregion</span><span class="sxs-lookup"><span data-stu-id="e3d7a-115">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="e3d7a-116">#pragma</span><span class="sxs-lookup"><span data-stu-id="e3d7a-116">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="e3d7a-117">Ostrzeżenie #pragma</span><span class="sxs-lookup"><span data-stu-id="e3d7a-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="e3d7a-118">#pragma sum kontrolnych</span><span class="sxs-lookup"><span data-stu-id="e3d7a-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="e3d7a-119">Więcej informacji i przykłady można znaleźć w poszczególnych tematach.</span><span class="sxs-lookup"><span data-stu-id="e3d7a-119">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="e3d7a-120">Chociaż kompilator nie ma osobnego preprocesora, dyrektywy opisane w tej sekcji są przetwarzane tak, jakby były takie.</span><span class="sxs-lookup"><span data-stu-id="e3d7a-120">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="e3d7a-121">Są one używane do ułatwienia kompilacji warunkowej.</span><span class="sxs-lookup"><span data-stu-id="e3d7a-121">They are used to help in conditional compilation.</span></span> <span data-ttu-id="e3d7a-122">W przeciwieństwie do dyrektyw C i C++, nie można używać tych dyrektyw do tworzenia makr.</span><span class="sxs-lookup"><span data-stu-id="e3d7a-122">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="e3d7a-123">Dyrektywa preprocesora musi być jedyną instrukcją w wierszu.</span><span class="sxs-lookup"><span data-stu-id="e3d7a-123">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3d7a-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e3d7a-124">See also</span></span>

- [<span data-ttu-id="e3d7a-125">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="e3d7a-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e3d7a-126">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="e3d7a-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
