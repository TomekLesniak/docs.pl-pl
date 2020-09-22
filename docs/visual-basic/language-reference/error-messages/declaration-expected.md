---
title: Oczekiwano deklaracji
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: ee8f1f9ec26dc6c938f0b412dfe30832e3cfe165
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874522"
---
# <a name="declaration-expected"></a><span data-ttu-id="11a60-102">Oczekiwano deklaracji</span><span class="sxs-lookup"><span data-stu-id="11a60-102">Declaration expected</span></span>

<span data-ttu-id="11a60-103">Niedeklaratywna instrukcja, taka jak Instrukcja przypisania lub pętla, występuje poza żadną procedurą.</span><span class="sxs-lookup"><span data-stu-id="11a60-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="11a60-104">Tylko deklaracje są dozwolone poza procedurami.</span><span class="sxs-lookup"><span data-stu-id="11a60-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="11a60-105">Alternatywnie, element programowania jest zadeklarowany bez słowa kluczowego deklaracji, takiego jak `Dim` lub `Const` .</span><span class="sxs-lookup"><span data-stu-id="11a60-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="11a60-106">**Identyfikator błędu:** BC30188</span><span class="sxs-lookup"><span data-stu-id="11a60-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="11a60-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="11a60-107">To correct this error</span></span>  
  
- <span data-ttu-id="11a60-108">Przenieś niedeklaracyjne instrukcje do treści procedury.</span><span class="sxs-lookup"><span data-stu-id="11a60-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
- <span data-ttu-id="11a60-109">Rozpocznij deklarację z odpowiednimi słowami kluczowymi deklaracji.</span><span class="sxs-lookup"><span data-stu-id="11a60-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
- <span data-ttu-id="11a60-110">Upewnij się, że słowo kluczowe deklaracji nie jest błędnie napisane.</span><span class="sxs-lookup"><span data-stu-id="11a60-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a60-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="11a60-111">See also</span></span>

- [<span data-ttu-id="11a60-112">Procedury</span><span class="sxs-lookup"><span data-stu-id="11a60-112">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="11a60-113">Dim, instrukcja</span><span class="sxs-lookup"><span data-stu-id="11a60-113">Dim Statement</span></span>](../statements/dim-statement.md)
