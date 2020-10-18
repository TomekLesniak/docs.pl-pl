---
title: Instrukcje „#Region” i „#End Region” nie są prawidłowe w treści metod/wielowierszowych wyrażeń lambda
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: c792fa1a42bde22959ae21439cb2a0a1e4be343f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162287"
---
# <a name="bc32025-region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="7d60b-102">BC32025: instrukcje "#Region" i "#End Region" nie są prawidłowe w treści metod/wielowierszowych wyrażeń lambda</span><span class="sxs-lookup"><span data-stu-id="7d60b-102">BC32025: '#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>

<span data-ttu-id="7d60b-103">`#Region`Blok musi być zadeklarowany na poziomie klasy, modułu lub przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="7d60b-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="7d60b-104">Region zwijany może zawierać jedną lub więcej procedur, ale nie może zaczynać się ani kończyć wewnątrz procedury.</span><span class="sxs-lookup"><span data-stu-id="7d60b-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>

 <span data-ttu-id="7d60b-105">**Identyfikator błędu:** BC32025</span><span class="sxs-lookup"><span data-stu-id="7d60b-105">**Error ID:** BC32025</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7d60b-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="7d60b-106">To correct this error</span></span>

1. <span data-ttu-id="7d60b-107">Upewnij się, że poprzednia procedura została prawidłowo `End Function` zakończona `End Sub` instrukcją or.</span><span class="sxs-lookup"><span data-stu-id="7d60b-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>

2. <span data-ttu-id="7d60b-108">Upewnij się, `#Region` że `#End Region` dyrektywy i znajdują się w tym samym bloku kodu.</span><span class="sxs-lookup"><span data-stu-id="7d60b-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d60b-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7d60b-109">See also</span></span>

- [<span data-ttu-id="7d60b-110">#Region — dyrektywa</span><span class="sxs-lookup"><span data-stu-id="7d60b-110">#Region Directive</span></span>](../directives/region-directive.md)
