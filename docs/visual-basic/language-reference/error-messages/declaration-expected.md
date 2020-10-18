---
title: Oczekiwano deklaracji
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 2755f5afcb96ca7a6c4d140908649390dd66d571
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162703"
---
# <a name="bc30188-declaration-expected"></a><span data-ttu-id="4e50b-102">BC30188: oczekiwano deklaracji</span><span class="sxs-lookup"><span data-stu-id="4e50b-102">BC30188: Declaration expected</span></span>

<span data-ttu-id="4e50b-103">Niedeklaratywna instrukcja, taka jak Instrukcja przypisania lub pętla, występuje poza żadną procedurą.</span><span class="sxs-lookup"><span data-stu-id="4e50b-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="4e50b-104">Tylko deklaracje są dozwolone poza procedurami.</span><span class="sxs-lookup"><span data-stu-id="4e50b-104">Only declarations are allowed outside procedures.</span></span>

 <span data-ttu-id="4e50b-105">Alternatywnie, element programowania jest zadeklarowany bez słowa kluczowego deklaracji, takiego jak `Dim` lub `Const` .</span><span class="sxs-lookup"><span data-stu-id="4e50b-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>

 <span data-ttu-id="4e50b-106">**Identyfikator błędu:** BC30188</span><span class="sxs-lookup"><span data-stu-id="4e50b-106">**Error ID:** BC30188</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4e50b-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="4e50b-107">To correct this error</span></span>

- <span data-ttu-id="4e50b-108">Przenieś niedeklaracyjne instrukcje do treści procedury.</span><span class="sxs-lookup"><span data-stu-id="4e50b-108">Move the nondeclarative statement to the body of a procedure.</span></span>

- <span data-ttu-id="4e50b-109">Rozpocznij deklarację z odpowiednimi słowami kluczowymi deklaracji.</span><span class="sxs-lookup"><span data-stu-id="4e50b-109">Begin the declaration with an appropriate declaration keyword.</span></span>

- <span data-ttu-id="4e50b-110">Upewnij się, że słowo kluczowe deklaracji nie jest błędnie napisane.</span><span class="sxs-lookup"><span data-stu-id="4e50b-110">Ensure that a declaration keyword is not misspelled.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e50b-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4e50b-111">See also</span></span>

- [<span data-ttu-id="4e50b-112">Procedury</span><span class="sxs-lookup"><span data-stu-id="4e50b-112">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="4e50b-113">Dim, instrukcja</span><span class="sxs-lookup"><span data-stu-id="4e50b-113">Dim Statement</span></span>](../statements/dim-statement.md)
