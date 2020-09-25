---
title: MIĘDZY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 17e3fe97942b34232640b0326eca2c5729e86989
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201177"
---
# <a name="between-entity-sql"></a><span data-ttu-id="2a3aa-102">MIĘDZY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2a3aa-102">BETWEEN (Entity SQL)</span></span>

<span data-ttu-id="2a3aa-103">Określa, czy wynikiem wyrażenia jest wartość w określonym zakresie.</span><span class="sxs-lookup"><span data-stu-id="2a3aa-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="2a3aa-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]Wyrażenie Between ma takie same funkcje jak wyrażenie Transact-SQL między wyrażeniami.</span><span class="sxs-lookup"><span data-stu-id="2a3aa-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a3aa-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="2a3aa-105">Syntax</span></span>  
  
```csharp  
expression [ NOT ] BETWEEN begin_expression AND end_expression
```  
  
## <a name="arguments"></a><span data-ttu-id="2a3aa-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="2a3aa-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="2a3aa-107">Dowolne prawidłowe wyrażenie do przetestowania w zakresie zdefiniowanym przez `begin_expression` i `end_expression` .</span><span class="sxs-lookup"><span data-stu-id="2a3aa-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="2a3aa-108">`expression` musi być tego samego typu co `begin_expression` i `end_expression` .</span><span class="sxs-lookup"><span data-stu-id="2a3aa-108">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="2a3aa-109">Dowolne prawidłowe wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="2a3aa-109">Any valid expression.</span></span> <span data-ttu-id="2a3aa-110">`begin_expression` musi być tego samego typu co `expression` i `end_expression` .</span><span class="sxs-lookup"><span data-stu-id="2a3aa-110">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="2a3aa-111">`begin_expression` wartość nie może być mniejsza niż `end_expression` , w przeciwnym razie zwracana jest Negacja.</span><span class="sxs-lookup"><span data-stu-id="2a3aa-111">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="2a3aa-112">Dowolne prawidłowe wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="2a3aa-112">Any valid expression.</span></span> <span data-ttu-id="2a3aa-113">`end_expression` musi być tego samego typu co `expression` i `begin_expression` .</span><span class="sxs-lookup"><span data-stu-id="2a3aa-113">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="2a3aa-114">NOT</span><span class="sxs-lookup"><span data-stu-id="2a3aa-114">NOT</span></span>  
 <span data-ttu-id="2a3aa-115">Określa, że wynik między jest negacją.</span><span class="sxs-lookup"><span data-stu-id="2a3aa-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="2a3aa-116">AND</span><span class="sxs-lookup"><span data-stu-id="2a3aa-116">AND</span></span>  
 <span data-ttu-id="2a3aa-117">Działa jako symbol zastępczy, który wskazuje, że `expression` powinien znajdować się w zakresie wskazanym przez `begin_expression` i `end_expression` .</span><span class="sxs-lookup"><span data-stu-id="2a3aa-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a3aa-118">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="2a3aa-118">Return Value</span></span>  

 <span data-ttu-id="2a3aa-119">`true` Jeśli `expression` jest między zakresem wskazanym przez `begin_expression` i `end_expression` ; w przeciwnym razie, `false` .</span><span class="sxs-lookup"><span data-stu-id="2a3aa-119">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="2a3aa-120">`null` zostanie zwrócona, jeśli `expression` jest `null` lub jeśli `begin_expression` lub `end_expression` jest `null` .</span><span class="sxs-lookup"><span data-stu-id="2a3aa-120">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a3aa-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2a3aa-121">Remarks</span></span>  

 <span data-ttu-id="2a3aa-122">Aby określić zakres wyłącznych, użyj operatorów większe niż (>) i mniejsze niż (<), a nie między.</span><span class="sxs-lookup"><span data-stu-id="2a3aa-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a3aa-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="2a3aa-123">Example</span></span>  

 <span data-ttu-id="2a3aa-124">Poniższe zapytanie Entity SQL używa operatora, aby określić, czy wynikiem wyrażenia jest wartość w określonym zakresie.</span><span class="sxs-lookup"><span data-stu-id="2a3aa-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="2a3aa-125">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2a3aa-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2a3aa-126">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="2a3aa-126">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2a3aa-127">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2a3aa-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="2a3aa-128">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="2a3aa-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="2a3aa-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2a3aa-129">See also</span></span>

- [<span data-ttu-id="2a3aa-130">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="2a3aa-130">Entity SQL Reference</span></span>](entity-sql-reference.md)
