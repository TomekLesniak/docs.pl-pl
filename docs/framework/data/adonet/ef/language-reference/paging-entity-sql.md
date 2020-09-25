---
title: Stronicowanie (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
ms.openlocfilehash: 42f685e0b84109f3099b501b2a75e681af1ea1bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177478"
---
# <a name="paging-entity-sql"></a><span data-ttu-id="ed131-102">Stronicowanie (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ed131-102">Paging (Entity SQL)</span></span>

<span data-ttu-id="ed131-103">Stronicowanie fizyczne można wykonać za pomocą podklauzul [Skip](skip-entity-sql.md) i [Limit](limit-entity-sql.md) w klauzuli [order by](order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="ed131-103">Physical paging can be performed by using the [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses in the [ORDER BY](order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="ed131-104">Aby dokonać niejednoznacznego stronicowania, należy użyć SKIP i LIMIT.</span><span class="sxs-lookup"><span data-stu-id="ed131-104">To perform physical paging deterministically, you should use SKIP and LIMIT.</span></span> <span data-ttu-id="ed131-105">Jeśli chcesz tylko ograniczyć liczbę wierszy w wyniku w sposób niedeterministyczny, należy użyć [klauzuli TOP](top-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ed131-105">If you only want to restrict the number of rows in the result in a non-deterministic way, you should use [TOP](top-entity-sql.md).</span></span> <span data-ttu-id="ed131-106">Wartość TOP i SKIP/LIMIT wykluczają się wzajemnie.</span><span class="sxs-lookup"><span data-stu-id="ed131-106">TOP and SKIP/LIMIT are mutually exclusive.</span></span>  
  
## <a name="top-overview"></a><span data-ttu-id="ed131-107">Najważniejsze Omówienie</span><span class="sxs-lookup"><span data-stu-id="ed131-107">TOP Overview</span></span>  

 <span data-ttu-id="ed131-108">Klauzula SELECT może mieć opcjonalną podklauzulę TOP, która znajduje się po opcjonalnym modyfikatorze ALL/DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="ed131-108">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="ed131-109">Podklauzula TOP określa, że tylko pierwszy zestaw wierszy zostanie zwrócony z wyniku zapytania.</span><span class="sxs-lookup"><span data-stu-id="ed131-109">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span> <span data-ttu-id="ed131-110">Aby uzyskać więcej informacji, zobacz [Top](top-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ed131-110">For more information, see [TOP](top-entity-sql.md).</span></span>  
  
## <a name="skip-and-limit-overview"></a><span data-ttu-id="ed131-111">Przegląd POMIJAnia i OGRANICZAnia</span><span class="sxs-lookup"><span data-stu-id="ed131-111">SKIP And LIMIT Overview</span></span>  

 <span data-ttu-id="ed131-112">SKIP i LIMIT są częścią klauzuli ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="ed131-112">SKIP and LIMIT are part of the ORDER BY clause.</span></span> <span data-ttu-id="ed131-113">Jeśli Podklauzula POMIJAnia wyrażenia jest obecna w klauzuli ORDER BY, wyniki zostaną posortowane zgodnie z specyfikacją sortowania, a zestaw wyników będzie zawierać wiersze zaczynające się od następnego wiersza bezpośrednio po wyrażeniu SKIP.</span><span class="sxs-lookup"><span data-stu-id="ed131-113">If a SKIP expression sub-clause is present in a ORDER BY clause, the results will be sorted according to the sort specification and the result set will include row(s) starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="ed131-114">Na przykład Pomiń 5 spowoduje pominięcie pierwszych pięciu wierszy i zwrócenie od szóstego wiersza do przodu.</span><span class="sxs-lookup"><span data-stu-id="ed131-114">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span> <span data-ttu-id="ed131-115">Jeśli Podklauzula wyrażenia limitu jest obecna w klauzuli ORDER BY, zapytanie zostanie posortowane zgodnie z specyfikacją sortowania, a wynikowa liczba wierszy zostanie ograniczona przez wyrażenie limitu.</span><span class="sxs-lookup"><span data-stu-id="ed131-115">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="ed131-116">Na przykład LIMIT 5 ograniczy wynik do pięciu wystąpień lub wierszy.</span><span class="sxs-lookup"><span data-stu-id="ed131-116">For instance, LIMIT 5 will restrict the result set to five instances or rows.</span></span> <span data-ttu-id="ed131-117">Nie trzeba używać jednocześnie pominięcia i limitu; Możesz użyć tylko pominięcia lub wystarczy ograniczyć z klauzulą ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="ed131-117">SKIP and LIMIT do not have to be used together; you can use just SKIP or just LIMIT with ORDER BY clause.</span></span> <span data-ttu-id="ed131-118">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="ed131-118">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="ed131-119">Skocz</span><span class="sxs-lookup"><span data-stu-id="ed131-119">SKIP</span></span>](skip-entity-sql.md)  
  
- [<span data-ttu-id="ed131-120">GRANICE</span><span class="sxs-lookup"><span data-stu-id="ed131-120">LIMIT</span></span>](limit-entity-sql.md)  
  
- [<span data-ttu-id="ed131-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="ed131-121">ORDER BY</span></span>](order-by-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="ed131-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ed131-122">See also</span></span>

- [<span data-ttu-id="ed131-123">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="ed131-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="ed131-124">Omówienie jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="ed131-124">Entity SQL Overview</span></span>](entity-sql-overview.md)
- <span data-ttu-id="ed131-125">[Instrukcje: Strona za poorednictwem wyników zapytania](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ed131-125">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
