---
title: Wiodący znak „.” lub „!” może wystąpić tylko wewnątrz instrukcji „With”
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 4ff273d5930fe58a5bccf0f4f4c10e971d777d01
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162508"
---
# <a name="bc30157-leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="ebcb2-102">BC30157: wiodący znak "." lub "!" może wystąpić tylko wewnątrz instrukcji "with"</span><span class="sxs-lookup"><span data-stu-id="ebcb2-102">BC30157: Leading '.' or '!' can only appear inside a 'With' statement</span></span>

<span data-ttu-id="ebcb2-103">Kropka (.) lub wykrzyknik (!), które nie znajduje się wewnątrz `With` bloku, nie ma wyrażenia po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="ebcb2-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="ebcb2-104">Dostęp do składowych ( `.` ) i dostęp do składowych słownika ( `!` ) wymagają wyrażenia określającego element, który zawiera element członkowski.</span><span class="sxs-lookup"><span data-stu-id="ebcb2-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="ebcb2-105">Musi on pojawić się natychmiast po lewej stronie metody dostępu lub jako obiekt docelowy `With` bloku zawierającego dostęp do elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="ebcb2-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>

 <span data-ttu-id="ebcb2-106">**Identyfikator błędu:** BC30157</span><span class="sxs-lookup"><span data-stu-id="ebcb2-106">**Error ID:** BC30157</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ebcb2-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="ebcb2-107">To correct this error</span></span>

1. <span data-ttu-id="ebcb2-108">Upewnij się, że `With` blok jest poprawnie sformatowany.</span><span class="sxs-lookup"><span data-stu-id="ebcb2-108">Ensure that the `With` block is correctly formatted.</span></span>

2. <span data-ttu-id="ebcb2-109">Jeśli nie ma `With` bloku, Dodaj wyrażenie z lewej strony metody dostępu, które jest obliczane do zdefiniowanego elementu zawierającego element członkowski.</span><span class="sxs-lookup"><span data-stu-id="ebcb2-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebcb2-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ebcb2-110">See also</span></span>

- [<span data-ttu-id="ebcb2-111">Znaki specjalne w kodzie</span><span class="sxs-lookup"><span data-stu-id="ebcb2-111">Special Characters in Code</span></span>](../../programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="ebcb2-112">With...End With, instrukcja</span><span class="sxs-lookup"><span data-stu-id="ebcb2-112">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
