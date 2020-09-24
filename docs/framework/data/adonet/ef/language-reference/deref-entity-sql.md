---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: c0c975ab5cf2761496db6efa1f88f409aa1b1abd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148220"
---
# <a name="deref-entity-sql"></a><span data-ttu-id="598d4-102">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="598d4-102">DEREF (Entity SQL)</span></span>

<span data-ttu-id="598d4-103">Odwołuje się do wartości odniesienia i tworzy wynik tego odwołania.</span><span class="sxs-lookup"><span data-stu-id="598d4-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="598d4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="598d4-104">Syntax</span></span>  
  
```sql  
SELECT DEREF ( o.expression ) FROM Table AS o;
```  
  
## <a name="arguments"></a><span data-ttu-id="598d4-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="598d4-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="598d4-106">Każde prawidłowe wyrażenie zapytania, które zwraca kolekcję.</span><span class="sxs-lookup"><span data-stu-id="598d4-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="598d4-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="598d4-107">Return Value</span></span>  

 <span data-ttu-id="598d4-108">Wartość obiektu, do którego istnieje odwołanie.</span><span class="sxs-lookup"><span data-stu-id="598d4-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="598d4-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="598d4-109">Remarks</span></span>  

 <span data-ttu-id="598d4-110">Operator DEREF odwołuje się do wartości odniesienia i tworzy wynik tego odwołania.</span><span class="sxs-lookup"><span data-stu-id="598d4-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="598d4-111">Na przykład, jeśli `r` jest odwołaniem typu ref \<T> , `Deref(r)` to wyrażenie typu `T` , które zwraca jednostkę, do której odwołuje się `r` .</span><span class="sxs-lookup"><span data-stu-id="598d4-111">For example, if `r` is a reference of type ref\<T>, `Deref(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="598d4-112">Jeśli wartość odwołania ma wartość null lub jest zawieszonego (oznacza to, że obiekt docelowy odwołania nie istnieje), wynik operatora DEREF ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="598d4-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="598d4-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="598d4-113">Example</span></span>  

 <span data-ttu-id="598d4-114">Poniższe [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytanie używa operatora DEREF, aby usunąć odwołanie do wartości odniesienia i utworzyć wynik tego odwołania.</span><span class="sxs-lookup"><span data-stu-id="598d4-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="598d4-115">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="598d4-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="598d4-116">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="598d4-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="598d4-117">Postępuj zgodnie z procedurą w [instrukcje: wykonywanie zapytania, które zwraca wyniki typu pierwotnego](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="598d4-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="598d4-118">Przekaż następujące zapytanie jako argument do metody ExecutePrimitiveTypeQuery:</span><span class="sxs-lookup"><span data-stu-id="598d4-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#DEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="598d4-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="598d4-119">See also</span></span>

- [<span data-ttu-id="598d4-120">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="598d4-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="598d4-121">UMIESZCZONE</span><span class="sxs-lookup"><span data-stu-id="598d4-121">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="598d4-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="598d4-122">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="598d4-123">GŁÓWNYCH</span><span class="sxs-lookup"><span data-stu-id="598d4-123">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="598d4-124">Typy strukturalne dopuszczające wartości Null</span><span class="sxs-lookup"><span data-stu-id="598d4-124">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
