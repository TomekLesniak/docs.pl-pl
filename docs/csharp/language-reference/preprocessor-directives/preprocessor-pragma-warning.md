---
description: '#pragma warning — odwołanie w C#'
title: '#pragma warning — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 5b67d384e37a5e509ce8ebcc5ddeb16a4437ea2b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91168533"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="f1611-103">#pragma warning (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="f1611-103">#pragma warning (C# Reference)</span></span>

<span data-ttu-id="f1611-104">`#pragma warning` można włączać lub wyłączać pewne ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="f1611-104">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1611-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f1611-105">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1611-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="f1611-106">Parameters</span></span>  

 `warning-list`  
 <span data-ttu-id="f1611-107">Rozdzielana przecinkami lista numerów ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="f1611-107">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="f1611-108">Prefiks "CS" jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="f1611-108">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="f1611-109">Gdy nie określono żadnych numerów ostrzeżeń, program `disable` wyłącza wszystkie ostrzeżenia i `restore` włącza wszystkie ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="f1611-109">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1611-110">Aby znaleźć numery ostrzegawcze w programie Visual Studio, Skompiluj projekt, a następnie poszukaj numerów ostrzeżeń w oknie **danych wyjściowych** .</span><span class="sxs-lookup"><span data-stu-id="f1611-110">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1611-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="f1611-111">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f1611-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f1611-112">See also</span></span>

- [<span data-ttu-id="f1611-113">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="f1611-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f1611-114">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="f1611-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f1611-115">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="f1611-115">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="f1611-116">Błędy kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="f1611-116">C# Compiler Errors</span></span>](../compiler-messages/index.md)
