---
title: Argument "lokr" musi być większy od zera
ms.date: 07/20/2015
f1_keywords:
- vbrRate_NPerMustBeGTZero
ms.assetid: d49242df-dbd1-4b26-bd8c-ed56d24fdfcd
ms.openlocfilehash: f0185e30cb711472105955f5febf8d7702b29c72
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087144"
---
# <a name="argument-nper-must-be-greater-than-zero"></a><span data-ttu-id="a92c2-102">Argument "lokr" musi być większy od zera</span><span class="sxs-lookup"><span data-stu-id="a92c2-102">Argument 'NPer' must be greater than zero</span></span>

<span data-ttu-id="a92c2-103">`NPer`Funkcja, która zwraca `Double` określenie liczby okresów dla raty rocznej na podstawie okresowych stałych płatności i stałej stopy oprocentowania, wymaga argumentu większego od zera.</span><span class="sxs-lookup"><span data-stu-id="a92c2-103">The `NPer` function, which returns a `Double` specifying the number of periods for an annuity based on periodic fixed payments and a fixed interest rate, requires an argument greater than zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a92c2-104">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="a92c2-104">To correct this error</span></span>  
  
- <span data-ttu-id="a92c2-105">Sprawdź pisownię argumentów w wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="a92c2-105">Check the spelling of arguments in the expression.</span></span> <span data-ttu-id="a92c2-106">Błędnie wpisana nazwa zmiennej może niejawnie utworzyć zmienną numeryczną, która została zainicjowana do zera.</span><span class="sxs-lookup"><span data-stu-id="a92c2-106">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
- <span data-ttu-id="a92c2-107">Sprawdź poprzednie operacje na zmiennych w wyrażeniu, szczególnie te przekazane do procedury jako argumenty z innych procedur.</span><span class="sxs-lookup"><span data-stu-id="a92c2-107">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a92c2-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a92c2-108">See also</span></span>

- [<span data-ttu-id="a92c2-109">Przekazywanie argumentów według wartości i według odwołania</span><span class="sxs-lookup"><span data-stu-id="a92c2-109">Passing Arguments by Value and by Reference</span></span>](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
