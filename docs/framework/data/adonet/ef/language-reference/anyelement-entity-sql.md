---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: e060956545ca924fa6fedb80b2f53ff312f307a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201203"
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="d7969-102">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d7969-102">ANYELEMENT (Entity SQL)</span></span>

<span data-ttu-id="d7969-103">Wyodrębnia element z kolekcji wielowartościowej.</span><span class="sxs-lookup"><span data-stu-id="d7969-103">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7969-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d7969-104">Syntax</span></span>  
  
```csharp
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="d7969-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="d7969-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="d7969-106">Każde prawidłowe wyrażenie zapytania, które zwraca kolekcję w celu wyodrębnienia elementu z.</span><span class="sxs-lookup"><span data-stu-id="d7969-106">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7969-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="d7969-107">Return Value</span></span>  

 <span data-ttu-id="d7969-108">Pojedynczy element w kolekcji lub dowolny element, jeśli kolekcja zawiera więcej niż jeden; Jeśli kolekcja jest pusta, zwraca `null` .</span><span class="sxs-lookup"><span data-stu-id="d7969-108">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="d7969-109">Jeśli `collection` jest kolekcją typu `Collection<T>` , `ANYELEMENT(collection)` jest prawidłowym wyrażeniem, które zwraca wystąpienie typu `T` .</span><span class="sxs-lookup"><span data-stu-id="d7969-109">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7969-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d7969-110">Remarks</span></span>  

 <span data-ttu-id="d7969-111">ANYELEMENT wyodrębnia dowolny element z kolekcji wielowartościowej.</span><span class="sxs-lookup"><span data-stu-id="d7969-111">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="d7969-112">Na przykład poniższy przykład próbuje wyodrębnić element singleton z zestawu `Customers` .</span><span class="sxs-lookup"><span data-stu-id="d7969-112">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```csharp
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="d7969-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="d7969-113">Example</span></span>  

 <span data-ttu-id="d7969-114">Następujące [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytanie używa operatora AnyElement do wyodrębnienia elementu z kolekcji wielowartościowej.</span><span class="sxs-lookup"><span data-stu-id="d7969-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="d7969-115">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d7969-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d7969-116">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="d7969-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d7969-117">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d7969-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d7969-118">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="d7969-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="d7969-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d7969-119">See also</span></span>

- [<span data-ttu-id="d7969-120">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="d7969-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="d7969-121">Typy strukturalne dopuszczające wartości Null</span><span class="sxs-lookup"><span data-stu-id="d7969-121">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
