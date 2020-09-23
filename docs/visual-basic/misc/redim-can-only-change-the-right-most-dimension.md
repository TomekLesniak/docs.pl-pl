---
title: Element "ReDim" może zmienić tylko najwyższy wymiar
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: c3a18bb93d1253628d73919b18fe4614d742d280
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077387"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="f9fdf-102">Element "ReDim" może zmienić tylko najwyższy wymiar</span><span class="sxs-lookup"><span data-stu-id="f9fdf-102">'ReDim' can only change the right-most dimension</span></span>

<span data-ttu-id="f9fdf-103">`ReDim`Instrukcja próbowała użyć `Preserve` słowa kluczowego, aby zmienić wymiar tablicy, która nie jest ostatnim wymiarem.</span><span class="sxs-lookup"><span data-stu-id="f9fdf-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="f9fdf-104">W przypadku używania `Preserve` , można zmienić rozmiar tylko ostatniego wymiaru tablicy.</span><span class="sxs-lookup"><span data-stu-id="f9fdf-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="f9fdf-105">Dla wszystkich innych wymiarów należy określić ten sam rozmiar jak dla istniejącej tablicy.</span><span class="sxs-lookup"><span data-stu-id="f9fdf-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f9fdf-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="f9fdf-106">To correct this error</span></span>  
  
- <span data-ttu-id="f9fdf-107">Usuń `Preserve` słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="f9fdf-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9fdf-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f9fdf-108">See also</span></span>

- [<span data-ttu-id="f9fdf-109">Tablice w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f9fdf-109">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="f9fdf-110">Wymiary tablicy w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f9fdf-110">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="f9fdf-111">ReDim, instrukcja</span><span class="sxs-lookup"><span data-stu-id="f9fdf-111">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="f9fdf-112">Dim, instrukcja</span><span class="sxs-lookup"><span data-stu-id="f9fdf-112">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)
