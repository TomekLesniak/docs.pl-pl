---
title: Pobieranie obiektów z pamięci podręcznej tożsamości
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96c13903-ccb6-4a0e-ab6a-8ca955ca314d
ms.openlocfilehash: 457e11ddad16ca3be55f53f03c480b0e464ab38f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200397"
---
# <a name="retrieving-objects-from-the-identity-cache"></a><span data-ttu-id="8b58d-102">Pobieranie obiektów z pamięci podręcznej tożsamości</span><span class="sxs-lookup"><span data-stu-id="8b58d-102">Retrieving Objects from the Identity Cache</span></span>

<span data-ttu-id="8b58d-103">W tym temacie opisano typy zapytań LINQ to SQL, które zwracają obiekt z pamięci podręcznej tożsamości, która jest zarządzana przez program <xref:System.Data.Linq.DataContext> .</span><span class="sxs-lookup"><span data-stu-id="8b58d-103">This topic describes the types of LINQ to SQL queries that return an object from the identity cache that is managed by the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="8b58d-104">W LINQ to SQL jednym ze sposobów <xref:System.Data.Linq.DataContext> zarządzania obiektami zarządza tożsamość obiektów w pamięci podręcznej tożsamości, gdy są wykonywane zapytania.</span><span class="sxs-lookup"><span data-stu-id="8b58d-104">In LINQ to SQL, one of the ways in which the <xref:System.Data.Linq.DataContext> manages objects is by logging object identities in an identity cache as queries are executed.</span></span> <span data-ttu-id="8b58d-105">W niektórych przypadkach LINQ to SQL spróbuje pobrać obiekt z pamięci podręcznej tożsamości przed wykonaniem zapytania w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="8b58d-105">In some cases, LINQ to SQL will attempt to retrieve an object from the identity cache before executing a query in the database.</span></span>  
  
 <span data-ttu-id="8b58d-106">Ogólnie rzecz biorąc, aby kwerenda LINQ to SQL zwracała obiekt z pamięci podręcznej tożsamości, zapytanie musi być oparte na kluczu podstawowym obiektu i musi zwrócić pojedynczy obiekt.</span><span class="sxs-lookup"><span data-stu-id="8b58d-106">In general, for a LINQ to SQL query to return an object from the identity cache, the query must be based on the primary key of an object and must return a single object.</span></span> <span data-ttu-id="8b58d-107">W szczególności zapytanie musi znajdować się w jednym z formularzy ogólnych przedstawionych poniżej.</span><span class="sxs-lookup"><span data-stu-id="8b58d-107">In particular, the query must be in one of the general forms shown below.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b58d-108">Wstępnie skompilowane zapytania nie będą zwracać obiektów z pamięci podręcznej tożsamości.</span><span class="sxs-lookup"><span data-stu-id="8b58d-108">Pre-compiled queries will not return objects from the identity cache.</span></span> <span data-ttu-id="8b58d-109">Aby uzyskać więcej informacji na temat wstępnie skompilowanych zapytań, zobacz <xref:System.Data.Linq.CompiledQuery> i [instrukcje: przechowywanie i ponowne używanie zapytań](how-to-store-and-reuse-queries.md).</span><span class="sxs-lookup"><span data-stu-id="8b58d-109">For more information about pre-compiled queries, see <xref:System.Data.Linq.CompiledQuery> and [How to: Store and Reuse Queries](how-to-store-and-reuse-queries.md).</span></span>  
  
 <span data-ttu-id="8b58d-110">Zapytanie musi znajdować się w jednym z następujących formularzy ogólnych, aby pobrać obiekt z pamięci podręcznej tożsamości:</span><span class="sxs-lookup"><span data-stu-id="8b58d-110">A query must be in one of the following general forms to retrieve an object from the identity cache:</span></span>  
  
- <span data-ttu-id="8b58d-111"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`</span><span class="sxs-lookup"><span data-stu-id="8b58d-111"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`</span></span>  
  
- <span data-ttu-id="8b58d-112"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`</span><span class="sxs-lookup"><span data-stu-id="8b58d-112"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`</span></span>  
  
 <span data-ttu-id="8b58d-113">W tych ogólnych formularzach `Function1` , `Function2` i `predicate` są zdefiniowane w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="8b58d-113">In these general forms, `Function1`, `Function2`, and `predicate` are defined as follows.</span></span>  
  
 <span data-ttu-id="8b58d-114">`Function1` może to być dowolny z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="8b58d-114">`Function1` can be any of the following:</span></span>  
  
- <xref:System.Linq.Queryable.Where%2A>  
  
- <xref:System.Linq.Queryable.First%2A>  
  
- <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
- <xref:System.Linq.Queryable.Single%2A>  
  
- <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 <span data-ttu-id="8b58d-115">`Function2` może to być dowolny z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="8b58d-115">`Function2` can be any of the following:</span></span>  
  
- <xref:System.Linq.Queryable.First%2A>  
  
- <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
- <xref:System.Linq.Queryable.Single%2A>  
  
- <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 <span data-ttu-id="8b58d-116">`predicate` musi być wyrażeniem, w którym Właściwość klucz podstawowy obiektu ma ustawioną wartość stałą.</span><span class="sxs-lookup"><span data-stu-id="8b58d-116">`predicate` must be an expression in which the object's primary key property is set to a constant value.</span></span> <span data-ttu-id="8b58d-117">Jeśli obiekt ma klucz podstawowy zdefiniowany przez więcej niż jedną właściwość, Każda właściwość klucza podstawowego musi być ustawiona na wartość stałą.</span><span class="sxs-lookup"><span data-stu-id="8b58d-117">If an object has a primary key defined by more than one property, each primary key property must be set to a constant value.</span></span> <span data-ttu-id="8b58d-118">Poniżej przedstawiono przykłady formularza, które `predicate` należy wykonać:</span><span class="sxs-lookup"><span data-stu-id="8b58d-118">The following are examples of the form `predicate` must take:</span></span>  
  
- `c => c.PK == constant_value`  
  
- `c => c.PK1 == constant_value1 && c=> c.PK2 == constant_value2`  
  
## <a name="example"></a><span data-ttu-id="8b58d-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="8b58d-119">Example</span></span>  

 <span data-ttu-id="8b58d-120">Poniższy kod zawiera przykłady typów zapytań LINQ to SQL, które pobierają obiekt z pamięci podręcznej tożsamości.</span><span class="sxs-lookup"><span data-stu-id="8b58d-120">The following code provides examples of the types of LINQ to SQL queries that retrieve an object from the identity cache.</span></span>  
  
 [!code-csharp[L2S_QueryCache#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/l2s_querycache/cs/program.cs#1)]
 [!code-vb[L2S_QueryCache#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/l2s_querycache/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8b58d-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8b58d-121">See also</span></span>

- [<span data-ttu-id="8b58d-122">Pojęcia dotyczące zapytań</span><span class="sxs-lookup"><span data-stu-id="8b58d-122">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="8b58d-123">Tożsamość obiektu</span><span class="sxs-lookup"><span data-stu-id="8b58d-123">Object Identity</span></span>](object-identity.md)
- [<span data-ttu-id="8b58d-124">Informacje uzupełniające</span><span class="sxs-lookup"><span data-stu-id="8b58d-124">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="8b58d-125">Tożsamość obiektu</span><span class="sxs-lookup"><span data-stu-id="8b58d-125">Object Identity</span></span>](object-identity.md)
