---
title: = (Equals) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 31299670d9f47ed7672b980a3415b8d214463b8e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148090"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="b5c24-102">= (Equals) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b5c24-102">= (Equals) (Entity SQL)</span></span>

<span data-ttu-id="b5c24-103">Porównuje równość dwóch wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="b5c24-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5c24-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b5c24-104">Syntax</span></span>  
  
```sql  
expression = expression  
-- or
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b5c24-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="b5c24-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="b5c24-106">Dowolne prawidłowe wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="b5c24-106">Any valid expression.</span></span> <span data-ttu-id="b5c24-107">Oba wyrażenia muszą mieć niejawnie wymienialne typy danych.</span><span class="sxs-lookup"><span data-stu-id="b5c24-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b5c24-108">Typy wyników</span><span class="sxs-lookup"><span data-stu-id="b5c24-108">Result Types</span></span>  

 <span data-ttu-id="b5c24-109">`true` Jeśli wyrażenie po lewej stronie jest równe wyrażeniu z prawej strony; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="b5c24-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5c24-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b5c24-110">Remarks</span></span>  

 <span data-ttu-id="b5c24-111">Operator = = jest równoważny z =.</span><span class="sxs-lookup"><span data-stu-id="b5c24-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5c24-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="b5c24-112">Example</span></span>  

 <span data-ttu-id="b5c24-113">Poniższy Entity SQL Query używa operatora porównania, aby porównać równość dwóch wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="b5c24-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="b5c24-114">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b5c24-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b5c24-115">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="b5c24-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b5c24-116">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b5c24-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b5c24-117">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="b5c24-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="b5c24-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b5c24-118">See also</span></span>

- [<span data-ttu-id="b5c24-119">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="b5c24-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
