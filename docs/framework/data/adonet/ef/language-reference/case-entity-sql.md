---
title: PRZYPADEK (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: 65efedd36401db402a32748afaebff0f2af9f2a7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185226"
---
# <a name="case-entity-sql"></a><span data-ttu-id="8e357-102">PRZYPADEK (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8e357-102">CASE (Entity SQL)</span></span>

<span data-ttu-id="8e357-103">Oblicza zestaw `Boolean` wyrażeń, aby określić wynik.</span><span class="sxs-lookup"><span data-stu-id="8e357-103">Evaluates a set of `Boolean` expressions to determine the result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e357-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8e357-104">Syntax</span></span>  
  
```csharp  
CASE  
     WHEN Boolean_expression THEN result_expression
    [ ...n ]
     [
    ELSE else_result_expression
     ]
END  
```  
  
## <a name="arguments"></a><span data-ttu-id="8e357-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="8e357-105">Arguments</span></span>  

 `n`  
 <span data-ttu-id="8e357-106">Jest symbolem zastępczym, który wskazuje, że `Boolean_expression` `result_expression` można użyć wielu klauzule then.</span><span class="sxs-lookup"><span data-stu-id="8e357-106">Is a placeholder that indicates that multiple WHEN `Boolean_expression` THEN `result_expression` clauses can be used.</span></span>  
  
 <span data-ttu-id="8e357-107">NASTĘPNIE `result_expression`</span><span class="sxs-lookup"><span data-stu-id="8e357-107">THEN `result_expression`</span></span>  
 <span data-ttu-id="8e357-108">Jest wyrażeniem zwracanym podczas `Boolean_expression` obliczania `true` .</span><span class="sxs-lookup"><span data-stu-id="8e357-108">Is the expression returned when `Boolean_expression` evaluates to `true`.</span></span> <span data-ttu-id="8e357-109">`result expression` jest dowolnym prawidłowym wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="8e357-109">`result expression` is any valid expression.</span></span>  
  
 <span data-ttu-id="8e357-110">PRZEJMI `else_result_expression`</span><span class="sxs-lookup"><span data-stu-id="8e357-110">ELSE `else_result_expression`</span></span>  
 <span data-ttu-id="8e357-111">Jest wyrażeniem zwracanym, jeśli nie zostanie obliczona żadna operacja porównania `true` .</span><span class="sxs-lookup"><span data-stu-id="8e357-111">Is the expression returned if no comparison operation evaluates to `true`.</span></span> <span data-ttu-id="8e357-112">Jeśli ten argument zostanie pominięty i żadna operacja porównania nie zostanie obliczona do `true` , przypadek zwraca wartość null.</span><span class="sxs-lookup"><span data-stu-id="8e357-112">If this argument is omitted and no comparison operation evaluates to `true`, CASE returns null.</span></span> <span data-ttu-id="8e357-113">`else_result_expression` jest dowolnym prawidłowym wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="8e357-113">`else_result_expression` is any valid expression.</span></span> <span data-ttu-id="8e357-114">Typy danych `else_result_expression` i any `result_expression` muszą być takie same lub muszą być niejawną konwersją.</span><span class="sxs-lookup"><span data-stu-id="8e357-114">The data types of `else_result_expression` and any `result_expression` must be the same or must be an implicit conversion.</span></span>  
  
 <span data-ttu-id="8e357-115">CZASIE `Boolean_expression`</span><span class="sxs-lookup"><span data-stu-id="8e357-115">WHEN `Boolean_expression`</span></span>  
 <span data-ttu-id="8e357-116">Jest `Boolean` wyrażeniem obliczanym, gdy jest używany przeszukiwany format wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="8e357-116">Is the `Boolean` expression evaluated when the searched CASE format is used.</span></span> <span data-ttu-id="8e357-117">`Boolean_expression` jest dowolnym prawidłowym `Boolean` wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="8e357-117">`Boolean_expression` is any valid `Boolean` expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e357-118">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="8e357-118">Return Value</span></span>  

 <span data-ttu-id="8e357-119">Zwraca typ najwyższego pierwszeństwa z zestawu typów w `result_expression` i opcjonalne `else_result_expression` .</span><span class="sxs-lookup"><span data-stu-id="8e357-119">Returns the highest precedence type from the set of types in the `result_expression` and the optional `else_result_expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e357-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8e357-120">Remarks</span></span>  

 <span data-ttu-id="8e357-121">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]Wyrażenie CASE przypomina wyrażenie CASE języka Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="8e357-121">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case expression resembles the Transact-SQL case expression.</span></span> <span data-ttu-id="8e357-122">Wyrażenie CASE służy do tworzenia serii testów warunkowych, aby określić, które wyrażenie zwróci odpowiedni wynik.</span><span class="sxs-lookup"><span data-stu-id="8e357-122">You use the case expression to make a series of conditional tests to determine which expression will yield the appropriate result.</span></span> <span data-ttu-id="8e357-123">Ta forma wyrażenia case ma zastosowanie do serii co najmniej jednego `Boolean` wyrażenia, aby określić poprawne wyrażenie wyniku.</span><span class="sxs-lookup"><span data-stu-id="8e357-123">This form of the case expression applies to a series of one or more `Boolean` expressions to determine the correct resulting expression.</span></span>  
  
 <span data-ttu-id="8e357-124">Funkcja CASE oblicza `Boolean_expression` dla każdej klauzuli when w określonej kolejności i zwraca `result_expression` pierwszy `Boolean_expression` , który jest obliczany `true` .</span><span class="sxs-lookup"><span data-stu-id="8e357-124">The CASE function evaluates `Boolean_expression` for each WHEN clause in the order specified, and returns `result_expression` of the first `Boolean_expression` that evaluates to `true`.</span></span> <span data-ttu-id="8e357-125">Pozostałe wyrażenia nie są oceniane.</span><span class="sxs-lookup"><span data-stu-id="8e357-125">The remaining expressions are not evaluated.</span></span> <span data-ttu-id="8e357-126">Jeśli żaden z nich nie jest `Boolean_expression` wynikiem `true` , aparat bazy danych zwraca wartość, `else_result_expression` Jeśli określono klauzulę else lub wartość null, jeśli nie określono klauzuli else.</span><span class="sxs-lookup"><span data-stu-id="8e357-126">If no `Boolean_expression` evaluates to `true`, the Database Engine returns the `else_result_expression` if an ELSE clause is specified, or a null value if no ELSE clause is specified.</span></span>  
  
 <span data-ttu-id="8e357-127">Instrukcja CASE nie może zwracać zestawu wielokrotnego.</span><span class="sxs-lookup"><span data-stu-id="8e357-127">A CASE statement cannot return a multiset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e357-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="8e357-128">Example</span></span>  

 <span data-ttu-id="8e357-129">Poniższe zapytanie Entity SQL używa wyrażenia CASE do obliczenia zestawu `Boolean` wyrażeń w celu określenia wyniku.</span><span class="sxs-lookup"><span data-stu-id="8e357-129">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions in order to determine the result.</span></span> <span data-ttu-id="8e357-130">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8e357-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8e357-131">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="8e357-131">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="8e357-132">Postępuj zgodnie z procedurą w [instrukcje: wykonywanie zapytania, które zwraca wyniki typu pierwotnego](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8e357-132">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="8e357-133">Przekaż następujące zapytanie jako argument do `ExecutePrimitiveTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="8e357-133">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="8e357-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8e357-134">See also</span></span>

- [<span data-ttu-id="8e357-135">NASTĘPNIE</span><span class="sxs-lookup"><span data-stu-id="8e357-135">THEN</span></span>](then-entity-sql.md)
- [<span data-ttu-id="8e357-136">ZAZNACZENIA</span><span class="sxs-lookup"><span data-stu-id="8e357-136">SELECT</span></span>](select-entity-sql.md)
- [<span data-ttu-id="8e357-137">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="8e357-137">Entity SQL Reference</span></span>](entity-sql-reference.md)
