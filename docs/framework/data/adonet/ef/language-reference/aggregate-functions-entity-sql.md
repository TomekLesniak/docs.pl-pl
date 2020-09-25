---
title: Funkcje agregujące (Entity SQL)
ms.date: 03/30/2017
ms.assetid: acfd3149-f519-4c6e-8fe1-b21d243a0e58
ms.openlocfilehash: 308670f04b9a04b1fff77ece08deb39c8c4081d1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198083"
---
# <a name="aggregate-functions-entity-sql"></a><span data-ttu-id="f2df5-102">Funkcje agregujące (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f2df5-102">Aggregate Functions (Entity SQL)</span></span>

<span data-ttu-id="f2df5-103">Agregacja jest konstrukcja języka, która przekształca kolekcję do skalarnej jako część operacji grupy.</span><span class="sxs-lookup"><span data-stu-id="f2df5-103">An aggregate is a language construct that condenses a collection into a scalar as a part of a group operation.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="f2df5-104">agregacje są dostępne w dwóch formach:</span><span class="sxs-lookup"><span data-stu-id="f2df5-104">aggregates come in two forms:</span></span>  
  
- [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="f2df5-105">funkcje kolekcji, które mogą być używane w dowolnym miejscu w wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="f2df5-105">collection functions that may be used anywhere in an expression.</span></span> <span data-ttu-id="f2df5-106">Obejmuje to używanie funkcji agregujących w projekcjach i predykatach, które działają na kolekcjach.</span><span class="sxs-lookup"><span data-stu-id="f2df5-106">This includes using aggregate functions in projections and predicates that act on collections.</span></span> <span data-ttu-id="f2df5-107">Funkcje kolekcji są preferowanym trybem określania wartości zagregowanych w elemencie [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2df5-107">Collection functions are the preferred mode of specifying aggregates in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
- <span data-ttu-id="f2df5-108">Grupowanie agregacji w wyrażeniach zapytania, które mają klauzulę GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="f2df5-108">Group aggregates in query expressions that have a GROUP BY clause.</span></span> <span data-ttu-id="f2df5-109">Podobnie jak w języku Transact-SQL, agregacje grup akceptują różne i wszystkie jako modyfikatory do zagregowanych danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="f2df5-109">As in Transact-SQL, group aggregates accept DISTINCT and ALL as modifiers to the aggregate input.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="f2df5-110">najpierw próbuje zinterpretować wyrażenie jako funkcję kolekcji, a jeśli wyrażenie znajduje się w kontekście wyrażenia SELECT, interpretuje je jako agregację grupy.</span><span class="sxs-lookup"><span data-stu-id="f2df5-110">first tries to interpret an expression as a collection function and if the expression is in the context of a SELECT expression it interprets it as a group aggregate.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="f2df5-111">definiuje specjalny operator agregujący o nazwie [GROUPPARTITION](grouppartition-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f2df5-111">defines a special aggregate operator called [GROUPPARTITION](grouppartition-entity-sql.md).</span></span> <span data-ttu-id="f2df5-112">Ten operator umożliwia uzyskanie odwołania do pogrupowanego zestawu danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="f2df5-112">This operator enables you to get a reference to the grouped input set.</span></span> <span data-ttu-id="f2df5-113">Pozwala to na bardziej zaawansowane zapytania grupujące, gdzie wyniki klauzuli GROUP BY mogą być używane w miejscach innych niż agregacja lub funkcje kolekcji grupy.</span><span class="sxs-lookup"><span data-stu-id="f2df5-113">This allows more advanced grouping queries, where the results of the GROUP BY clause can be used in places other than group aggregate or collection functions.</span></span>  
  
## <a name="collection-functions"></a><span data-ttu-id="f2df5-114">Funkcje kolekcji</span><span class="sxs-lookup"><span data-stu-id="f2df5-114">Collection Functions</span></span>  

 <span data-ttu-id="f2df5-115">Funkcje kolekcji działają na kolekcjach i zwracają wartość skalarną.</span><span class="sxs-lookup"><span data-stu-id="f2df5-115">Collection functions operate on collections and return a scalar value.</span></span> <span data-ttu-id="f2df5-116">Na przykład jeśli `orders` jest kolekcją wszystkich `orders` , można obliczyć najwcześniejszą datę wysyłki przy użyciu następującego wyrażenia:</span><span class="sxs-lookup"><span data-stu-id="f2df5-116">For example, if `orders` is a collection of all `orders`, you can calculate the earliest ship date with the following expression:</span></span>  
  
 `min(select value o.ShipDate from LOB.Orders as o)`  
  
## <a name="group-aggregates"></a><span data-ttu-id="f2df5-117">Agregacje grup</span><span class="sxs-lookup"><span data-stu-id="f2df5-117">Group Aggregates</span></span>  

 <span data-ttu-id="f2df5-118">Agregacje grup są obliczane na podstawie wyniku grupy zgodnie z definicją w klauzuli GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="f2df5-118">Group aggregates are calculated over a group result as defined by the GROUP BY clause.</span></span> <span data-ttu-id="f2df5-119">Klauzula GROUP BY dzieli dane na grupy.</span><span class="sxs-lookup"><span data-stu-id="f2df5-119">The GROUP BY clause partitions data  into groups.</span></span> <span data-ttu-id="f2df5-120">Dla każdej grupy w wyniku stosowana jest funkcja agregująca i oddzielna wartość zagregowana jest obliczana przy użyciu elementów w każdej grupie jako dane wejściowe obliczenia agregacji.</span><span class="sxs-lookup"><span data-stu-id="f2df5-120">For each group in the result, the aggregate function is applied and a separate aggregate is calculated by using the elements in each group as inputs to the aggregate calculation.</span></span> <span data-ttu-id="f2df5-121">Gdy klauzula GROUP BY jest używana w wyrażeniu SELECT, w klauzuli projekcji, HAVING lub ORDER BY może występować tylko nazwa wyrażenia grupującego, agregacje lub wyrażenia stałe.</span><span class="sxs-lookup"><span data-stu-id="f2df5-121">When a GROUP BY clause is used in a SELECT expression, only grouping expression names, aggregates, or constant expressions may be present in the projection, HAVING, or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="f2df5-122">Poniższy przykład oblicza średnią ilość zamówioną dla każdego produktu.</span><span class="sxs-lookup"><span data-stu-id="f2df5-122">The following example calculates the average quantity ordered for each product.</span></span>  
  
 `select p, avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `group by ol.Product as p`  
  
 <span data-ttu-id="f2df5-123">Możliwe jest posiadanie agregacji grupowej bez jawnej klauzuli GROUP BY w wyrażeniu SELECT.</span><span class="sxs-lookup"><span data-stu-id="f2df5-123">It is possible to have a group aggregate without an explicit GROUP BY clause in the SELECT expression.</span></span> <span data-ttu-id="f2df5-124">Wszystkie elementy będą traktowane jako pojedyncze grupy, równoważne przypadku określania grupowania na podstawie stałej.</span><span class="sxs-lookup"><span data-stu-id="f2df5-124">All elements will be treated as a single group, equivalent to the case of specifying a grouping based on a constant.</span></span>  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol group by 1`  
  
 <span data-ttu-id="f2df5-125">Wyrażenia używane w klauzuli GROUP BY są oceniane przy użyciu tego samego zakresu rozpoznawania nazw, który byłby widoczny dla wyrażenia klauzuli WHERE.</span><span class="sxs-lookup"><span data-stu-id="f2df5-125">Expressions used in the GROUP BY clause are evaluated by using the same name-resolution scope that would be visible to the WHERE clause expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2df5-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f2df5-126">See also</span></span>

- [<span data-ttu-id="f2df5-127">Funkcje</span><span class="sxs-lookup"><span data-stu-id="f2df5-127">Functions</span></span>](functions-entity-sql.md)
