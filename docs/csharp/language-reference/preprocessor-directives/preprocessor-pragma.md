---
description: '#pragma — odwołanie w C#'
title: '#pragma — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 2788c2589bee149676c5cb2b4212ec7a060a47af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168520"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="04127-103">#pragma (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="04127-103">#pragma (C# Reference)</span></span>

<span data-ttu-id="04127-104">`#pragma` przekazuje specjalne instrukcje kompilatora dla kompilacji pliku, w którym występuje.</span><span class="sxs-lookup"><span data-stu-id="04127-104">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="04127-105">Instrukcje muszą być obsługiwane przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="04127-105">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="04127-106">Innymi słowy, nie można użyć `#pragma` programu do utworzenia niestandardowych instrukcji przetwarzania wstępnego.</span><span class="sxs-lookup"><span data-stu-id="04127-106">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="04127-107">Kompilator języka C# firmy Microsoft obsługuje następujące dwie `#pragma` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="04127-107">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="04127-108">Ostrzeżenie #pragma</span><span class="sxs-lookup"><span data-stu-id="04127-108">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="04127-109">#pragma sum kontrolnych</span><span class="sxs-lookup"><span data-stu-id="04127-109">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="04127-110">Składnia</span><span class="sxs-lookup"><span data-stu-id="04127-110">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="04127-111">Parametry</span><span class="sxs-lookup"><span data-stu-id="04127-111">Parameters</span></span>  

 `pragma-name`  
 <span data-ttu-id="04127-112">Nazwa rozpoznanej dyrektywy pragma.</span><span class="sxs-lookup"><span data-stu-id="04127-112">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="04127-113">Argumenty specyficzne dla dyrektywy pragma.</span><span class="sxs-lookup"><span data-stu-id="04127-113">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04127-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="04127-114">See also</span></span>

- [<span data-ttu-id="04127-115">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="04127-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="04127-116">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="04127-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="04127-117">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="04127-117">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="04127-118">Ostrzeżenie #pragma</span><span class="sxs-lookup"><span data-stu-id="04127-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="04127-119">#pragma sum kontrolnych</span><span class="sxs-lookup"><span data-stu-id="04127-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
