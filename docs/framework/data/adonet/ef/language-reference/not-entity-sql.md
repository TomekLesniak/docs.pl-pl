---
title: '! NIEMOŻLIWE (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 0eb9be9ed4cbce45a51d15eea68e9fb1a26f0107
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191843"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="44a8d-103">!</span><span class="sxs-lookup"><span data-stu-id="44a8d-103">!</span></span> <span data-ttu-id="44a8d-104">NIEMOŻLIWE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="44a8d-104">(NOT) (Entity SQL)</span></span>

<span data-ttu-id="44a8d-105">Wyklucza `Boolean` wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="44a8d-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44a8d-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="44a8d-106">Syntax</span></span>  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a><span data-ttu-id="44a8d-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="44a8d-107">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="44a8d-108">Dowolne prawidłowe wyrażenie zwracające wartość logiczną.</span><span class="sxs-lookup"><span data-stu-id="44a8d-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44a8d-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="44a8d-109">Remarks</span></span>  

 <span data-ttu-id="44a8d-110">Wykrzyknik (!) ma takie same funkcje jak operator NOT.</span><span class="sxs-lookup"><span data-stu-id="44a8d-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44a8d-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="44a8d-111">Example</span></span>  

 <span data-ttu-id="44a8d-112">Poniższe zapytanie Entity SQL używa operatora NOT, aby Negacja `Boolean` wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="44a8d-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="44a8d-113">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="44a8d-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="44a8d-114">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="44a8d-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="44a8d-115">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="44a8d-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="44a8d-116">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="44a8d-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a><span data-ttu-id="44a8d-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="44a8d-117">See also</span></span>

- [<span data-ttu-id="44a8d-118">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="44a8d-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
