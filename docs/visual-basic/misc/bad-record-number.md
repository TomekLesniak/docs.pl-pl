---
title: Zły numer rekordu
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: 8cbffc7714211fb10bedc3a73729eac59d98f0bb
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086988"
---
# <a name="bad-record-number"></a><span data-ttu-id="4d403-102">Zły numer rekordu</span><span class="sxs-lookup"><span data-stu-id="4d403-102">Bad record number</span></span>

<span data-ttu-id="4d403-103">Liczba rekordów w `a FileGet` , `FilePut` , `FileGetObject` , lub `FilePutObject` instrukcji jest mniejsza lub równa zero.</span><span class="sxs-lookup"><span data-stu-id="4d403-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4d403-104">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="4d403-104">To correct this error</span></span>  
  
1. <span data-ttu-id="4d403-105">Sprawdź obliczenia używane podczas generowania numeru rekordu.</span><span class="sxs-lookup"><span data-stu-id="4d403-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="4d403-106">Sprawdź pisownię zmiennych zawierających numer rekordu lub używany w obliczaniu numerów rekordów.</span><span class="sxs-lookup"><span data-stu-id="4d403-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="4d403-107">Błędnie wpisana nazwa zmiennej jest niejawnie zadeklarowana i została zainicjowana do zera, chyba że została użyta `Option Explicit On` w module.</span><span class="sxs-lookup"><span data-stu-id="4d403-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d403-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4d403-108">See also</span></span>

- [<span data-ttu-id="4d403-109">Option Explicit, instrukcja</span><span class="sxs-lookup"><span data-stu-id="4d403-109">Option Explicit Statement</span></span>](../language-reference/statements/option-explicit-statement.md)
