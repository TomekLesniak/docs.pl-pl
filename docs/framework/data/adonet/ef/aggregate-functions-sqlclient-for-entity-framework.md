---
title: Funkcje agregujące (SqlClient dla Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 1c32ccfe18c67c9baeb7df0f981c9129b3bbc8bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204518"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="ddd36-102">Funkcje agregujące (SqlClient dla Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="ddd36-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>

<span data-ttu-id="ddd36-103">Dostawca danych .NET Framework dla SQL Server (SqlClient) udostępnia funkcje agregujące.</span><span class="sxs-lookup"><span data-stu-id="ddd36-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="ddd36-104">Funkcje agregujące wykonują obliczenia na zestawie wartości wejściowych i zwracają wartość.</span><span class="sxs-lookup"><span data-stu-id="ddd36-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="ddd36-105">Te funkcje znajdują się w przestrzeni nazw SqlServer, która jest dostępna w przypadku korzystania z programu SqlClient.</span><span class="sxs-lookup"><span data-stu-id="ddd36-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="ddd36-106">Właściwość przestrzeni nazw dostawcy umożliwia Entity Framework odnajdywania prefiksu używanego przez tego dostawcę dla określonych konstrukcji, takich jak typy i funkcje.</span><span class="sxs-lookup"><span data-stu-id="ddd36-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="ddd36-107">Poniżej przedstawiono funkcje agregujące SqlClient.</span><span class="sxs-lookup"><span data-stu-id="ddd36-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="ddd36-108">Średnia (wyrażenie)</span><span class="sxs-lookup"><span data-stu-id="ddd36-108">AVG(expression)</span></span>

<span data-ttu-id="ddd36-109">Zwraca średnią wartości w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="ddd36-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="ddd36-110">Wartości null są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="ddd36-110">Null values are ignored.</span></span>

<span data-ttu-id="ddd36-111">**Argumenty**</span><span class="sxs-lookup"><span data-stu-id="ddd36-111">**Arguments**</span></span>

<span data-ttu-id="ddd36-112">`Int32`, `Int64` , `Double` , I `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="ddd36-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="ddd36-113">**Wartość zwracana**</span><span class="sxs-lookup"><span data-stu-id="ddd36-113">**Return Value**</span></span>

<span data-ttu-id="ddd36-114">Typ `expression` .</span><span class="sxs-lookup"><span data-stu-id="ddd36-114">The type of `expression`.</span></span>

<span data-ttu-id="ddd36-115">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="ddd36-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="ddd36-116">CHECKSUM_AGG (kolekcja)</span><span class="sxs-lookup"><span data-stu-id="ddd36-116">CHECKSUM_AGG(collection)</span></span>

 <span data-ttu-id="ddd36-117">Zwraca sumę kontrolną wartości w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="ddd36-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="ddd36-118">Wartości null są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="ddd36-118">Null values are ignored.</span></span>

 <span data-ttu-id="ddd36-119">**Argumenty**</span><span class="sxs-lookup"><span data-stu-id="ddd36-119">**Arguments**</span></span>

 <span data-ttu-id="ddd36-120">Kolekcja ( `Int32` ).</span><span class="sxs-lookup"><span data-stu-id="ddd36-120">A Collection(`Int32`).</span></span>

 <span data-ttu-id="ddd36-121">**Wartość zwracana**</span><span class="sxs-lookup"><span data-stu-id="ddd36-121">**Return Value**</span></span>

 <span data-ttu-id="ddd36-122">A `Int32` .</span><span class="sxs-lookup"><span data-stu-id="ddd36-122">An `Int32`.</span></span>

 <span data-ttu-id="ddd36-123">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="ddd36-123">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a><span data-ttu-id="ddd36-124">COUNT (wyrażenie)</span><span class="sxs-lookup"><span data-stu-id="ddd36-124">COUNT(expression)</span></span>

<span data-ttu-id="ddd36-125">Zwraca liczbę elementów w kolekcji jako `Int32` .</span><span class="sxs-lookup"><span data-stu-id="ddd36-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="ddd36-126">**Argumenty**</span><span class="sxs-lookup"><span data-stu-id="ddd36-126">**Arguments**</span></span>

<span data-ttu-id="ddd36-127">Kolekcja \<T> , gdzie T jest jednym z następujących typów:</span><span class="sxs-lookup"><span data-stu-id="ddd36-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="ddd36-128">`Guid` (niezwrócone w SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="ddd36-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="ddd36-129">**Wartość zwracana**</span><span class="sxs-lookup"><span data-stu-id="ddd36-129">**Return Value**</span></span>

<span data-ttu-id="ddd36-130">A `Int32` .</span><span class="sxs-lookup"><span data-stu-id="ddd36-130">An `Int32`.</span></span>

<span data-ttu-id="ddd36-131">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="ddd36-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a><span data-ttu-id="ddd36-132">COUNT_BIG (wyrażenie)</span><span class="sxs-lookup"><span data-stu-id="ddd36-132">COUNT_BIG(expression)</span></span>

<span data-ttu-id="ddd36-133">Zwraca liczbę elementów w kolekcji jako `bigint` .</span><span class="sxs-lookup"><span data-stu-id="ddd36-133">Returns the number of items in a collection as a `bigint`.</span></span>

 <span data-ttu-id="ddd36-134">**Argumenty**</span><span class="sxs-lookup"><span data-stu-id="ddd36-134">**Arguments**</span></span>

 <span data-ttu-id="ddd36-135">Kolekcja (T), gdzie T jest jednym z następujących typów:</span><span class="sxs-lookup"><span data-stu-id="ddd36-135">A Collection(T), where T is one of the following types:</span></span>

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="ddd36-136">`Guid` (niezwrócone w SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="ddd36-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="ddd36-137">**Wartość zwracana**</span><span class="sxs-lookup"><span data-stu-id="ddd36-137">**Return Value**</span></span>

<span data-ttu-id="ddd36-138">A `Int64` .</span><span class="sxs-lookup"><span data-stu-id="ddd36-138">An `Int64`.</span></span>

<span data-ttu-id="ddd36-139">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="ddd36-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="ddd36-140">MAX (wyrażenie)</span><span class="sxs-lookup"><span data-stu-id="ddd36-140">MAX(expression)</span></span>

<span data-ttu-id="ddd36-141">Zwraca maksymalną wartość kolekcji.</span><span class="sxs-lookup"><span data-stu-id="ddd36-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="ddd36-142">**Argumenty**</span><span class="sxs-lookup"><span data-stu-id="ddd36-142">**Arguments**</span></span>

<span data-ttu-id="ddd36-143">Kolekcja (T), gdzie T jest jednym z następujących typów:</span><span class="sxs-lookup"><span data-stu-id="ddd36-143">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="ddd36-144">**Wartość zwracana**</span><span class="sxs-lookup"><span data-stu-id="ddd36-144">**Return Value**</span></span>

<span data-ttu-id="ddd36-145">Typ `expression` .</span><span class="sxs-lookup"><span data-stu-id="ddd36-145">The type of `expression`.</span></span>

<span data-ttu-id="ddd36-146">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="ddd36-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="ddd36-147">MIN (wyrażenie)</span><span class="sxs-lookup"><span data-stu-id="ddd36-147">MIN(expression)</span></span>

<span data-ttu-id="ddd36-148">Zwraca minimalną wartość w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="ddd36-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="ddd36-149">**Argumenty**</span><span class="sxs-lookup"><span data-stu-id="ddd36-149">**Arguments**</span></span>

<span data-ttu-id="ddd36-150">Kolekcja (T), gdzie T jest jednym z następujących typów:</span><span class="sxs-lookup"><span data-stu-id="ddd36-150">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="ddd36-151">**Wartość zwracana**</span><span class="sxs-lookup"><span data-stu-id="ddd36-151">**Return Value**</span></span>

<span data-ttu-id="ddd36-152">Typ `expression` .</span><span class="sxs-lookup"><span data-stu-id="ddd36-152">The type of `expression`.</span></span>

<span data-ttu-id="ddd36-153">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="ddd36-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="ddd36-154">STDEV (wyrażenie)</span><span class="sxs-lookup"><span data-stu-id="ddd36-154">STDEV(expression)</span></span>

<span data-ttu-id="ddd36-155">Zwraca statystyczne odchylenie standardowe wszystkich wartości w określonym wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="ddd36-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="ddd36-156">**Argumenty**</span><span class="sxs-lookup"><span data-stu-id="ddd36-156">**Arguments**</span></span>

<span data-ttu-id="ddd36-157">Kolekcja ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="ddd36-157">A Collection(`Double`).</span></span>

<span data-ttu-id="ddd36-158">**Wartość zwracana**</span><span class="sxs-lookup"><span data-stu-id="ddd36-158">**Return Value**</span></span>

<span data-ttu-id="ddd36-159">Klasa `Double`.</span><span class="sxs-lookup"><span data-stu-id="ddd36-159">A `Double`.</span></span>

<span data-ttu-id="ddd36-160">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="ddd36-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="ddd36-161">STDEVP (wyrażenie)</span><span class="sxs-lookup"><span data-stu-id="ddd36-161">STDEVP(expression)</span></span>

<span data-ttu-id="ddd36-162">Zwraca statystyczne odchylenie standardowe populacji dla wszystkich wartości w określonym wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="ddd36-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="ddd36-163">**Argumenty**</span><span class="sxs-lookup"><span data-stu-id="ddd36-163">**Arguments**</span></span>

<span data-ttu-id="ddd36-164">Kolekcja ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="ddd36-164">A Collection(`Double`).</span></span>

<span data-ttu-id="ddd36-165">**Wartość zwracana**</span><span class="sxs-lookup"><span data-stu-id="ddd36-165">**Return Value**</span></span>

<span data-ttu-id="ddd36-166">Klasa `Double`.</span><span class="sxs-lookup"><span data-stu-id="ddd36-166">A `Double`.</span></span>

<span data-ttu-id="ddd36-167">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="ddd36-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="ddd36-168">SUM (wyrażenie)</span><span class="sxs-lookup"><span data-stu-id="ddd36-168">SUM(expression)</span></span>

<span data-ttu-id="ddd36-169">Zwraca sumę wszystkich wartości w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="ddd36-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="ddd36-170">**Argumenty**</span><span class="sxs-lookup"><span data-stu-id="ddd36-170">**Arguments**</span></span>

<span data-ttu-id="ddd36-171">Kolekcja (T), gdzie T jest jednym z następujących typów: `Int32` , `Int64` , `Double` , `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="ddd36-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="ddd36-172">**Wartość zwracana**</span><span class="sxs-lookup"><span data-stu-id="ddd36-172">**Return Value**</span></span>

<span data-ttu-id="ddd36-173">Typ `expression` .</span><span class="sxs-lookup"><span data-stu-id="ddd36-173">The type of `expression`.</span></span>

<span data-ttu-id="ddd36-174">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="ddd36-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="ddd36-175">VAR (wyrażenie)</span><span class="sxs-lookup"><span data-stu-id="ddd36-175">VAR(expression)</span></span>

<span data-ttu-id="ddd36-176">Zwraca wariancję statystyczną wszystkich wartości w określonym wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="ddd36-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="ddd36-177">**Argumenty**</span><span class="sxs-lookup"><span data-stu-id="ddd36-177">**Arguments**</span></span>

<span data-ttu-id="ddd36-178">Kolekcja ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="ddd36-178">A Collection(`Double`).</span></span>

<span data-ttu-id="ddd36-179">**Wartość zwracana**</span><span class="sxs-lookup"><span data-stu-id="ddd36-179">**Return Value**</span></span>

<span data-ttu-id="ddd36-180">Klasa `Double`.</span><span class="sxs-lookup"><span data-stu-id="ddd36-180">A `Double`.</span></span>

<span data-ttu-id="ddd36-181">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="ddd36-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="ddd36-182">VARP (wyrażenie)</span><span class="sxs-lookup"><span data-stu-id="ddd36-182">VARP(expression)</span></span>

<span data-ttu-id="ddd36-183">Zwraca wariancję statystyczną dla populacji dla wszystkich wartości w określonym wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="ddd36-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="ddd36-184">**Argumenty**</span><span class="sxs-lookup"><span data-stu-id="ddd36-184">**Arguments**</span></span>

<span data-ttu-id="ddd36-185">Kolekcja ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="ddd36-185">A Collection(`Double`).</span></span>

<span data-ttu-id="ddd36-186">**Wartość zwracana**</span><span class="sxs-lookup"><span data-stu-id="ddd36-186">**Return Value**</span></span>

<span data-ttu-id="ddd36-187">Klasa `Double`.</span><span class="sxs-lookup"><span data-stu-id="ddd36-187">A `Double`.</span></span>

<span data-ttu-id="ddd36-188">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="ddd36-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a><span data-ttu-id="ddd36-189">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ddd36-189">See also</span></span>

- [<span data-ttu-id="ddd36-190">Funkcje agregujące (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ddd36-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="ddd36-191">Jednostki języka SQL</span><span class="sxs-lookup"><span data-stu-id="ddd36-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="ddd36-192">Funkcje agregujące Canonical</span><span class="sxs-lookup"><span data-stu-id="ddd36-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
