---
title: Nie można wykonać operacji, ponieważ katalog docelowy znajduje się w katalogu źródłowym
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: d159b9bb3a765a2fefe99fa15dff42e979fda9e3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91079142"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="40158-102">Nie można wykonać operacji, ponieważ katalog docelowy znajduje się w katalogu źródłowym</span><span class="sxs-lookup"><span data-stu-id="40158-102">Could not complete operation since target directory is under source directory</span></span>

<span data-ttu-id="40158-103">Operacja cykliczna zakończyła się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="40158-103">A cyclic operation has failed.</span></span> <span data-ttu-id="40158-104">Cykliczny cykl operacji i w związku z tym nie można ukończyć.</span><span class="sxs-lookup"><span data-stu-id="40158-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="40158-105">Na przykład obiekt A może próbować dziedziczyć z obiektu B, który z kolei dziedziczy z obiektu A.</span><span class="sxs-lookup"><span data-stu-id="40158-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="40158-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="40158-106">To correct this error</span></span>  
  
- <span data-ttu-id="40158-107">Podczas dziedziczenia upewnij się, że nie ma odwołań cyklicznych.</span><span class="sxs-lookup"><span data-stu-id="40158-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40158-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="40158-108">See also</span></span>

- [<span data-ttu-id="40158-109">Typy błędów</span><span class="sxs-lookup"><span data-stu-id="40158-109">Error Types</span></span>](../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="40158-110">Używanie punktów przerwania w debugerze programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="40158-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
