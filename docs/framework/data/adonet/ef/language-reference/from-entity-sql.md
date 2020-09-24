---
title: OD (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ff3e3048-0d5d-4502-ae5c-9187fcbd0514
ms.openlocfilehash: 8affac82fb1813aa0282540b5dc2f47d42234a1b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148061"
---
# <a name="from-entity-sql"></a><span data-ttu-id="3d520-102">OD (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3d520-102">FROM (Entity SQL)</span></span>

<span data-ttu-id="3d520-103">Określa kolekcję używaną w instrukcjach [SELECT](select-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="3d520-103">Specifies the collection used in [SELECT](select-entity-sql.md) statements.</span></span>

## <a name="syntax"></a><span data-ttu-id="3d520-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3d520-104">Syntax</span></span>

```sql
FROM expression [ ,...n ] AS C
```

## <a name="arguments"></a><span data-ttu-id="3d520-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="3d520-105">Arguments</span></span>

`expression` \
<span data-ttu-id="3d520-106">Każde prawidłowe wyrażenie zapytania, które zwraca kolekcję do użycia jako źródło w `SELECT` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="3d520-106">Any valid query expression that yields a collection to use as a source in a `SELECT` statement.</span></span>

## <a name="remarks"></a><span data-ttu-id="3d520-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3d520-107">Remarks</span></span>

<span data-ttu-id="3d520-108">`FROM`Klauzula jest rozdzielaną przecinkami listą `FROM` elementów klauzuli.</span><span class="sxs-lookup"><span data-stu-id="3d520-108">A `FROM` clause is a comma-separated list of one or more `FROM` clause items.</span></span> <span data-ttu-id="3d520-109">`FROM`Klauzula może służyć do określenia co najmniej jednego źródła dla `SELECT` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="3d520-109">The `FROM` clause can be used to specify one or more sources for a `SELECT` statement.</span></span> <span data-ttu-id="3d520-110">Najprostsza forma `FROM` klauzuli to pojedyncze wyrażenie zapytania, które identyfikuje kolekcję i alias używany jako źródło w `SELECT` instrukcji, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="3d520-110">The simplest form of a `FROM` clause is a single query expression that identifies a collection and an alias used as the source in a `SELECT` statement, as illustrated in the following example:</span></span>

`FROM C as c`

## <a name="from-clause-items"></a><span data-ttu-id="3d520-111">Elementy klauzuli FROM</span><span class="sxs-lookup"><span data-stu-id="3d520-111">FROM Clause Items</span></span>

<span data-ttu-id="3d520-112">Każdy `FROM` element klauzuli odwołuje się do kolekcji źródłowej w [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="3d520-112">Each `FROM` clause item refers to a source collection in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="3d520-113">obsługuje następujące klasy `FROM` elementów klauzuli: proste elementy klauzuli `FROM` , `JOIN FROM` elementy klauzuli i `APPLY FROM` klauzule.</span><span class="sxs-lookup"><span data-stu-id="3d520-113">supports the following classes of `FROM` clause items: simple `FROM` clause items, `JOIN FROM` clause items, and `APPLY FROM` clause items.</span></span> <span data-ttu-id="3d520-114">Każdy z tych `FROM` elementów klauzuli został opisany bardziej szczegółowo w poniższych sekcjach.</span><span class="sxs-lookup"><span data-stu-id="3d520-114">Each of these `FROM` clause items is described in more detail in the following sections.</span></span>

### <a name="simple-from-clause-item"></a><span data-ttu-id="3d520-115">Prosty element klauzuli FROM</span><span class="sxs-lookup"><span data-stu-id="3d520-115">Simple FROM Clause Item</span></span>

<span data-ttu-id="3d520-116">`FROM`Element klauzuli najprostsza jest pojedynczym wyrażeniem, które identyfikuje kolekcję i alias.</span><span class="sxs-lookup"><span data-stu-id="3d520-116">The simplest `FROM` clause item is a single expression that identifies a collection and an alias.</span></span> <span data-ttu-id="3d520-117">Wyrażenie może po prostu być zestawem jednostek lub podzapytaniem albo innym wyrażeniem, które jest typem kolekcji.</span><span class="sxs-lookup"><span data-stu-id="3d520-117">The expression can simply be an entity set, or a subquery, or any other expression that is a collection type.</span></span> <span data-ttu-id="3d520-118">Poniżej przedstawiono przykład:</span><span class="sxs-lookup"><span data-stu-id="3d520-118">The following is an example:</span></span>

```sql
LOB.Customers as c
```

<span data-ttu-id="3d520-119">Specyfikacja aliasu jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="3d520-119">The alias specification is optional.</span></span> <span data-ttu-id="3d520-120">Alternatywna Specyfikacja powyższego elementu klauzuli FROM może być następująca:</span><span class="sxs-lookup"><span data-stu-id="3d520-120">An alternate specification of the above from clause item could be the following:</span></span>

```sql
LOB.Customers
```

<span data-ttu-id="3d520-121">Jeśli alias nie zostanie określony, program [!INCLUDE[esql](../../../../../../includes/esql-md.md)] podejmie próbę wygenerowania aliasu na podstawie wyrażenia kolekcji.</span><span class="sxs-lookup"><span data-stu-id="3d520-121">If no alias is specified, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] attempts to generate an alias based on the collection expression.</span></span>

### <a name="join-from-clause-item"></a><span data-ttu-id="3d520-122">Element klauzuli JOIN</span><span class="sxs-lookup"><span data-stu-id="3d520-122">JOIN FROM Clause Item</span></span>

<span data-ttu-id="3d520-123">`JOIN FROM`Element klauzuli reprezentuje sprzężenie między dwoma `FROM` elementami klauzuli.</span><span class="sxs-lookup"><span data-stu-id="3d520-123">A `JOIN FROM` clause item represents a join between two `FROM` clause items.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="3d520-124">obsługuje sprzężenia krzyżowe, sprzężenia wewnętrzne, sprzężenia zewnętrzne Left i Right oraz pełne sprzężenia zewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="3d520-124">supports cross joins, inner joins, left and right outer joins, and full outer joins.</span></span> <span data-ttu-id="3d520-125">Wszystkie te sprzężenia są obsługiwane podobne do sposobu, w jaki są obsługiwane w języku Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="3d520-125">All these joins are supported similar to the way that they are supported in Transact-SQL.</span></span> <span data-ttu-id="3d520-126">Podobnie jak w języku Transact-SQL, dwie `FROM` klauzule `JOIN` muszą być niezależne.</span><span class="sxs-lookup"><span data-stu-id="3d520-126">As in Transact-SQL, the two `FROM` clause items involved in the `JOIN` must be independent.</span></span> <span data-ttu-id="3d520-127">Oznacza to, że nie mogą być skorelowane.</span><span class="sxs-lookup"><span data-stu-id="3d520-127">That is, they cannot be correlated.</span></span> <span data-ttu-id="3d520-128">A `CROSS APPLY` lub `OUTER APPLY` może być używany w takich przypadkach.</span><span class="sxs-lookup"><span data-stu-id="3d520-128">A `CROSS APPLY` or `OUTER APPLY` can be used for these cases.</span></span>

#### <a name="cross-joins"></a><span data-ttu-id="3d520-129">Sprzężenia krzyżowe</span><span class="sxs-lookup"><span data-stu-id="3d520-129">Cross Joins</span></span>

<span data-ttu-id="3d520-130">`CROSS JOIN`Wyrażenie zapytania generuje produkt kartezjańskiego dwóch kolekcji, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="3d520-130">A `CROSS JOIN` query expression produces the Cartesian product of the two collections, as illustrated in the following example:</span></span>

`FROM C AS c CROSS JOIN D as d`

#### <a name="inner-joins"></a><span data-ttu-id="3d520-131">Sprzężenia wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="3d520-131">Inner Joins</span></span>

<span data-ttu-id="3d520-132">`INNER JOIN`Tworzy ograniczony produkt kartezjańskiego dla dwóch kolekcji, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="3d520-132">An `INNER JOIN` produces a constrained Cartesian product of the two collections, as illustrated in the following example:</span></span>

`FROM C AS c [INNER] JOIN D AS d ON e`

<span data-ttu-id="3d520-133">Poprzednie wyrażenie zapytania przetwarza kombinację każdego elementu kolekcji po lewej stronie dla każdego elementu kolekcji po prawej stronie, gdzie `ON` warunek ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="3d520-133">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="3d520-134">Jeśli `ON` warunek nie zostanie określony, `INNER JOIN` degeneruje do `CROSS JOIN` .</span><span class="sxs-lookup"><span data-stu-id="3d520-134">If no `ON` condition is specified, an `INNER JOIN` degenerates to a `CROSS JOIN`.</span></span>

#### <a name="left-outer-joins-and-right-outer-joins"></a><span data-ttu-id="3d520-135">Lewe sprzężenia zewnętrzne i prawe sprzężenia zewnętrzne</span><span class="sxs-lookup"><span data-stu-id="3d520-135">Left Outer Joins and Right Outer Joins</span></span>

<span data-ttu-id="3d520-136">`OUTER JOIN`Wyrażenie zapytania tworzy ograniczony produkt kartezjańskiego dla dwóch kolekcji, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="3d520-136">An `OUTER JOIN` query expression produces a constrained Cartesian product of the two collections, as illustrated in the following example:</span></span>

`FROM C AS c LEFT OUTER JOIN D AS d ON e`

<span data-ttu-id="3d520-137">Poprzednie wyrażenie zapytania przetwarza kombinację każdego elementu kolekcji po lewej stronie dla każdego elementu kolekcji po prawej stronie, gdzie `ON` warunek ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="3d520-137">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="3d520-138">Jeśli `ON` warunek ma wartość false, wyrażenie nadal przetwarza pojedyncze wystąpienie elementu w lewej parze z elementem po prawej stronie, z wartością null.</span><span class="sxs-lookup"><span data-stu-id="3d520-138">If the `ON` condition is false, the expression still processes a single instance of the element on the left paired against the element on the right, with the value null.</span></span>

<span data-ttu-id="3d520-139">A `RIGHT OUTER JOIN` może być wyrażona w podobny sposób.</span><span class="sxs-lookup"><span data-stu-id="3d520-139">A `RIGHT OUTER JOIN` may be expressed in a similar manner.</span></span>

#### <a name="full-outer-joins"></a><span data-ttu-id="3d520-140">Pełne sprzężenia zewnętrzne</span><span class="sxs-lookup"><span data-stu-id="3d520-140">Full Outer Joins</span></span>

<span data-ttu-id="3d520-141">Jawne `FULL OUTER JOIN` tworzy ograniczony produkt kartezjańskiego dla dwóch kolekcji, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="3d520-141">An explicit `FULL OUTER JOIN` produces a constrained Cartesian product of the two collections as illustrated in the following example:</span></span>

`FROM C AS c FULL OUTER JOIN D AS d ON e`

<span data-ttu-id="3d520-142">Poprzednie wyrażenie zapytania przetwarza kombinację każdego elementu kolekcji po lewej stronie dla każdego elementu kolekcji po prawej stronie, gdzie `ON` warunek ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="3d520-142">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="3d520-143">Jeśli `ON` warunek ma wartość false, wyrażenie nadal przetwarza jedno wystąpienie elementu w lewej parze względem elementu po prawej stronie, z wartością null.</span><span class="sxs-lookup"><span data-stu-id="3d520-143">If the `ON` condition is false, the expression still processes one instance of the element on the left paired against the element on the right, with the value null.</span></span> <span data-ttu-id="3d520-144">Przetwarza także jedno wystąpienie elementu w prawej parze względem elementu po lewej stronie, z wartością null.</span><span class="sxs-lookup"><span data-stu-id="3d520-144">It also processes one instance of the element on the right paired against the element on the left, with the value null.</span></span>

> [!NOTE]
> <span data-ttu-id="3d520-145">Aby zachować zgodność z SQL-92, w języku Transact-SQL słowo kluczowe OUTER jest opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="3d520-145">To preserve compatibility with SQL-92, in Transact-SQL the OUTER keyword is optional.</span></span> <span data-ttu-id="3d520-146">W związku z tym,, `LEFT JOIN` `RIGHT JOIN` i `FULL JOIN` są synonimami dla `LEFT OUTER JOIN` , `RIGHT OUTER JOIN` , i `FULL OUTER JOIN` .</span><span class="sxs-lookup"><span data-stu-id="3d520-146">Therefore, `LEFT JOIN`, `RIGHT JOIN`, and `FULL JOIN` are synonyms for `LEFT OUTER JOIN`, `RIGHT OUTER JOIN`, and `FULL OUTER JOIN`.</span></span>

### <a name="apply-clause-item"></a><span data-ttu-id="3d520-147">APPLY — element klauzuli</span><span class="sxs-lookup"><span data-stu-id="3d520-147">APPLY Clause Item</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="3d520-148">obsługuje dwa rodzaje `APPLY` : `CROSS APPLY` i `OUTER APPLY` .</span><span class="sxs-lookup"><span data-stu-id="3d520-148">supports two kinds of `APPLY`: `CROSS APPLY` and `OUTER APPLY`.</span></span>

<span data-ttu-id="3d520-149">A tworzy `CROSS APPLY` unikatową parowanie każdego elementu kolekcji po lewej stronie z elementem kolekcji utworzonej przez obliczenie wyrażenia po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="3d520-149">A `CROSS APPLY` produces a unique pairing of each element of the collection on the left with an element of the collection produced by evaluating the expression on the right.</span></span> <span data-ttu-id="3d520-150">Wyrażenie po `CROSS APPLY` prawej stronie jest funkcjonalnie zależne od elementu po lewej stronie, jak pokazano w następującym przykładzie skojarzonej kolekcji:</span><span class="sxs-lookup"><span data-stu-id="3d520-150">With a `CROSS APPLY`, the expression on the right is functionally dependent on the element on the left, as illustrated in the following associated collection example:</span></span>

`SELECT c, f FROM C AS c CROSS APPLY c.Assoc AS f`

<span data-ttu-id="3d520-151">Zachowanie `CROSS APPLY` jest podobne do listy sprzężenia.</span><span class="sxs-lookup"><span data-stu-id="3d520-151">The behavior of `CROSS APPLY` is similar to the join list.</span></span> <span data-ttu-id="3d520-152">Jeśli wyrażenie po prawej stronie zwraca pustą kolekcję, `CROSS APPLY` nie tworzy żadnych par dla tego wystąpienia elementu po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="3d520-152">If the expression on the right evaluates to an empty collection, the `CROSS APPLY` produces no pairings for that instance of the element on the left.</span></span>

<span data-ttu-id="3d520-153">`OUTER APPLY`Przypomina `CROSS APPLY` , z wyjątkiem tego, że parowanie jest nadal generowane nawet wtedy, gdy wyrażenie po prawej stronie oblicza pustą kolekcję.</span><span class="sxs-lookup"><span data-stu-id="3d520-153">An `OUTER APPLY` resembles a `CROSS APPLY`, except a pairing is still produced even when the expression on the right evaluates to an empty collection.</span></span> <span data-ttu-id="3d520-154">Oto przykład `OUTER APPLY` :</span><span class="sxs-lookup"><span data-stu-id="3d520-154">The following is an example of an `OUTER APPLY`:</span></span>

`SELECT c, f FROM C AS c OUTER APPLY c.Assoc AS f`

> [!NOTE]
> <span data-ttu-id="3d520-155">W przeciwieństwie do języka Transact-SQL nie ma potrzeby jawnego kroku unnesting w [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d520-155">Unlike in Transact-SQL, there is no need for an explicit unnest step in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

> [!NOTE]
> <span data-ttu-id="3d520-156">`CROSS``OUTER APPLY`Operatory i zostały wprowadzone w SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3d520-156">`CROSS` and `OUTER APPLY` operators were introduced in SQL Server 2005.</span></span> <span data-ttu-id="3d520-157">W niektórych przypadkach potok zapytania może generować Transact-SQL, które zawierają `CROSS APPLY` Operatory i/lub `OUTER APPLY` .</span><span class="sxs-lookup"><span data-stu-id="3d520-157">In some cases, the query pipeline might produce Transact-SQL that contains `CROSS APPLY` and/or `OUTER APPLY` operators.</span></span> <span data-ttu-id="3d520-158">Ponieważ niektórzy dostawcy zaplecza, w tym wersje SQL Server wcześniejsze niż SQL Server 2005, nie obsługują tych operatorów, takie zapytania nie mogą być wykonywane w tych dostawcach zaplecza.</span><span class="sxs-lookup"><span data-stu-id="3d520-158">Because some backend providers, including versions of SQL Server earlier than SQL Server 2005, do not support these operators, such queries cannot be executed on these backend providers.</span></span>
>
> <span data-ttu-id="3d520-159">Niektóre typowe scenariusze, które mogą prowadzić do obecności `CROSS APPLY` i/lub `OUTER APPLY` operatorów w zapytaniu wyjściowym są następujące: skorelowane podzapytanie ze stronicowaniem; AnyElement za pomocą skorelowanego podzapytania lub kolekcji utworzonej przez nawigację; Zapytania LINQ używające metod grupowania, które akceptują selektor elementu; zapytanie, które jest `CROSS APPLY` `OUTER APPLY` jawnie określone lub jest zapytania, które ma `DEREF` konstrukcję w `REF` konstrukcji.</span><span class="sxs-lookup"><span data-stu-id="3d520-159">Some typical scenarios that might lead to the presence of `CROSS APPLY` and/or `OUTER APPLY` operators in the output query are the following: a correlated subquery with paging; AnyElement over a correlated subquery or over a collection produced by navigation; LINQ queries that use grouping methods that accept an element selector; a query in which a `CROSS APPLY` or an `OUTER APPLY` are explicitly specified; a query that has a `DEREF` construct over a `REF` construct.</span></span>

## <a name="multiple-collections-in-the-from-clause"></a><span data-ttu-id="3d520-160">Wiele kolekcji w klauzuli FROM</span><span class="sxs-lookup"><span data-stu-id="3d520-160">Multiple Collections in the FROM Clause</span></span>

<span data-ttu-id="3d520-161">`FROM`Klauzula może zawierać więcej niż jedną kolekcję oddzieloną przecinkami.</span><span class="sxs-lookup"><span data-stu-id="3d520-161">The `FROM` clause can contain more than one collection separated by commas.</span></span> <span data-ttu-id="3d520-162">W takich przypadkach przyjmuje się, że kolekcje są połączone ze sobą.</span><span class="sxs-lookup"><span data-stu-id="3d520-162">In these cases, the collections are assumed to be joined together.</span></span> <span data-ttu-id="3d520-163">Zastanów się nad nimi jako SPRZĘŻENIem KRZYŻowym.</span><span class="sxs-lookup"><span data-stu-id="3d520-163">Think of these as an n-way CROSS JOIN.</span></span>

<span data-ttu-id="3d520-164">W poniższym przykładzie `C` i `D` są niezależnymi kolekcjami, ale `c.Names` jest zależne od `C` .</span><span class="sxs-lookup"><span data-stu-id="3d520-164">In the following example, `C` and `D` are independent collections, but `c.Names` is dependent on `C`.</span></span>

```sql
FROM C AS c, D AS d, c.Names AS e
```

<span data-ttu-id="3d520-165">Poprzedni przykład jest logicznym odpowiednikiem poniższego przykładu:</span><span class="sxs-lookup"><span data-stu-id="3d520-165">The previous example is logically equivalent to the following example:</span></span>

`FROM (C AS c JOIN D AS d) CROSS APPLY c.Names AS e`

## <a name="left-correlation"></a><span data-ttu-id="3d520-166">Lewa korelacja</span><span class="sxs-lookup"><span data-stu-id="3d520-166">Left Correlation</span></span>

 <span data-ttu-id="3d520-167">Elementy w `FROM` klauzuli mogą odwoływać się do elementów określonych w klauzulach wcześniejszych.</span><span class="sxs-lookup"><span data-stu-id="3d520-167">Items in the `FROM` clause can refer to items specified in earlier clauses.</span></span> <span data-ttu-id="3d520-168">W poniższym przykładzie `C` i `D` są niezależnymi kolekcjami, ale `c.Names` jest zależne od `C` :</span><span class="sxs-lookup"><span data-stu-id="3d520-168">In the following example, `C` and `D` are independent collections, but `c.Names` is dependent on `C`:</span></span>

```sql
from C as c, D as d, c.Names as e
```

<span data-ttu-id="3d520-169">Jest to logicznie równoważne z:</span><span class="sxs-lookup"><span data-stu-id="3d520-169">This is logically equivalent to:</span></span>

```sql
from (C as c join D as d) cross apply c.Names as e
```

## <a name="semantics"></a><span data-ttu-id="3d520-170">Semantyka</span><span class="sxs-lookup"><span data-stu-id="3d520-170">Semantics</span></span>

<span data-ttu-id="3d520-171">Logicznie kolekcje w `FROM` klauzuli są zakładane jako część `n` sprzężenia krzyżowego (z wyjątkiem w przypadku 1-kierunkowego sprzężenia krzyżowego).</span><span class="sxs-lookup"><span data-stu-id="3d520-171">Logically, the collections in the `FROM` clause are assumed to be part of an `n`-way cross join (except in the case of a 1-way cross join).</span></span> <span data-ttu-id="3d520-172">Aliasy w `FROM` klauzuli są przetwarzane od lewej do prawej i są dodawane do bieżącego zakresu w celu późniejszego odwołania.</span><span class="sxs-lookup"><span data-stu-id="3d520-172">Aliases in the `FROM` clause are processed left to right, and are added to the current scope for later reference.</span></span> <span data-ttu-id="3d520-173">`FROM`Przyjęto, że klauzula tworzy zestaw wielokrotny wierszy.</span><span class="sxs-lookup"><span data-stu-id="3d520-173">The `FROM` clause is assumed to produce a multiset of rows.</span></span> <span data-ttu-id="3d520-174">Dla każdego elementu w `FROM` klauzuli, który reprezentuje pojedynczy element z tego elementu kolekcji, będzie jedno pole.</span><span class="sxs-lookup"><span data-stu-id="3d520-174">There will be one field for each item in the `FROM` clause that represents a single element from that collection item.</span></span>

<span data-ttu-id="3d520-175">`FROM`Klauzula logicznie tworzy zestaw wielokrotny wierszy typu Row (c, d, e), gdzie pola c, d i e są zakładane jako typ elementu `C` , `D` , i `c.Names` .</span><span class="sxs-lookup"><span data-stu-id="3d520-175">The `FROM` clause logically produces a multiset of rows of type Row(c, d, e) where fields c, d, and e are assumed to be of the element type of `C`, `D`, and `c.Names`.</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="3d520-176">wprowadza alias dla każdego elementu prostej `FROM` klauzuli w zakresie.</span><span class="sxs-lookup"><span data-stu-id="3d520-176">introduces an alias for each simple `FROM` clause item in scope.</span></span> <span data-ttu-id="3d520-177">Na przykład, w poniższym fragmencie kodu klauzuli, nazwy wprowadzone do zakresu to c, d i e.</span><span class="sxs-lookup"><span data-stu-id="3d520-177">For example, in the following FROM clause snippet, The names introduced into scope are c, d, and e.</span></span>

```sql
from (C as c join D as d) cross apply c.Names as e
```

<span data-ttu-id="3d520-178">W programie [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (w przeciwieństwie do języka Transact-SQL) `FROM` klauzula wprowadza tylko aliasy do zakresu.</span><span class="sxs-lookup"><span data-stu-id="3d520-178">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (unlike Transact-SQL), the `FROM` clause only introduces the aliases into scope.</span></span> <span data-ttu-id="3d520-179">Wszystkie odwołania do kolumn (właściwości) tych kolekcji muszą być kwalifikowane przy użyciu aliasu.</span><span class="sxs-lookup"><span data-stu-id="3d520-179">Any references to columns (properties) of these collections must be qualified with the alias.</span></span>

## <a name="pulling-up-keys-from-nested-queries"></a><span data-ttu-id="3d520-180">Ściąganie kluczy z zagnieżdżonych zapytań</span><span class="sxs-lookup"><span data-stu-id="3d520-180">Pulling Up Keys from Nested Queries</span></span>

<span data-ttu-id="3d520-181">Niektóre typy zapytań, które wymagają ściągania kluczy z zapytania zagnieżdżonego, nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="3d520-181">Certain types of queries that require pulling up keys from a nested query are not supported.</span></span> <span data-ttu-id="3d520-182">Na przykład następujące zapytanie jest prawidłowe:</span><span class="sxs-lookup"><span data-stu-id="3d520-182">For example, the following query is valid:</span></span>

```sql
select c.Orders from Customers as c
```

<span data-ttu-id="3d520-183">Jednak następujące zapytanie jest nieprawidłowe, ponieważ zapytanie zagnieżdżone nie ma żadnych kluczy:</span><span class="sxs-lookup"><span data-stu-id="3d520-183">However, the following query is not valid, because the nested query does not have any keys:</span></span>

```sql
select {1} from {2, 3}
```

## <a name="see-also"></a><span data-ttu-id="3d520-184">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3d520-184">See also</span></span>

- [<span data-ttu-id="3d520-185">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="3d520-185">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="3d520-186">Wyrażenia kwerend</span><span class="sxs-lookup"><span data-stu-id="3d520-186">Query Expressions</span></span>](query-expressions-entity-sql.md)
- [<span data-ttu-id="3d520-187">Typy strukturalne dopuszczające wartości Null</span><span class="sxs-lookup"><span data-stu-id="3d520-187">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
