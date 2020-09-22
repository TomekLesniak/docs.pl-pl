---
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: baf9303101eea9eed27e8a4eee9e04d255c798e9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867823"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="0fb7b-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fb7b-102">ParamArray (Visual Basic)</span></span>

<span data-ttu-id="0fb7b-103">Określa, że parametr procedury przyjmuje opcjonalną tablicę elementów określonego typu.</span><span class="sxs-lookup"><span data-stu-id="0fb7b-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="0fb7b-104">`ParamArray` może być używany tylko dla ostatniego parametru listy parametrów.</span><span class="sxs-lookup"><span data-stu-id="0fb7b-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fb7b-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0fb7b-105">Remarks</span></span>  

 <span data-ttu-id="0fb7b-106">`ParamArray` umożliwia przekazanie dowolnej liczby argumentów do procedury.</span><span class="sxs-lookup"><span data-stu-id="0fb7b-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="0fb7b-107">`ParamArray`Parametr jest zawsze deklarowany przy użyciu [ByVal](byval.md).</span><span class="sxs-lookup"><span data-stu-id="0fb7b-107">A `ParamArray` parameter is always declared using [ByVal](byval.md).</span></span>  
  
 <span data-ttu-id="0fb7b-108">Można podać jeden lub więcej argumentów do parametru, `ParamArray` przekazując tablicę odpowiedniego typu danych, rozdzielaną przecinkami listę wartości lub nic wcale.</span><span class="sxs-lookup"><span data-stu-id="0fb7b-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="0fb7b-109">Aby uzyskać szczegółowe informacje, zobacz "wywoływanie ParamArray" w [tablicach parametrów](../../programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="0fb7b-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0fb7b-110">Za każdym razem, gdy zajmujesz się tablicą, która może być nienieskończona, istnieje ryzyko, że zachodzi taka Wewnętrzna pojemność aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0fb7b-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="0fb7b-111">Jeśli zaakceptujesz tablicę parametrów z kodu wywołującego, należy przetestować jego długość i wykonać odpowiednie czynności, jeśli jest ono zbyt duże dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0fb7b-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="0fb7b-112">`ParamArray`Modyfikator może być używany w tych kontekstach:</span><span class="sxs-lookup"><span data-stu-id="0fb7b-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="0fb7b-113">Declare — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="0fb7b-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="0fb7b-114">Function, instrukcja</span><span class="sxs-lookup"><span data-stu-id="0fb7b-114">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="0fb7b-115">Property — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="0fb7b-115">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="0fb7b-116">Sub, instrukcja</span><span class="sxs-lookup"><span data-stu-id="0fb7b-116">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0fb7b-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0fb7b-117">See also</span></span>

- [<span data-ttu-id="0fb7b-118">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="0fb7b-118">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="0fb7b-119">Parameter — Tablice</span><span class="sxs-lookup"><span data-stu-id="0fb7b-119">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
