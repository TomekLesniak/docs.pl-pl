---
title: NASTĘPNIE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: f038f242bc0873df3d72700aa05fca2f76f777ff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161675"
---
# <a name="then-entity-sql"></a><span data-ttu-id="0495e-102">NASTĘPNIE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0495e-102">THEN (Entity SQL)</span></span>

<span data-ttu-id="0495e-103">Wynik klauzuli WHEN, gdy jest obliczany `true` .</span><span class="sxs-lookup"><span data-stu-id="0495e-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0495e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0495e-104">Syntax</span></span>  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="0495e-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="0495e-105">Arguments</span></span>  

 `when_expression`  
 <span data-ttu-id="0495e-106">Dowolne prawidłowe wyrażenie logiczne.</span><span class="sxs-lookup"><span data-stu-id="0495e-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="0495e-107">Każde prawidłowe wyrażenie zapytania, które zwraca kolekcję.</span><span class="sxs-lookup"><span data-stu-id="0495e-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0495e-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0495e-108">Remarks</span></span>  

 <span data-ttu-id="0495e-109">Jeśli `when_expression` zwraca wartość `true` , wynik jest odpowiedni `then-expression` .</span><span class="sxs-lookup"><span data-stu-id="0495e-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="0495e-110">Jeśli żaden z warunków nie zostanie spełniony, `else-expression` zostanie obliczona wartość.</span><span class="sxs-lookup"><span data-stu-id="0495e-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="0495e-111">Jeśli jednak nie ma `else-expression` , wynik ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="0495e-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="0495e-112">Aby zapoznać się z przykładem, zobacz [wielkość liter](case-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0495e-112">For an example, see [CASE](case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0495e-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="0495e-113">Example</span></span>  

 <span data-ttu-id="0495e-114">Poniższe zapytanie Entity SQL używa wyrażenia CASE do obliczenia zestawu `Boolean` wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="0495e-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="0495e-115">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0495e-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0495e-116">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="0495e-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="0495e-117">Postępuj zgodnie z procedurą w [instrukcje: wykonywanie zapytania, które zwraca wyniki typu pierwotnego](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="0495e-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="0495e-118">Przekaż następujące zapytanie jako argument do `ExecutePrimitiveTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="0495e-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="0495e-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0495e-119">See also</span></span>

- [<span data-ttu-id="0495e-120">SPRAW</span><span class="sxs-lookup"><span data-stu-id="0495e-120">CASE</span></span>](case-entity-sql.md)
- [<span data-ttu-id="0495e-121">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="0495e-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
