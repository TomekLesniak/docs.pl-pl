---
title: Element „<name1>” jest niejednoznaczny, po imporcie z przestrzeni nazw lub typów „<name2>”
ms.date: 07/20/2015
f1_keywords:
- vbc30561
- bc30561
helpviewer_keywords:
- BC30561
ms.assetid: 761091f7-1018-4299-b481-3966a4a2c126
ms.openlocfilehash: 73cc604f1e3a06687ca93779a01e698512be198b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160187"
---
# <a name="bc30561-name1-is-ambiguous-imported-from-the-namespaces-or-types-name2"></a><span data-ttu-id="52dd9-102">BC30561: element " \<name1> " jest niejednoznaczny, importowany z przestrzeni nazw lub typów " \<name2> "</span><span class="sxs-lookup"><span data-stu-id="52dd9-102">BC30561: '\<name1>' is ambiguous, imported from the namespaces or types '\<name2>'</span></span>

<span data-ttu-id="52dd9-103">Podana nazwa jest niejednoznaczna i dlatego powoduje konflikt z inną nazwą.</span><span class="sxs-lookup"><span data-stu-id="52dd9-103">You have provided a name that is ambiguous and therefore conflicts with another name.</span></span> <span data-ttu-id="52dd9-104">Kompilator Visual Basic nie ma żadnych reguł rozwiązywania konfliktów; należy samodzielnie odróżnić nazwy.</span><span class="sxs-lookup"><span data-stu-id="52dd9-104">The Visual Basic compiler does not have any conflict resolution rules; you must disambiguate names yourself.</span></span>

 <span data-ttu-id="52dd9-105">**Identyfikator błędu:** BC30561</span><span class="sxs-lookup"><span data-stu-id="52dd9-105">**Error ID:** BC30561</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="52dd9-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="52dd9-106">To correct this error</span></span>

- <span data-ttu-id="52dd9-107">Usuń niejednoznaczność nazwy, usuwając Importy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="52dd9-107">Disambiguate the name by removing namespace imports.</span></span>

- <span data-ttu-id="52dd9-108">W pełni Zakwalifikuj nazwę.</span><span class="sxs-lookup"><span data-stu-id="52dd9-108">Fully qualify the name.</span></span>

## <a name="see-also"></a><span data-ttu-id="52dd9-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="52dd9-109">See also</span></span>

- [<span data-ttu-id="52dd9-110">Imports — Instrukcja (.NET Namespace i Type)</span><span class="sxs-lookup"><span data-stu-id="52dd9-110">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="52dd9-111">Przestrzenie nazw w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="52dd9-111">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="52dd9-112">Namespace — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="52dd9-112">Namespace Statement</span></span>](../statements/namespace-statement.md)
