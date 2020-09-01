---
description: '#pragma warning — odwołanie w C#'
title: '#pragma warning — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 3085c21db386ca215d48bbe8ade83cd26732242c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137971"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="67f0f-103">#pragma warning (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="67f0f-103">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="67f0f-104">`#pragma warning` można włączać lub wyłączać pewne ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="67f0f-104">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f0f-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="67f0f-105">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="67f0f-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="67f0f-106">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="67f0f-107">Rozdzielana przecinkami lista numerów ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="67f0f-107">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="67f0f-108">Prefiks "CS" jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="67f0f-108">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="67f0f-109">Gdy nie określono żadnych numerów ostrzeżeń, program `disable` wyłącza wszystkie ostrzeżenia i `restore` włącza wszystkie ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="67f0f-109">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67f0f-110">Aby znaleźć numery ostrzegawcze w programie Visual Studio, Skompiluj projekt, a następnie poszukaj numerów ostrzeżeń w oknie **danych wyjściowych** .</span><span class="sxs-lookup"><span data-stu-id="67f0f-110">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67f0f-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="67f0f-111">Example</span></span>  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="67f0f-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="67f0f-112">See also</span></span>

- [<span data-ttu-id="67f0f-113">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="67f0f-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="67f0f-114">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="67f0f-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="67f0f-115">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="67f0f-115">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="67f0f-116">Błędy kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="67f0f-116">C# Compiler Errors</span></span>](../compiler-messages/index.md)
