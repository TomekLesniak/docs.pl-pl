---
title: Let, klauzula
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: a6ff3fc80a2b6752c61a8b8f7d4ce62b5a46baad
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869882"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="3c4cd-102">Let — Klauzula (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c4cd-102">Let Clause (Visual Basic)</span></span>

<span data-ttu-id="3c4cd-103">Oblicza wartość i przypisuje ją do nowej zmiennej w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="3c4cd-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c4cd-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3c4cd-104">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="3c4cd-105">Części</span><span class="sxs-lookup"><span data-stu-id="3c4cd-105">Parts</span></span>  
  
|<span data-ttu-id="3c4cd-106">Termin</span><span class="sxs-lookup"><span data-stu-id="3c4cd-106">Term</span></span>|<span data-ttu-id="3c4cd-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="3c4cd-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="3c4cd-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="3c4cd-108">Required.</span></span> <span data-ttu-id="3c4cd-109">Alias, który może służyć do odwoływania się do wyników podanego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="3c4cd-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="3c4cd-110">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="3c4cd-110">Required.</span></span> <span data-ttu-id="3c4cd-111">Wyrażenie, które zostanie obliczone i przypisane do określonej zmiennej.</span><span class="sxs-lookup"><span data-stu-id="3c4cd-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c4cd-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3c4cd-112">Remarks</span></span>  

 <span data-ttu-id="3c4cd-113">`Let`Klauzula umożliwia obliczanie wartości dla każdego wyniku zapytania i odwoływanie się do nich za pomocą aliasu.</span><span class="sxs-lookup"><span data-stu-id="3c4cd-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="3c4cd-114">Alias może być używany w innych klauzulach, takich jak `Where` klauzula.</span><span class="sxs-lookup"><span data-stu-id="3c4cd-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="3c4cd-115">`Let`Klauzula umożliwia utworzenie instrukcji zapytania, która jest łatwiejsza do odczytania, ponieważ można określić alias dla klauzuli Expression zawartej w zapytaniu i zastąpić alias za każdym razem, gdy używana jest klauzula wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="3c4cd-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="3c4cd-116">W klauzuli można uwzględnić dowolną liczbę `variable` i `expression` przypisania `Let` .</span><span class="sxs-lookup"><span data-stu-id="3c4cd-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="3c4cd-117">Każde przypisanie należy oddzielić przecinkami (,).</span><span class="sxs-lookup"><span data-stu-id="3c4cd-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c4cd-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="3c4cd-118">Example</span></span>  

 <span data-ttu-id="3c4cd-119">Poniższy przykład kodu używa klauzuli, `Let` Aby obliczyć rabat 10% dla produktów.</span><span class="sxs-lookup"><span data-stu-id="3c4cd-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="3c4cd-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3c4cd-120">See also</span></span>

- [<span data-ttu-id="3c4cd-121">Wprowadzenie do LINQ w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c4cd-121">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="3c4cd-122">Zapytania</span><span class="sxs-lookup"><span data-stu-id="3c4cd-122">Queries</span></span>](index.md)
- [<span data-ttu-id="3c4cd-123">SELECT — klauzula</span><span class="sxs-lookup"><span data-stu-id="3c4cd-123">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="3c4cd-124">Klauzula from</span><span class="sxs-lookup"><span data-stu-id="3c4cd-124">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="3c4cd-125">Klauzula WHERE</span><span class="sxs-lookup"><span data-stu-id="3c4cd-125">Where Clause</span></span>](where-clause.md)
