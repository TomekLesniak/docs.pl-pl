---
title: ORDER BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
ms.openlocfilehash: 5e1c418a7f2bd40a42b259fb3784794b13098d7f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173682"
---
# <a name="order-by-entity-sql"></a><span data-ttu-id="b6392-102">ORDER BY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b6392-102">ORDER BY (Entity SQL)</span></span>

<span data-ttu-id="b6392-103">Określa kolejność sortowania używaną dla obiektów zwracanych w instrukcji SELECT.</span><span class="sxs-lookup"><span data-stu-id="b6392-103">Specifies the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6392-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b6392-104">Syntax</span></span>  
  
```sql  
[ ORDER BY
   {  
      order_by_expression [SKIP n] [LIMIT n]  
      [ COLLATE collation_name ]  
      [ ASC | DESC ]  
   }  
   [ ,…n ]
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b6392-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="b6392-105">Arguments</span></span>  

 `order_by_expression`  
 <span data-ttu-id="b6392-106">Dowolne prawidłowe wyrażenie zapytania określające właściwość, według której ma zostać wykonane sortowanie.</span><span class="sxs-lookup"><span data-stu-id="b6392-106">Any valid query expression specifying a property on which to sort.</span></span> <span data-ttu-id="b6392-107">Można określić wiele wyrażeń sortowania.</span><span class="sxs-lookup"><span data-stu-id="b6392-107">Multiple sort expressions can be specified.</span></span> <span data-ttu-id="b6392-108">Sekwencja wyrażeń sortowania w klauzuli ORDER BY definiuje organizację zestawu wyników sortowania.</span><span class="sxs-lookup"><span data-stu-id="b6392-108">The sequence of the sort expressions in the ORDER BY clause defines the organization of the sorted result set.</span></span>  
  
 <span data-ttu-id="b6392-109">SORTOWANIE {collation_name}</span><span class="sxs-lookup"><span data-stu-id="b6392-109">COLLATE {collation_name}</span></span>  
 <span data-ttu-id="b6392-110">Określa, że operacja ORDER BY powinna być wykonywana zgodnie z sortowaniem określonym w elemencie `collation_name` .</span><span class="sxs-lookup"><span data-stu-id="b6392-110">Specifies that the ORDER BY operation should be performed according to the collation specified in `collation_name`.</span></span> <span data-ttu-id="b6392-111">SORTOWANIE jest stosowane tylko w przypadku wyrażeń ciągów.</span><span class="sxs-lookup"><span data-stu-id="b6392-111">COLLATE is applicable only for string expressions.</span></span>  
  
 <span data-ttu-id="b6392-112">ASC</span><span class="sxs-lookup"><span data-stu-id="b6392-112">ASC</span></span>  
 <span data-ttu-id="b6392-113">Określa, że wartości w określonej właściwości powinny być sortowane w kolejności rosnącej, od najmniejszej wartości do najwyższej wartości.</span><span class="sxs-lookup"><span data-stu-id="b6392-113">Specifies that the values in the specified property should be sorted in ascending order, from lowest value to highest value.</span></span> <span data-ttu-id="b6392-114">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="b6392-114">This is the default.</span></span>  
  
 <span data-ttu-id="b6392-115">DESC</span><span class="sxs-lookup"><span data-stu-id="b6392-115">DESC</span></span>  
 <span data-ttu-id="b6392-116">Określa, że wartości w określonej właściwości powinny być sortowane w kolejności malejącej, od najwyższego do najniższej wartości.</span><span class="sxs-lookup"><span data-stu-id="b6392-116">Specifies that the values in the specified property should be sorted in descending order, from highest value to lowest value.</span></span>  
  
 <span data-ttu-id="b6392-117">GRANICE `n`</span><span class="sxs-lookup"><span data-stu-id="b6392-117">LIMIT `n`</span></span>  
 <span data-ttu-id="b6392-118">Tylko pierwsze `n` elementy zostaną zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="b6392-118">Only the first `n` items will be selected.</span></span>  
  
 <span data-ttu-id="b6392-119">Skocz `n`</span><span class="sxs-lookup"><span data-stu-id="b6392-119">SKIP `n`</span></span>  
 <span data-ttu-id="b6392-120">Pomija pierwsze `n` elementy.</span><span class="sxs-lookup"><span data-stu-id="b6392-120">Skips the first `n` items.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6392-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b6392-121">Remarks</span></span>  

 <span data-ttu-id="b6392-122">Klauzula ORDER BY jest logicznie stosowana do wyniku klauzuli SELECT.</span><span class="sxs-lookup"><span data-stu-id="b6392-122">The ORDER BY clause is logically applied to the result of the SELECT clause.</span></span> <span data-ttu-id="b6392-123">Klauzula ORDER BY może odwoływać się do elementów na liście wyboru przy użyciu ich aliasów.</span><span class="sxs-lookup"><span data-stu-id="b6392-123">The ORDER BY clause can reference items in the select list by using their aliases.</span></span> <span data-ttu-id="b6392-124">Klauzula ORDER BY może odwoływać się również do innych zmiennych, które są obecnie w zakresie.</span><span class="sxs-lookup"><span data-stu-id="b6392-124">The ORDER BY clause can also reference other variables that are currently in-scope.</span></span> <span data-ttu-id="b6392-125">Jednakże jeśli klauzula SELECT została określona za pomocą modyfikatora DISTINCT, klauzula ORDER BY może odwoływać się tylko do aliasów z klauzuli SELECT.</span><span class="sxs-lookup"><span data-stu-id="b6392-125">However, if the SELECT clause has been specified with a DISTINCT modifier, the ORDER BY clause can only reference aliases from the SELECT clause.</span></span>  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 <span data-ttu-id="b6392-126">Każde wyrażenie w klauzuli ORDER BY musi być szacowane do pewnego typu, który można porównać w przypadku uporządkowanej nierówności (mniejszej lub większej niż itd.).</span><span class="sxs-lookup"><span data-stu-id="b6392-126">Each expression in the ORDER BY clause must evaluate to some type that can be compared for ordered inequality (less than or greater than, and so on).</span></span> <span data-ttu-id="b6392-127">Te typy są ogólnie skalarnymi typami podstawowymi, takimi jak liczby, ciągi i daty.</span><span class="sxs-lookup"><span data-stu-id="b6392-127">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="b6392-128">RowTypes porównywalnych typów są również uporządkowane porównywalnie.</span><span class="sxs-lookup"><span data-stu-id="b6392-128">RowTypes of comparable types are also order comparable.</span></span>  
  
 <span data-ttu-id="b6392-129">Jeśli kod wykonuje iterację dla zestawu uporządkowanego, innego niż projekcja najwyższego poziomu, nie ma gwarancji, że jego zamówienie jest zachowywane.</span><span class="sxs-lookup"><span data-stu-id="b6392-129">If your code iterates over an ordered set, other than for a top-level projection, the output is not guaranteed to have its order preserved.</span></span>  

<span data-ttu-id="b6392-130">W poniższym przykładzie porządek jest zagwarantowany do zachowania:</span><span class="sxs-lookup"><span data-stu-id="b6392-130">In the following sample, order is guaranteed to be preserved:</span></span>

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

<span data-ttu-id="b6392-131">W poniższym zapytaniu kolejność zagnieżdżonych zapytań jest ignorowana:</span><span class="sxs-lookup"><span data-stu-id="b6392-131">In the following query, ordering of the nested query is ignored:</span></span>  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 <span data-ttu-id="b6392-132">Aby mieć przepustą operację UNION, UNION ALL, EXCEPT lub INTERSECT, użyj następującego wzorca:</span><span class="sxs-lookup"><span data-stu-id="b6392-132">To have an ordered UNION, UNION ALL, EXCEPT, or INTERSECT operation, use the following pattern:</span></span>  
  
```sql  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a><span data-ttu-id="b6392-133">Zastrzeżone słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="b6392-133">Restricted keywords</span></span>  

 <span data-ttu-id="b6392-134">Następujące słowa kluczowe muszą być ujęte w znaki cudzysłowu, jeśli są używane w `ORDER BY` klauzuli:</span><span class="sxs-lookup"><span data-stu-id="b6392-134">The following keywords must be enclosed in quotation marks when used in an `ORDER BY` clause:</span></span>  
  
- <span data-ttu-id="b6392-135">GRANICY</span><span class="sxs-lookup"><span data-stu-id="b6392-135">CROSS</span></span>  
  
- <span data-ttu-id="b6392-136">SZCZEGÓŁOWE</span><span class="sxs-lookup"><span data-stu-id="b6392-136">FULL</span></span>  
  
- <span data-ttu-id="b6392-137">KEY</span><span class="sxs-lookup"><span data-stu-id="b6392-137">KEY</span></span>  
  
- <span data-ttu-id="b6392-138">LEFT</span><span class="sxs-lookup"><span data-stu-id="b6392-138">LEFT</span></span>  
  
- <span data-ttu-id="b6392-139">PORZĄDEK</span><span class="sxs-lookup"><span data-stu-id="b6392-139">ORDER</span></span>  
  
- <span data-ttu-id="b6392-140">BLASK</span><span class="sxs-lookup"><span data-stu-id="b6392-140">OUTER</span></span>  
  
- <span data-ttu-id="b6392-141">RIGHT</span><span class="sxs-lookup"><span data-stu-id="b6392-141">RIGHT</span></span>  
  
- <span data-ttu-id="b6392-142">ROW</span><span class="sxs-lookup"><span data-stu-id="b6392-142">ROW</span></span>  
  
- <span data-ttu-id="b6392-143">VALUE</span><span class="sxs-lookup"><span data-stu-id="b6392-143">VALUE</span></span>  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="b6392-144">Porządkowanie zagnieżdżonych zapytań</span><span class="sxs-lookup"><span data-stu-id="b6392-144">Ordering Nested Queries</span></span>  

 <span data-ttu-id="b6392-145">W Entity Framework wyrażenie zagnieżdżone można umieścić w dowolnym miejscu zapytania; kolejność zagnieżdżonych zapytań nie jest zachowywana.</span><span class="sxs-lookup"><span data-stu-id="b6392-145">In the Entity Framework, a nested expression can be placed anywhere in the query; the order of a nested query is not preserved.</span></span>  

<span data-ttu-id="b6392-146">Następujące zapytanie porządkuje wyniki według nazwiska:</span><span class="sxs-lookup"><span data-stu-id="b6392-146">The following query will order the results by the last name:</span></span>  

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

<span data-ttu-id="b6392-147">W poniższym zapytaniu kolejność zagnieżdżonych zapytań jest ignorowana:</span><span class="sxs-lookup"><span data-stu-id="b6392-147">In the following query, ordering of the nested query is ignored:</span></span>  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a><span data-ttu-id="b6392-148">Przykład</span><span class="sxs-lookup"><span data-stu-id="b6392-148">Example</span></span>  

 <span data-ttu-id="b6392-149">Poniższe [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytanie używa operatora order by, aby określić kolejność sortowania używaną dla obiektów zwracanych w instrukcji SELECT.</span><span class="sxs-lookup"><span data-stu-id="b6392-149">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ORDER BY operator to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="b6392-150">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b6392-150">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b6392-151">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="b6392-151">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b6392-152">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b6392-152">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b6392-153">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="b6392-153">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ORDERBY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#orderby)]  
  
## <a name="see-also"></a><span data-ttu-id="b6392-154">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b6392-154">See also</span></span>

- [<span data-ttu-id="b6392-155">Wyrażenia kwerend</span><span class="sxs-lookup"><span data-stu-id="b6392-155">Query Expressions</span></span>](query-expressions-entity-sql.md)
- [<span data-ttu-id="b6392-156">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="b6392-156">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="b6392-157">Skocz</span><span class="sxs-lookup"><span data-stu-id="b6392-157">SKIP</span></span>](skip-entity-sql.md)
- [<span data-ttu-id="b6392-158">GRANICE</span><span class="sxs-lookup"><span data-stu-id="b6392-158">LIMIT</span></span>](limit-entity-sql.md)
- [<span data-ttu-id="b6392-159">Do góry</span><span class="sxs-lookup"><span data-stu-id="b6392-159">TOP</span></span>](top-entity-sql.md)
