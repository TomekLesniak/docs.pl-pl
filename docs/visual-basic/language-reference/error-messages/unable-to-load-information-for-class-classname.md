---
title: Nie można załadować informacji dla klasy „<classname>”
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 05c3303db90a396479bc396c5c2395c3afbb59ae
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161611"
---
# <a name="bc30712-unable-to-load-information-for-class-classname"></a><span data-ttu-id="afc01-102">BC30712: nie można załadować informacji dla klasy " \<classname> "</span><span class="sxs-lookup"><span data-stu-id="afc01-102">BC30712: Unable to load information for class '\<classname>'</span></span>

<span data-ttu-id="afc01-103">Wykonano odwołanie do klasy, która jest niedostępna.</span><span class="sxs-lookup"><span data-stu-id="afc01-103">A reference was made to a class that is not available.</span></span>

 <span data-ttu-id="afc01-104">**Identyfikator błędu:** BC30712</span><span class="sxs-lookup"><span data-stu-id="afc01-104">**Error ID:** BC30712</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="afc01-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="afc01-105">To correct this error</span></span>

1. <span data-ttu-id="afc01-106">Sprawdź, czy Klasa jest zdefiniowana i czy nazwa została wpisana poprawnie.</span><span class="sxs-lookup"><span data-stu-id="afc01-106">Verify that the class is defined and that you spelled the name correctly.</span></span>

2. <span data-ttu-id="afc01-107">Spróbuj uzyskać dostęp do jednego z elementów członkowskich zadeklarowanych w module.</span><span class="sxs-lookup"><span data-stu-id="afc01-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="afc01-108">W niektórych przypadkach środowisko debugowania nie może zlokalizować elementów członkowskich, ponieważ moduły, w których są zadeklarowane, nie zostały jeszcze załadowane.</span><span class="sxs-lookup"><span data-stu-id="afc01-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>

## <a name="see-also"></a><span data-ttu-id="afc01-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="afc01-109">See also</span></span>

- [<span data-ttu-id="afc01-110">Debugowanie w Visual Studio</span><span class="sxs-lookup"><span data-stu-id="afc01-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
