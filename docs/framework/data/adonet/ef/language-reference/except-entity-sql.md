---
title: Z wyjątkiem (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: 6797f8038a83533b5a6bd41ad402daec7abdc7de
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148060"
---
# <a name="except-entity-sql"></a><span data-ttu-id="bb585-102">Z wyjątkiem (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bb585-102">EXCEPT (Entity SQL)</span></span>

<span data-ttu-id="bb585-103">Zwraca kolekcję wszystkich odrębnych wartości z wyrażenia zapytania na lewo od operandu EXCEPT, które nie są zwracane z wyrażenia zapytania z prawej strony operandu EXCEPT.</span><span class="sxs-lookup"><span data-stu-id="bb585-103">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="bb585-104">Wszystkie wyrażenia muszą być tego samego typu lub według wspólnego typu podstawowego lub pochodnego `expression` .</span><span class="sxs-lookup"><span data-stu-id="bb585-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb585-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="bb585-105">Syntax</span></span>  
  
```sql  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="bb585-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="bb585-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="bb585-107">Każde prawidłowe wyrażenie zapytania, które zwraca kolekcję do porównania z kolekcją zwróconą z innego wyrażenia zapytania.</span><span class="sxs-lookup"><span data-stu-id="bb585-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb585-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="bb585-108">Return Value</span></span>  

 <span data-ttu-id="bb585-109">Kolekcja tego samego typu lub typowego typu podstawowego lub pochodnego jako `expression` .</span><span class="sxs-lookup"><span data-stu-id="bb585-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb585-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bb585-110">Remarks</span></span>  

 <span data-ttu-id="bb585-111">Oprócz tego jest jednym z [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatorów zestawu.</span><span class="sxs-lookup"><span data-stu-id="bb585-111">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="bb585-112">Wszystkie [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Operatory zestawów są oceniane od lewej do prawej.</span><span class="sxs-lookup"><span data-stu-id="bb585-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="bb585-113">W poniższej tabeli przedstawiono pierwszeństwo [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatorów zestawu.</span><span class="sxs-lookup"><span data-stu-id="bb585-113">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="bb585-114">Pierwszeństwo</span><span class="sxs-lookup"><span data-stu-id="bb585-114">Precedence</span></span>|<span data-ttu-id="bb585-115">Operatory</span><span class="sxs-lookup"><span data-stu-id="bb585-115">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="bb585-116">Najwyższy</span><span class="sxs-lookup"><span data-stu-id="bb585-116">Highest</span></span>|<span data-ttu-id="bb585-117">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="bb585-117">INTERSECT</span></span>|  
||<span data-ttu-id="bb585-118">UNION</span><span class="sxs-lookup"><span data-stu-id="bb585-118">UNION</span></span><br /><br /> <span data-ttu-id="bb585-119">UNION WSZYSTKO</span><span class="sxs-lookup"><span data-stu-id="bb585-119">UNION ALL</span></span>|  
||<span data-ttu-id="bb585-120">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="bb585-120">EXCEPT</span></span>|  
|<span data-ttu-id="bb585-121">Okreolon</span><span class="sxs-lookup"><span data-stu-id="bb585-121">Lowest</span></span>|<span data-ttu-id="bb585-122">EXISTS</span><span class="sxs-lookup"><span data-stu-id="bb585-122">EXISTS</span></span><br /><br /> <span data-ttu-id="bb585-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="bb585-123">OVERLAPS</span></span><br /><br /> <span data-ttu-id="bb585-124">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="bb585-124">FLATTEN</span></span><br /><br /> <span data-ttu-id="bb585-125">SET</span><span class="sxs-lookup"><span data-stu-id="bb585-125">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bb585-126">Przykład</span><span class="sxs-lookup"><span data-stu-id="bb585-126">Example</span></span>  

 <span data-ttu-id="bb585-127">Poniższe zapytanie Entity SQL używa operatora EXCEPT do zwrócenia kolekcji wszelkich odrębnych wartości z dwóch wyrażeń zapytań.</span><span class="sxs-lookup"><span data-stu-id="bb585-127">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="bb585-128">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="bb585-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bb585-129">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="bb585-129">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="bb585-130">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="bb585-130">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="bb585-131">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="bb585-131">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXCEPT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#except)]  
  
## <a name="see-also"></a><span data-ttu-id="bb585-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bb585-132">See also</span></span>

- [<span data-ttu-id="bb585-133">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="bb585-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
