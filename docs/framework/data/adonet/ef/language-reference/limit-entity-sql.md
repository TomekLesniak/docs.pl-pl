---
title: LIMIT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: 81d135785e567d46a105adcafbf083f48cb4868e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161766"
---
# <a name="limit-entity-sql"></a><span data-ttu-id="1bdd9-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1bdd9-102">LIMIT (Entity SQL)</span></span>

<span data-ttu-id="1bdd9-103">Stronicowanie fizyczne można wykonać za pomocą klauzuli LIMIT w klauzuli ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="1bdd9-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="1bdd9-104">Nie można użyć limitu niezależnie od klauzuli ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="1bdd9-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bdd9-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="1bdd9-105">Syntax</span></span>  
  
```sql  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1bdd9-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="1bdd9-106">Arguments</span></span>  

 `n`  
 <span data-ttu-id="1bdd9-107">Liczba elementów, które zostaną wybrane.</span><span class="sxs-lookup"><span data-stu-id="1bdd9-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="1bdd9-108">Jeśli Podklauzula wyrażenia limitu jest obecna w klauzuli ORDER BY, zapytanie zostanie posortowane zgodnie z specyfikacją sortowania, a wynikowa liczba wierszy zostanie ograniczona przez wyrażenie limitu.</span><span class="sxs-lookup"><span data-stu-id="1bdd9-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="1bdd9-109">Na przykład LIMIT 5 ograniczy wynik do 5 wystąpień lub wierszy.</span><span class="sxs-lookup"><span data-stu-id="1bdd9-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="1bdd9-110">LIMIT jest funkcjonalnie równoważny z GÓRNą opcją, ponieważ LIMIT wymaga obecności klauzuli ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="1bdd9-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="1bdd9-111">Nie można używać pominięcia i limitu niezależnie od klauzuli ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="1bdd9-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1bdd9-112">Zapytanie SQL jednostki zostanie uznane za nieprawidłowe, jeśli w tym samym wyrażeniu zapytania występuje modyfikator TOP i SKIP sub.</span><span class="sxs-lookup"><span data-stu-id="1bdd9-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="1bdd9-113">Zapytanie powinno być ponownie zapisywane przez zmianę wyrażenia TOP na wyrażenie OGRANICZAjące.</span><span class="sxs-lookup"><span data-stu-id="1bdd9-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bdd9-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="1bdd9-114">Example</span></span>  

 <span data-ttu-id="1bdd9-115">Poniższe zapytanie Entity SQL używa operatora ORDER BY z LIMITem, aby określić kolejność sortowania używaną dla obiektów zwracanych w instrukcji SELECT.</span><span class="sxs-lookup"><span data-stu-id="1bdd9-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="1bdd9-116">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="1bdd9-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1bdd9-117">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="1bdd9-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1bdd9-118">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1bdd9-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="1bdd9-119">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="1bdd9-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LIMIT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="1bdd9-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1bdd9-120">See also</span></span>

- [<span data-ttu-id="1bdd9-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="1bdd9-121">ORDER BY</span></span>](order-by-entity-sql.md)
- <span data-ttu-id="1bdd9-122">[Instrukcje: Strona za poorednictwem wyników zapytania](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1bdd9-122">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="1bdd9-123">Stronicowanie</span><span class="sxs-lookup"><span data-stu-id="1bdd9-123">Paging</span></span>](paging-entity-sql.md)
- [<span data-ttu-id="1bdd9-124">Do góry</span><span class="sxs-lookup"><span data-stu-id="1bdd9-124">TOP</span></span>](top-entity-sql.md)
