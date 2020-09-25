---
title: '! = (Nie równa się) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: bebe85072f5a2cf6a133b88c6d3f5c97299aa63f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191778"
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="8af9b-102">! = (Nie równa się) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8af9b-102">!= (Not Equal To) (Entity SQL)</span></span>

<span data-ttu-id="8af9b-103">Porównuje dwa wyrażenia, aby określić, czy lewe wyrażenie nie jest równe wyrażeniu z prawej strony.</span><span class="sxs-lookup"><span data-stu-id="8af9b-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="8af9b-104">Operator! = (nie równa się) jest funkcjonalnie równoważny operatorowi <> .</span><span class="sxs-lookup"><span data-stu-id="8af9b-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af9b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="8af9b-105">Syntax</span></span>  
  
```sql  
expression != expression  
-- or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="8af9b-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="8af9b-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="8af9b-107">Dowolne prawidłowe wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="8af9b-107">Any valid expression.</span></span> <span data-ttu-id="8af9b-108">Oba wyrażenia muszą mieć niejawnie wymienialne typy danych.</span><span class="sxs-lookup"><span data-stu-id="8af9b-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8af9b-109">Typy wyników</span><span class="sxs-lookup"><span data-stu-id="8af9b-109">Result Types</span></span>  

 <span data-ttu-id="8af9b-110">`true` Jeśli wyrażenie po lewej stronie nie jest równe wyrażeniu z prawej strony; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="8af9b-110">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8af9b-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="8af9b-111">Example</span></span>  

 <span data-ttu-id="8af9b-112">Poniższe zapytanie Entity SQL używa operatora! = do porównywania dwóch wyrażeń, aby określić, czy lewe wyrażenie nie jest równe wyrażeniu z prawej strony.</span><span class="sxs-lookup"><span data-stu-id="8af9b-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="8af9b-113">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8af9b-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8af9b-114">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="8af9b-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="8af9b-115">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8af9b-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="8af9b-116">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="8af9b-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="8af9b-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8af9b-117">See also</span></span>

- [<span data-ttu-id="8af9b-118">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="8af9b-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
