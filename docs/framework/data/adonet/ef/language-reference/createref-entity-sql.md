---
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: c2a57116f56abf4db3caabcfe3acd0d8afbcf4eb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201060"
---
# <a name="createref-entity-sql"></a><span data-ttu-id="8b83f-102">CREATEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8b83f-102">CREATEREF (Entity SQL)</span></span>

<span data-ttu-id="8b83f-103">W obiekcie EntitySet są przywoływane odwołania do jednostki.</span><span class="sxs-lookup"><span data-stu-id="8b83f-103">Fabricates references to an entity in an entityset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b83f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8b83f-104">Syntax</span></span>  
  
```sql  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="8b83f-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="8b83f-105">Arguments</span></span>  

 `entityset_identifier`  
 <span data-ttu-id="8b83f-106">Identyfikator obiektu EntitySet, a nie literału ciągu.</span><span class="sxs-lookup"><span data-stu-id="8b83f-106">The entityset identifier, not a string literal.</span></span>  
  
 `row_typed_expression`  
 <span data-ttu-id="8b83f-107">Wyrażenie z określonym wierszem, które odnosi się do właściwości klucza typu jednostki.</span><span class="sxs-lookup"><span data-stu-id="8b83f-107">A row-typed expression that corresponds to the key properties of the entity type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b83f-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8b83f-108">Remarks</span></span>  

 <span data-ttu-id="8b83f-109">`row_typed_expression` muszą być strukturalnie równoważne z typem klucza dla jednostki.</span><span class="sxs-lookup"><span data-stu-id="8b83f-109">`row_typed_expression` must be structurally equivalent to the key type for the entity.</span></span> <span data-ttu-id="8b83f-110">Oznacza to, że musi mieć taką samą liczbę i typy pól w tej samej kolejności co klucze jednostek.</span><span class="sxs-lookup"><span data-stu-id="8b83f-110">That is, it must have the same number and types of fields in the same order as the entity keys.</span></span>  
  
 <span data-ttu-id="8b83f-111">W poniższym przykładzie zamówienia i BadOrders są zarówno obiektem EntitySet typu Order, jak i przyjmuje się, że są one właściwością Single Key kolejności.</span><span class="sxs-lookup"><span data-stu-id="8b83f-111">In the example below, Orders and BadOrders are both entitysets of type Order, and Id is assumed to be the single key property of Order.</span></span> <span data-ttu-id="8b83f-112">W przykładzie pokazano, jak możemy utworzyć odwołanie do jednostki w BadOrders.</span><span class="sxs-lookup"><span data-stu-id="8b83f-112">The example illustrates how we may produce a reference to an entity in BadOrders.</span></span> <span data-ttu-id="8b83f-113">Należy zauważyć, że odwołanie może być zawieszonego.</span><span class="sxs-lookup"><span data-stu-id="8b83f-113">Note that the reference may be dangling.</span></span>  <span data-ttu-id="8b83f-114">Oznacza to, że odwołanie może nie identyfikować określonej jednostki.</span><span class="sxs-lookup"><span data-stu-id="8b83f-114">That is, the reference may not actually identify a specific entity.</span></span> <span data-ttu-id="8b83f-115">W takich przypadkach `DEREF` operacja na tym odwołaniu zwraca wartość null.</span><span class="sxs-lookup"><span data-stu-id="8b83f-115">In those cases, a `DEREF` operation on that reference returns a null.</span></span>  
  
```sql  
SELECT CreateRef(LOB.BadOrders, row(o.Id))
FROM LOB.Orders AS o
```  
  
## <a name="example"></a><span data-ttu-id="8b83f-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="8b83f-116">Example</span></span>  

 <span data-ttu-id="8b83f-117">Poniższe zapytanie Entity SQL używa operatora CREATEREF do tworzenia odwołań do jednostki w zestawie jednostek.</span><span class="sxs-lookup"><span data-stu-id="8b83f-117">The following Entity SQL query uses the CREATEREF operator to fabricate references to an entity in an entity set.</span></span> <span data-ttu-id="8b83f-118">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8b83f-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8b83f-119">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="8b83f-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="8b83f-120">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8b83f-120">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="8b83f-121">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="8b83f-121">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CREATEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#createref)]  
  
## <a name="see-also"></a><span data-ttu-id="8b83f-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8b83f-122">See also</span></span>

- [<span data-ttu-id="8b83f-123">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="8b83f-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="8b83f-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="8b83f-124">DEREF</span></span>](deref-entity-sql.md)
- [<span data-ttu-id="8b83f-125">GŁÓWNYCH</span><span class="sxs-lookup"><span data-stu-id="8b83f-125">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="8b83f-126">UMIESZCZONE</span><span class="sxs-lookup"><span data-stu-id="8b83f-126">REF</span></span>](ref-entity-sql.md)
