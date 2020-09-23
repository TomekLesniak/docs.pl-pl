---
title: Dzielenie przez zero (błąd czasu wykonywania Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID11
ms.assetid: 5b9bc5d6-792e-48bc-a974-012e07ad95f3
ms.openlocfilehash: 2dc36123478c0946b3ba5931dcc283acc08920cc
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084362"
---
# <a name="division-by-zero-visual-basic-run-time-error"></a><span data-ttu-id="e79f0-102">Dzielenie przez zero (błąd czasu wykonywania Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e79f0-102">Division by zero (Visual Basic Run-Time Error)</span></span>

<span data-ttu-id="e79f0-103">Wyrażenie używane jako dzielnik ma wartość zero.</span><span class="sxs-lookup"><span data-stu-id="e79f0-103">An expression being used as a divisor has a value of zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e79f0-104">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="e79f0-104">To correct this error</span></span>  
  
1. <span data-ttu-id="e79f0-105">Sprawdź pisownię zmiennych w wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="e79f0-105">Check the spelling of variables in the expression.</span></span> <span data-ttu-id="e79f0-106">Błędnie wpisana nazwa zmiennej może niejawnie utworzyć zmienną numeryczną, która została zainicjowana do zera.</span><span class="sxs-lookup"><span data-stu-id="e79f0-106">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
2. <span data-ttu-id="e79f0-107">Sprawdź poprzednie operacje na zmiennych w wyrażeniu, szczególnie te przekazane do procedury jako argumenty z innych procedur.</span><span class="sxs-lookup"><span data-stu-id="e79f0-107">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e79f0-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e79f0-108">See also</span></span>

- [<span data-ttu-id="e79f0-109">Przekazywanie argumentów według wartości i według odwołania</span><span class="sxs-lookup"><span data-stu-id="e79f0-109">Passing Arguments by Value and by Reference</span></span>](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
