---
description: Zaznaczone i niesprawdzone — odwołanie w C#
title: Zaznaczone i niesprawdzone — odwołanie w C#
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: a8d6a26e28062da682689bf64a9e38ea5fd158b2
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138270"
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="af0ae-103">checked i unchecked (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="af0ae-103">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="af0ae-104">Instrukcje języka C# można wykonać w kontekście zaznaczonym lub niezaznaczonym.</span><span class="sxs-lookup"><span data-stu-id="af0ae-104">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="af0ae-105">W kontekście, przepełnienie arytmetyczne wywołuje wyjątek.</span><span class="sxs-lookup"><span data-stu-id="af0ae-105">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="af0ae-106">W kontekście niesprawdzonym przepełnienie arytmetyczne jest ignorowane, a wynik zostanie obcięty przez odrzucenie wszystkich bitów o dużej kolejności, które nie mieszczą się w typie docelowym.</span><span class="sxs-lookup"><span data-stu-id="af0ae-106">In an unchecked context, arithmetic overflow is ignored and the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>  
  
- <span data-ttu-id="af0ae-107">[zaznaczone](checked.md) Określ sprawdzony kontekst.</span><span class="sxs-lookup"><span data-stu-id="af0ae-107">[checked](checked.md) Specify checked context.</span></span>  
  
- <span data-ttu-id="af0ae-108">[niezaznaczone](unchecked.md) Określ kontekst niesprawdzony.</span><span class="sxs-lookup"><span data-stu-id="af0ae-108">[unchecked](unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="af0ae-109">Sprawdzanie przepełnienia ma wpływ na następujące operacje:</span><span class="sxs-lookup"><span data-stu-id="af0ae-109">The following operations are affected by the overflow checking:</span></span>  
  
- <span data-ttu-id="af0ae-110">Wyrażenia wykorzystujące następujące wstępnie zdefiniowane operatory w typach całkowitych:</span><span class="sxs-lookup"><span data-stu-id="af0ae-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="af0ae-111">`++`,,,,,, `--` `-` `+` `-` `*` , `/`</span><span class="sxs-lookup"><span data-stu-id="af0ae-111">`++`, `--`, unary `-`, `+`, `-`, `*`, `/`</span></span>  
  
- <span data-ttu-id="af0ae-112">Jawne konwersje liczbowe między typami całkowitymi lub z `float` lub `double` do typu całkowitego.</span><span class="sxs-lookup"><span data-stu-id="af0ae-112">Explicit numeric conversions between integral types, or from `float` or `double` to an integral type.</span></span>  
  
 <span data-ttu-id="af0ae-113">Jeśli ani `checked` nie `unchecked` zostanie określony, domyślny kontekst dla wyrażeń niestałych (wyrażenia, które są oceniane w czasie wykonywania) jest zdefiniowany przez wartość opcji kompilatora [-Checked](../compiler-options/checked-compiler-option.md) .</span><span class="sxs-lookup"><span data-stu-id="af0ae-113">If neither `checked` nor `unchecked` is specified, the default context for non-constant expressions (expressions that are evaluated at run time) is defined by the value of the [-checked](../compiler-options/checked-compiler-option.md) compiler option.</span></span> <span data-ttu-id="af0ae-114">Domyślnie wartość tej opcji to unoptional, a operacje arytmetyczne są wykonywane w niesprawdzonym kontekście.</span><span class="sxs-lookup"><span data-stu-id="af0ae-114">By default the value of that option is unset and arithmetic operations are executed in an unchecked context.</span></span>

 <span data-ttu-id="af0ae-115">W przypadku wyrażeń stałych (wyrażenia, które mogą być w pełni oceniane w czasie kompilacji), domyślnym kontekstem jest zawsze zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="af0ae-115">For constant expressions (expressions that can be fully evaluated at compile time), the default context is always checked.</span></span> <span data-ttu-id="af0ae-116">Jeśli wyrażenie stałe nie jest jawnie umieszczane w niesprawdzonym kontekście, przepełnienie następuje podczas obliczania czasu kompilacji wyrażenia powodującego błędy czasu kompilacji.</span><span class="sxs-lookup"><span data-stu-id="af0ae-116">Unless a constant expression is explicitly placed in an unchecked context, overflows that occur during the compile-time evaluation of the expression cause compile-time errors.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="af0ae-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="af0ae-117">See also</span></span>

- [<span data-ttu-id="af0ae-118">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="af0ae-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="af0ae-119">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="af0ae-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="af0ae-120">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="af0ae-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="af0ae-121">Słowa kluczowe instrukcji</span><span class="sxs-lookup"><span data-stu-id="af0ae-121">Statement Keywords</span></span>](statement-keywords.md)
