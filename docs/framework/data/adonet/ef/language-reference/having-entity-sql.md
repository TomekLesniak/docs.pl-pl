---
title: POSIADANIE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: a117f377b3f03b6a1a12e39426a24f3141aa40ff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204466"
---
# <a name="having-entity-sql"></a><span data-ttu-id="f6762-102">POSIADANIE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f6762-102">HAVING (Entity SQL)</span></span>

<span data-ttu-id="f6762-103">Określa warunek wyszukiwania dla grupy lub agregacji.</span><span class="sxs-lookup"><span data-stu-id="f6762-103">Specifies a search condition for a group or an aggregate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6762-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f6762-104">Syntax</span></span>  
  
```sql  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f6762-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="f6762-105">Arguments</span></span>  

 `search_condition`  
 <span data-ttu-id="f6762-106">Określa warunek wyszukiwania dla grupy lub agregacji, które mają zostać spełnione.</span><span class="sxs-lookup"><span data-stu-id="f6762-106">Specifies the search condition for the group or the aggregate to meet.</span></span> <span data-ttu-id="f6762-107">Gdy jest używany z klauzulą GROUP BY ALL, klauzula HAVING zastępuje wszystkie.</span><span class="sxs-lookup"><span data-stu-id="f6762-107">When HAVING is used with GROUP BY ALL, the HAVING clause overrides ALL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6762-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f6762-108">Remarks</span></span>  

 <span data-ttu-id="f6762-109">Klauzula HAVING służy do określania dodatkowego warunku filtrowania w wyniku grupowania.</span><span class="sxs-lookup"><span data-stu-id="f6762-109">The HAVING clause is used to specify an additional filtering condition on the result of a grouping.</span></span> <span data-ttu-id="f6762-110">Jeśli w wyrażeniu zapytania nie określono klauzuli GROUP BY, założono niejawną grupę z pojedynczym zestawem.</span><span class="sxs-lookup"><span data-stu-id="f6762-110">If no GROUP BY clause is specified in the query expression, an implicit single-set group is assumed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6762-111">HAVING można używać tylko z instrukcją [SELECT](select-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="f6762-111">HAVING can be used only with the [SELECT](select-entity-sql.md) statement.</span></span> <span data-ttu-id="f6762-112">Gdy klauzula [Group by](group-by-entity-sql.md) nie jest używana, zachowanie jest podobne do klauzuli WHERE.</span><span class="sxs-lookup"><span data-stu-id="f6762-112">When [GROUP BY](group-by-entity-sql.md) is not used, HAVING behaves like a WHERE clause.</span></span>  
  
<span data-ttu-id="f6762-113">Klauzula HAVING działa podobnie jak klauzula WHERE, z tą różnicą, że jest stosowana po operacji Grupuj według.</span><span class="sxs-lookup"><span data-stu-id="f6762-113">The HAVING clause works like the WHERE clause except that it is applied after the GROUP BY operation.</span></span> <span data-ttu-id="f6762-114">Oznacza to, że klauzula HAVING może tylko tworzyć odwołania do aliasów grupowania i agregacji, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="f6762-114">This means that the HAVING clause can only make references to grouping aliases and aggregates, as illustrated in the following example:</span></span>
  
```sql  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 <span data-ttu-id="f6762-115">Poprzednie ogranicza grupy tylko do tych, które zawierają więcej niż jeden produkt.</span><span class="sxs-lookup"><span data-stu-id="f6762-115">The previous restricts the groups to only those that include more than one product.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6762-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="f6762-116">Example</span></span>  

 <span data-ttu-id="f6762-117">Poniższe zapytanie Entity SQL używa operatorów HAVING i GROUP BY, aby określić warunek wyszukiwania dla grupy lub agregacji.</span><span class="sxs-lookup"><span data-stu-id="f6762-117">The following Entity SQL query uses the HAVING and GROUP BY operators to specify a search condition for a group or an aggregate.</span></span> <span data-ttu-id="f6762-118">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f6762-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f6762-119">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="f6762-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f6762-120">Postępuj zgodnie z procedurą w [instrukcje: wykonywanie zapytania, które zwraca wyniki typu pierwotnego](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f6762-120">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="f6762-121">Przekaż następujące zapytanie jako argument do `ExecutePrimitiveTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="f6762-121">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#HAVING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#having)]  
  
## <a name="see-also"></a><span data-ttu-id="f6762-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f6762-122">See also</span></span>

- [<span data-ttu-id="f6762-123">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="f6762-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="f6762-124">Wyrażenia kwerend</span><span class="sxs-lookup"><span data-stu-id="f6762-124">Query Expressions</span></span>](query-expressions-entity-sql.md)
