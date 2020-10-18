---
title: Instrukcja nie jest prawidłowa wewnątrz metody/wielowierszowego wyrażenia lambda
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef992c3eaa2b82bbf5e8993f9fccd64ae388c95
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159680"
---
# <a name="bc30024-statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="87fb9-102">BC30024: instrukcja nie jest prawidłowa wewnątrz metody/wielowierszowego wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="87fb9-102">BC30024: Statement is not valid inside a method/multiline lambda</span></span>

<span data-ttu-id="87fb9-103">Instrukcja nie jest prawidłowa w ramach `Sub` procedury, `Function` , właściwości `Get` lub właściwości `Set` .</span><span class="sxs-lookup"><span data-stu-id="87fb9-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="87fb9-104">Niektóre instrukcje mogą być umieszczane na poziomie modułu lub klasy.</span><span class="sxs-lookup"><span data-stu-id="87fb9-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="87fb9-105">Inne, takie jak `Option Strict` , muszą znajdować się na poziomie przestrzeni nazw i poprzedzać wszystkie inne deklaracje.</span><span class="sxs-lookup"><span data-stu-id="87fb9-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>

 <span data-ttu-id="87fb9-106">**Identyfikator błędu:** BC30024</span><span class="sxs-lookup"><span data-stu-id="87fb9-106">**Error ID:** BC30024</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="87fb9-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="87fb9-107">To correct this error</span></span>

- <span data-ttu-id="87fb9-108">Usuń instrukcję z procedury.</span><span class="sxs-lookup"><span data-stu-id="87fb9-108">Remove the statement from the procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="87fb9-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="87fb9-109">See also</span></span>

- [<span data-ttu-id="87fb9-110">Sub, instrukcja</span><span class="sxs-lookup"><span data-stu-id="87fb9-110">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="87fb9-111">Function, instrukcja</span><span class="sxs-lookup"><span data-stu-id="87fb9-111">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="87fb9-112">Get — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="87fb9-112">Get Statement</span></span>](../statements/get-statement.md)
- [<span data-ttu-id="87fb9-113">Set — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="87fb9-113">Set Statement</span></span>](../statements/set-statement.md)
