---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 56ae576ac60d1716d86fbbb797882bf96e99813f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202243"
---
# <a name="ref-entity-sql"></a><span data-ttu-id="ce62d-102">REF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ce62d-102">REF (Entity SQL)</span></span>

<span data-ttu-id="ce62d-103">Zwraca odwołanie do wystąpienia jednostki.</span><span class="sxs-lookup"><span data-stu-id="ce62d-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce62d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ce62d-104">Syntax</span></span>  
  
```sql  
REF( expression )
```  
  
## <a name="arguments"></a><span data-ttu-id="ce62d-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="ce62d-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="ce62d-106">Dowolne prawidłowe wyrażenie zwracające wystąpienie typu jednostki.</span><span class="sxs-lookup"><span data-stu-id="ce62d-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce62d-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="ce62d-107">Return Value</span></span>  

 <span data-ttu-id="ce62d-108">Odwołanie do określonego wystąpienia jednostki.</span><span class="sxs-lookup"><span data-stu-id="ce62d-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce62d-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ce62d-109">Remarks</span></span>  

 <span data-ttu-id="ce62d-110">Odwołanie do jednostki składa się z klucza jednostki i nazwy zestawu jednostek.</span><span class="sxs-lookup"><span data-stu-id="ce62d-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="ce62d-111">Ponieważ różne zestawy jednostek mogą opierać się na tym samym typie jednostki, określony klucz jednostki może pojawić się w wielu zestawach jednostek.</span><span class="sxs-lookup"><span data-stu-id="ce62d-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="ce62d-112">Odwołanie do jednostki jest jednak zawsze unikatowe.</span><span class="sxs-lookup"><span data-stu-id="ce62d-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="ce62d-113">Jeśli wyrażenie danych wejściowych reprezentuje obiekt utrwalony, odwołanie do tej jednostki zostanie zwrócone.</span><span class="sxs-lookup"><span data-stu-id="ce62d-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="ce62d-114">Jeśli wyrażenie wejściowe nie jest utrwaloną jednostką, zostanie zwrócone odwołanie o wartości null.</span><span class="sxs-lookup"><span data-stu-id="ce62d-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="ce62d-115">Jeśli operator wyodrębniania właściwości (.) jest używany w celu uzyskania dostępu do właściwości jednostki, odwołanie zostanie automatycznie wywoływać.</span><span class="sxs-lookup"><span data-stu-id="ce62d-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce62d-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="ce62d-116">Example</span></span>  

 <span data-ttu-id="ce62d-117">Poniższe zapytanie Entity SQL używa operatora REF do zwrócenia odwołania dla argumentu jednostki wejściowej.</span><span class="sxs-lookup"><span data-stu-id="ce62d-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="ce62d-118">To samo zapytanie odwołuje się do odwołania, ponieważ używamy operacji wyodrębniania właściwości (.) w celu uzyskania dostępu do właściwości jednostki produktu.</span><span class="sxs-lookup"><span data-stu-id="ce62d-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="ce62d-119">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ce62d-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ce62d-120">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="ce62d-120">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ce62d-121">Postępuj zgodnie z procedurą w [instrukcje: wykonywanie zapytania, które zwraca wyniki typu pierwotnego](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ce62d-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="ce62d-122">Przekaż następujące zapytanie jako argument do `ExecutePrimitiveTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="ce62d-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#REF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="ce62d-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ce62d-123">See also</span></span>

- [<span data-ttu-id="ce62d-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="ce62d-124">DEREF</span></span>](deref-entity-sql.md)
- [<span data-ttu-id="ce62d-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="ce62d-125">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="ce62d-126">GŁÓWNYCH</span><span class="sxs-lookup"><span data-stu-id="ce62d-126">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="ce62d-127">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="ce62d-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="ce62d-128">Definicje typu</span><span class="sxs-lookup"><span data-stu-id="ce62d-128">Type Definitions</span></span>](type-definitions-entity-sql.md)
