---
title: Język Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 2600b7626ebc5196c702f2d1e3159fd9549227f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553385"
---
# <a name="entity-sql-language"></a><span data-ttu-id="eb20d-102">Język Entity SQL</span><span class="sxs-lookup"><span data-stu-id="eb20d-102">Entity SQL Language</span></span>
<span data-ttu-id="eb20d-103">Entity SQL to język zapytań niezależnych od magazynu, podobny do SQL.</span><span class="sxs-lookup"><span data-stu-id="eb20d-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="eb20d-104">Entity SQL umożliwia wykonywanie zapytań dotyczących danych jednostki jako obiektów lub w formie tabelarycznej.</span><span class="sxs-lookup"><span data-stu-id="eb20d-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="eb20d-105">Należy rozważyć użycie Entity SQL w następujących przypadkach:</span><span class="sxs-lookup"><span data-stu-id="eb20d-105">You should consider using Entity SQL in the following cases:</span></span>  
  
- <span data-ttu-id="eb20d-106">Gdy zapytanie musi być skonstruowane dynamicznie w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="eb20d-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="eb20d-107">W takim przypadku należy również rozważyć użycie metod konstruktora zapytań <xref:System.Data.Objects.ObjectQuery%601> zamiast konstruowania Entity SQL ciągu zapytania w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="eb20d-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
- <span data-ttu-id="eb20d-108">Jeśli chcesz zdefiniować zapytanie jako część definicji modelu.</span><span class="sxs-lookup"><span data-stu-id="eb20d-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="eb20d-109">Tylko Entity SQL jest obsługiwane w modelu danych.</span><span class="sxs-lookup"><span data-stu-id="eb20d-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="eb20d-110">Aby uzyskać więcej informacji, zobacz [QueryView element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span><span class="sxs-lookup"><span data-stu-id="eb20d-110">For more information, see [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span></span>  
  
- <span data-ttu-id="eb20d-111">W przypadku używania EntityClient do zwracania danych jednostki tylko do odczytu jako zestawów wierszy przy użyciu <xref:System.Data.EntityClient.EntityDataReader> .</span><span class="sxs-lookup"><span data-stu-id="eb20d-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="eb20d-112">Aby uzyskać więcej informacji, zobacz [EntityClient Provider for the Entity Framework](../entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="eb20d-112">For more information, see [EntityClient Provider for the Entity Framework](../entityclient-provider-for-the-entity-framework.md).</span></span>  
  
- <span data-ttu-id="eb20d-113">Jeśli już jesteś ekspertem w językach zapytań opartych na języku SQL, Entity SQL mogą być najbardziej naturalne.</span><span class="sxs-lookup"><span data-stu-id="eb20d-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="eb20d-114">Używanie Entity SQL z dostawcą EntityClient</span><span class="sxs-lookup"><span data-stu-id="eb20d-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="eb20d-115">Jeśli chcesz użyć Entity SQL z dostawcą EntityClient, zobacz następujące tematy, aby uzyskać więcej informacji:</span><span class="sxs-lookup"><span data-stu-id="eb20d-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="eb20d-116">Dostawca EntityClient dla programu Entity Framework</span><span class="sxs-lookup"><span data-stu-id="eb20d-116">EntityClient Provider for the Entity Framework</span></span>](../entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="eb20d-117">Instrukcje: Tworzenie parametrów połączenia EntityConnection</span><span class="sxs-lookup"><span data-stu-id="eb20d-117">How to: Build an EntityConnection Connection String</span></span>](../how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="eb20d-118">Instrukcje: Wykonywanie zapytania, które zwraca wyniki PrimitiveType</span><span class="sxs-lookup"><span data-stu-id="eb20d-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="eb20d-119">Instrukcje: Wykonywanie zapytania, które zwraca wyniki StructuralType</span><span class="sxs-lookup"><span data-stu-id="eb20d-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="eb20d-120">Instrukcje: Wykonywanie zapytania, które zwraca wyniki RefType</span><span class="sxs-lookup"><span data-stu-id="eb20d-120">How to: Execute a Query that Returns RefType Results</span></span>](../how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="eb20d-121">Instrukcje: Wykonywanie zapytania, które zwraca typy złożone</span><span class="sxs-lookup"><span data-stu-id="eb20d-121">How to: Execute a Query that Returns Complex Types</span></span>](../how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="eb20d-122">Instrukcje: Wykonywanie zapytania, które zwraca kolekcje zagnieżdżone</span><span class="sxs-lookup"><span data-stu-id="eb20d-122">How to: Execute a Query that Returns Nested Collections</span></span>](../how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="eb20d-123">Instrukcje: Wykonywanie zapytania SQL do sparametryzowanej jednostki przy użyciu EntityCommand</span><span class="sxs-lookup"><span data-stu-id="eb20d-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="eb20d-124">Instrukcje: Wykonywanie zapytania SQL do sparametryzowanej procedury składowanej przy użyciu EntityCommand</span><span class="sxs-lookup"><span data-stu-id="eb20d-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="eb20d-125">Instrukcje: Wykonywanie zapytania polimorficznego</span><span class="sxs-lookup"><span data-stu-id="eb20d-125">How to: Execute a Polymorphic Query</span></span>](../how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="eb20d-126">Instrukcje: Nawigowanie po relacjach za pomocą operatora nawigowania</span><span class="sxs-lookup"><span data-stu-id="eb20d-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="eb20d-127">Używanie Entity SQL z kwerendami obiektów</span><span class="sxs-lookup"><span data-stu-id="eb20d-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="eb20d-128">Jeśli chcesz użyć Entity SQL z kwerendami obiektów, zobacz następujące tematy, aby uzyskać więcej informacji:</span><span class="sxs-lookup"><span data-stu-id="eb20d-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 <span data-ttu-id="eb20d-129">[Instrukcje: wykonywanie zapytania, które zwraca obiekty typu jednostki](/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-129">[How to: Execute a Query that Returns Entity Type Objects](/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))</span></span>  
  
 <span data-ttu-id="eb20d-130">[Instrukcje: wykonywanie zapytania parametrycznego](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-130">[How to: Execute a Parameterized Query](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span></span>  
  
 <span data-ttu-id="eb20d-131">[Instrukcje: nawigowanie po relacjach przy użyciu właściwości nawigacji](/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-131">[How to: Navigate Relationships Using Navigation Properties](/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))</span></span>  
  
 <span data-ttu-id="eb20d-132">[Instrukcje: wywoływanie funkcji zdefiniowanej przez użytkownika](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-132">[How to: Call a User-Defined Function](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))</span></span>  
  
 <span data-ttu-id="eb20d-133">[Instrukcje: filtrowanie danych](/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-133">[How to: Filter Data](/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))</span></span>  
  
 <span data-ttu-id="eb20d-134">[Instrukcje: sortowanie danych](/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-134">[How to: Sort Data](/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))</span></span>  
  
 <span data-ttu-id="eb20d-135">[Instrukcje: grupowanie danych](/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-135">[How to: Group Data](/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))</span></span>  
  
 <span data-ttu-id="eb20d-136">[Instrukcje: agregowanie danych](/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-136">[How to: Aggregate Data](/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))</span></span>  
  
 <span data-ttu-id="eb20d-137">[Instrukcje: wykonywanie zapytania, które zwraca obiekty typu anonimowego](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-137">[How to: Execute a Query that Returns Anonymous Type Objects](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span></span>  
  
 <span data-ttu-id="eb20d-138">[Instrukcje: wykonywanie zapytania, które zwraca kolekcję typów pierwotnych](/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-138">[How to: Execute a Query that Returns a Collection of Primitive Types](/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))</span></span>  
  
 <span data-ttu-id="eb20d-139">[Instrukcje: zapytanie dotyczące obiektów pokrewnych w obiekcie EntityCollection](/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-139">[How to: Query Related Objects in an EntityCollection](/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))</span></span>  
  
 <span data-ttu-id="eb20d-140">[Jak zamówić złożenie dwóch zapytań](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-140">[How to: Order the Union of Two Queries](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))</span></span>  
  
 <span data-ttu-id="eb20d-141">[Instrukcje: Strona za poorednictwem wyników zapytania](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20d-141">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb20d-142">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="eb20d-142">In This Section</span></span>  
 [<span data-ttu-id="eb20d-143">Omówienie jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="eb20d-143">Entity SQL Overview</span></span>](entity-sql-overview.md)  
  
 [<span data-ttu-id="eb20d-144">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="eb20d-144">Entity SQL Reference</span></span>](entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="eb20d-145">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="eb20d-145">See also</span></span>

- [<span data-ttu-id="eb20d-146">Program Entity Framework na platformie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eb20d-146">ADO.NET Entity Framework</span></span>](../index.md)
- [<span data-ttu-id="eb20d-147">Dokumentacja języka</span><span class="sxs-lookup"><span data-stu-id="eb20d-147">Language Reference</span></span>](index.md)
