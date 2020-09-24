---
title: Istnieje (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: f08b3ea60a985e56e05e4686cd531f94e0bd4e18
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166771"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="d2a65-102">Istnieje (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d2a65-102">EXISTS (Entity SQL)</span></span>

<span data-ttu-id="d2a65-103">Określa, czy kolekcja jest pusta.</span><span class="sxs-lookup"><span data-stu-id="d2a65-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2a65-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d2a65-104">Syntax</span></span>  
  
```sql  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="d2a65-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="d2a65-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="d2a65-106">Dowolne prawidłowe wyrażenie zwracające kolekcję.</span><span class="sxs-lookup"><span data-stu-id="d2a65-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="d2a65-107">NOT</span><span class="sxs-lookup"><span data-stu-id="d2a65-107">NOT</span></span>  
 <span data-ttu-id="d2a65-108">Określa, że wynik istnieje jest negacją.</span><span class="sxs-lookup"><span data-stu-id="d2a65-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2a65-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="d2a65-109">Return Value</span></span>  

 <span data-ttu-id="d2a65-110">`true` Jeśli kolekcja nie jest pusta; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="d2a65-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2a65-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d2a65-111">Remarks</span></span>  

 <span data-ttu-id="d2a65-112">ISTNIEJE, jest jednym z [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatorów zestawu.</span><span class="sxs-lookup"><span data-stu-id="d2a65-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="d2a65-113">Wszystkie [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Operatory zestawów są oceniane od lewej do prawej.</span><span class="sxs-lookup"><span data-stu-id="d2a65-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="d2a65-114">Aby uzyskać informacje o pierwszeństwie dla [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatorów zestawu, zobacz [except](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d2a65-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2a65-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="d2a65-115">Example</span></span>  

 <span data-ttu-id="d2a65-116">Poniższe zapytanie Entity SQL używa operatora EXISTS, aby określić, czy kolekcja jest pusta.</span><span class="sxs-lookup"><span data-stu-id="d2a65-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="d2a65-117">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d2a65-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d2a65-118">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="d2a65-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d2a65-119">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d2a65-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d2a65-120">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="d2a65-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXISTS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="d2a65-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d2a65-121">See also</span></span>

- [<span data-ttu-id="d2a65-122">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="d2a65-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
