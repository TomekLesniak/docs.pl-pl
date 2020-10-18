---
title: Typ „<typename>” nie ma konstruktorów
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 249bcb7020f26c7c43d560e91ef7a34e4dc64470
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161182"
---
# <a name="bc30251-type-typename-has-no-constructors"></a><span data-ttu-id="b734c-102">BC30251: typ " \<typename> " nie ma konstruktorów</span><span class="sxs-lookup"><span data-stu-id="b734c-102">BC30251: Type '\<typename>' has no constructors</span></span>

<span data-ttu-id="b734c-103">Typ nie obsługuje wywołania do `Sub New()` .</span><span class="sxs-lookup"><span data-stu-id="b734c-103">A type does not support a call to `Sub New()`.</span></span> <span data-ttu-id="b734c-104">Jedną z możliwych przyczyn jest uszkodzony kompilator lub plik binarny.</span><span class="sxs-lookup"><span data-stu-id="b734c-104">One possible cause is a corrupted compiler or binary file.</span></span>

 <span data-ttu-id="b734c-105">**Identyfikator błędu:** BC30251</span><span class="sxs-lookup"><span data-stu-id="b734c-105">**Error ID:** BC30251</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b734c-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="b734c-106">To correct this error</span></span>

1. <span data-ttu-id="b734c-107">Jeśli typ znajduje się w innym projekcie lub w pliku, do którego istnieje odwołanie, zainstaluj ponownie projekt lub plik.</span><span class="sxs-lookup"><span data-stu-id="b734c-107">If the type is in a different project or in a referenced file, reinstall the project or file.</span></span>

2. <span data-ttu-id="b734c-108">Jeśli typ znajduje się w tym samym projekcie, Skompiluj ponownie zestaw zawierający typ.</span><span class="sxs-lookup"><span data-stu-id="b734c-108">If the type is in the same project, recompile the assembly containing the type.</span></span>

3. <span data-ttu-id="b734c-109">Jeśli błąd powtarza się, zainstaluj ponownie kompilator Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b734c-109">If the error recurs, reinstall the Visual Basic compiler.</span></span>

4. <span data-ttu-id="b734c-110">Jeśli błąd będzie się powtarzać, Zbierz informacje o okolicznościach i powiadom usługi pomocy technicznej firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b734c-110">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="b734c-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b734c-111">See also</span></span>

- [<span data-ttu-id="b734c-112">Obiekty i klasy</span><span class="sxs-lookup"><span data-stu-id="b734c-112">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="b734c-113">Porozmawiaj z nami</span><span class="sxs-lookup"><span data-stu-id="b734c-113">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
