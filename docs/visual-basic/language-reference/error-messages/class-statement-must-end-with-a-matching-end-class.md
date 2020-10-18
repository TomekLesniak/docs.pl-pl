---
title: Instrukcja „Class” musi być zakończona odpowiadającą jej instrukcją „End Class”
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 6889e97aad913f6911ce438892752542de0d10f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163197"
---
# <a name="bc30481-class-statement-must-end-with-a-matching-end-class"></a><span data-ttu-id="b62c1-102">BC30481: Instrukcja "Class" musi być zakończona odpowiadającą jej instrukcją "End Class"</span><span class="sxs-lookup"><span data-stu-id="b62c1-102">BC30481: 'Class' statement must end with a matching 'End Class'</span></span>

<span data-ttu-id="b62c1-103">`Class` służy do inicjowania `Class` bloku; w związku z tym może wystąpić tylko na początku bloku, z odpowiadającą instrukcją `End Class` kończącą blok.</span><span class="sxs-lookup"><span data-stu-id="b62c1-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="b62c1-104">Istnieje instrukcja nadmiarowa `Class` lub nie zakończono `Class` blokady przy użyciu `End Class` .</span><span class="sxs-lookup"><span data-stu-id="b62c1-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>

 <span data-ttu-id="b62c1-105">**Identyfikator błędu:** BC30481</span><span class="sxs-lookup"><span data-stu-id="b62c1-105">**Error ID:** BC30481</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b62c1-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="b62c1-106">To correct this error</span></span>

- <span data-ttu-id="b62c1-107">Znajdź i Usuń niezbędną `Class` instrukcję.</span><span class="sxs-lookup"><span data-stu-id="b62c1-107">Locate and remove the unnecessary `Class` statement.</span></span>

- <span data-ttu-id="b62c1-108">Zakończ `Class` blok ze zgodnym elementem `End Class` .</span><span class="sxs-lookup"><span data-stu-id="b62c1-108">Conclude the `Class` block with a matching `End Class`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b62c1-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b62c1-109">See also</span></span>

- [<span data-ttu-id="b62c1-110">End — \<keyword> instrukcja</span><span class="sxs-lookup"><span data-stu-id="b62c1-110">End \<keyword> Statement</span></span>](../statements/end-keyword-statement.md)
- [<span data-ttu-id="b62c1-111">Class, instrukcja</span><span class="sxs-lookup"><span data-stu-id="b62c1-111">Class Statement</span></span>](../statements/class-statement.md)
