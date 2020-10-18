---
title: Wymagane odwołanie do zestawu „<assemblyname>” z klasą bazową „<classname>”
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: d2fb3498219dfe3318ec418ede250de818874ba9
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162339"
---
# <a name="bc30007-reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a><span data-ttu-id="040fb-102">BC30007: odwołanie wymagane do zestawu " \<assemblyname> " zawierającego klasę bazową " \<classname> "</span><span class="sxs-lookup"><span data-stu-id="040fb-102">BC30007: Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'</span></span>

<span data-ttu-id="040fb-103">Wymagane odwołanie do zestawu " \<assemblyname> " zawierającego klasę bazową " \<classname> ".</span><span class="sxs-lookup"><span data-stu-id="040fb-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="040fb-104">Dodaj je do projektu.</span><span class="sxs-lookup"><span data-stu-id="040fb-104">Add one to your project.</span></span>

 <span data-ttu-id="040fb-105">Klasa jest definiowana w bibliotece dołączanej dynamicznie (DLL) lub w zestawie, który nie jest bezpośrednio przywoływany w projekcie.</span><span class="sxs-lookup"><span data-stu-id="040fb-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="040fb-106">Kompilator Visual Basic wymaga odwołania, aby uniknąć niejednoznaczności na wypadek, gdyby Klasa została zdefiniowana w więcej niż jednej bibliotece DLL lub zestawie.</span><span class="sxs-lookup"><span data-stu-id="040fb-106">The Visual Basic compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>

 <span data-ttu-id="040fb-107">**Identyfikator błędu:** BC30007</span><span class="sxs-lookup"><span data-stu-id="040fb-107">**Error ID:** BC30007</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="040fb-108">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="040fb-108">To correct this error</span></span>

- <span data-ttu-id="040fb-109">Dołącz nazwę nieodwołania do biblioteki DLL lub zestawu w odwołaniach do projektu.</span><span class="sxs-lookup"><span data-stu-id="040fb-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>

## <a name="see-also"></a><span data-ttu-id="040fb-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="040fb-110">See also</span></span>

- [<span data-ttu-id="040fb-111">Zarządzanie odwołaniami w projekcie</span><span class="sxs-lookup"><span data-stu-id="040fb-111">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="040fb-112">Rozwiązywanie problemów z przerwanymi odwołaniami</span><span class="sxs-lookup"><span data-stu-id="040fb-112">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
