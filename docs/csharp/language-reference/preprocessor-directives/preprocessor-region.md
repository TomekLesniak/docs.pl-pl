---
description: '#Region — odwołanie w C#'
title: '#Region — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: ed40d895fedb9be271bb389a4f8de69d7ae3f266
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137945"
---
# <a name="region-c-reference"></a><span data-ttu-id="bb64e-103">#region (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="bb64e-103">#region (C# Reference)</span></span>
<span data-ttu-id="bb64e-104">`#region` umożliwia określenie bloku kodu, który można rozwijać lub zwijać podczas korzystania z funkcji tworzenia [konspektu](/visualstudio/ide/outlining) w edytorze kodu.</span><span class="sxs-lookup"><span data-stu-id="bb64e-104">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the code editor.</span></span> <span data-ttu-id="bb64e-105">W przypadku plików o większej liczbie można zwinąć lub ukryć jeden lub więcej regionów, aby można było skupić się na części pliku, nad którym pracujesz.</span><span class="sxs-lookup"><span data-stu-id="bb64e-105">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="bb64e-106">Poniższy przykład pokazuje, jak zdefiniować region:</span><span class="sxs-lookup"><span data-stu-id="bb64e-106">The following example shows how to define a region:</span></span>  
  
```csharp
#region MyClass definition  
public class MyClass
{  
    static void Main()
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a><span data-ttu-id="bb64e-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bb64e-107">Remarks</span></span>  
 <span data-ttu-id="bb64e-108">`#region`Blok musi być zakończony przy użyciu dyrektywy [#endregion](./preprocessor-endregion.md) .</span><span class="sxs-lookup"><span data-stu-id="bb64e-108">A `#region` block must be terminated with a [#endregion](./preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="bb64e-109">`#region`Blok nie może nakładać się na blok [#if](./preprocessor-if.md) .</span><span class="sxs-lookup"><span data-stu-id="bb64e-109">A `#region` block cannot overlap with a [#if](./preprocessor-if.md) block.</span></span> <span data-ttu-id="bb64e-110">Jednak `#region` blok może być zagnieżdżony w `#if` bloku, a `#if` blok może być zagnieżdżony w `#region` bloku.</span><span class="sxs-lookup"><span data-stu-id="bb64e-110">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb64e-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bb64e-111">See also</span></span>

- [<span data-ttu-id="bb64e-112">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="bb64e-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bb64e-113">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="bb64e-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bb64e-114">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="bb64e-114">C# Preprocessor Directives</span></span>](./index.md)
