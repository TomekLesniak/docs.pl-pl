---
title: '&amp;&amp; LUB (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 86ff43f8ed20c5696d15e21284394c3cb63200e3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198044"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="7dda9-102">&amp;&amp; LUB (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7dda9-102">&amp;&amp; (AND) (Entity SQL)</span></span>

<span data-ttu-id="7dda9-103">Zwraca `true` Jeśli oba wyrażenia są `true` ; w przeciwnym razie `false` lub `NULL` .</span><span class="sxs-lookup"><span data-stu-id="7dda9-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dda9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7dda9-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```

<span data-ttu-id="7dda9-105">lub</span><span class="sxs-lookup"><span data-stu-id="7dda9-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="7dda9-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="7dda9-106">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="7dda9-107">Dowolne prawidłowe wyrażenie zwracające wartość logiczną.</span><span class="sxs-lookup"><span data-stu-id="7dda9-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dda9-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7dda9-108">Remarks</span></span>  

 <span data-ttu-id="7dda9-109">Podwójne znaki "i" (&&) mają takie same funkcje jak operator i.</span><span class="sxs-lookup"><span data-stu-id="7dda9-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="7dda9-110">W poniższej tabeli przedstawiono możliwe wartości wejściowe i typy zwracane.</span><span class="sxs-lookup"><span data-stu-id="7dda9-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="7dda9-111">TRUE</span><span class="sxs-lookup"><span data-stu-id="7dda9-111">TRUE</span></span>|<span data-ttu-id="7dda9-112">FALSE</span><span class="sxs-lookup"><span data-stu-id="7dda9-112">FALSE</span></span>|<span data-ttu-id="7dda9-113">NULL</span><span class="sxs-lookup"><span data-stu-id="7dda9-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="7dda9-114">Fałsz</span><span class="sxs-lookup"><span data-stu-id="7dda9-114">FALSE</span></span>|<span data-ttu-id="7dda9-115">Fałsz</span><span class="sxs-lookup"><span data-stu-id="7dda9-115">FALSE</span></span>|<span data-ttu-id="7dda9-116">Fałsz</span><span class="sxs-lookup"><span data-stu-id="7dda9-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="7dda9-117">NULL</span><span class="sxs-lookup"><span data-stu-id="7dda9-117">NULL</span></span>|<span data-ttu-id="7dda9-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="7dda9-118">FALSE</span></span>|<span data-ttu-id="7dda9-119">NULL</span><span class="sxs-lookup"><span data-stu-id="7dda9-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7dda9-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="7dda9-120">Example</span></span>  

 <span data-ttu-id="7dda9-121">W poniższym zapytaniu Entity SQL pokazano, jak używać operatora i.</span><span class="sxs-lookup"><span data-stu-id="7dda9-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="7dda9-122">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7dda9-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7dda9-123">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="7dda9-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="7dda9-124">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="7dda9-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="7dda9-125">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="7dda9-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="7dda9-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7dda9-126">See also</span></span>

- [<span data-ttu-id="7dda9-127">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="7dda9-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
