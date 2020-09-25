---
description: '#ostrzeżenie — odwołanie w C#'
title: '#ostrzeżenie — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 9ade723bdca17597dcd56240f506e60f2debf6be
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186422"
---
# <a name="warning-c-reference"></a><span data-ttu-id="d8365-103">#warning (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="d8365-103">#warning (C# Reference)</span></span>

<span data-ttu-id="d8365-104">`#warning` umożliwia wygenerowanie ostrzeżenia kompilatora o poziomie [CS1030](../../misc/cs1030.md) z określonej lokalizacji w kodzie.</span><span class="sxs-lookup"><span data-stu-id="d8365-104">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="d8365-105">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="d8365-105">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="d8365-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d8365-106">Remarks</span></span>

 <span data-ttu-id="d8365-107">Typowym zastosowaniem `#warning` jest w dyrektywie warunkowej.</span><span class="sxs-lookup"><span data-stu-id="d8365-107">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="d8365-108">Istnieje również możliwość wygenerowania błędu zdefiniowanego przez użytkownika przy użyciu [#error](./preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="d8365-108">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8365-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="d8365-109">Example</span></span>  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="d8365-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d8365-110">See also</span></span>

- [<span data-ttu-id="d8365-111">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="d8365-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d8365-112">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="d8365-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d8365-113">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="d8365-113">C# Preprocessor Directives</span></span>](./index.md)
