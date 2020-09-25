---
title: Pierwszeństwo operatorów (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: f8aa0f213a24d6431d8910af849571a67fbd9f57
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175645"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="87048-102">Pierwszeństwo operatorów (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="87048-102">Operator Precedence (Entity SQL)</span></span>

<span data-ttu-id="87048-103">Gdy [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytanie ma wiele operatorów, pierwszeństwo operatorów określa kolejność wykonywania operacji.</span><span class="sxs-lookup"><span data-stu-id="87048-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="87048-104">Kolejność wykonywania może znacząco wpłynąć na wynik zapytania.</span><span class="sxs-lookup"><span data-stu-id="87048-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="87048-105">Operatory mają poziomy pierwszeństwa pokazane w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="87048-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="87048-106">Operator o wyższym poziomie jest obliczany przed operatorem o niższym poziomie.</span><span class="sxs-lookup"><span data-stu-id="87048-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="87048-107">Poziom</span><span class="sxs-lookup"><span data-stu-id="87048-107">Level</span></span>|<span data-ttu-id="87048-108">Typ operacji</span><span class="sxs-lookup"><span data-stu-id="87048-108">Operation type</span></span>|<span data-ttu-id="87048-109">Operator</span><span class="sxs-lookup"><span data-stu-id="87048-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="87048-110">1</span><span class="sxs-lookup"><span data-stu-id="87048-110">1</span></span>|<span data-ttu-id="87048-111">Podstawowe</span><span class="sxs-lookup"><span data-stu-id="87048-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="87048-112">2</span><span class="sxs-lookup"><span data-stu-id="87048-112">2</span></span>|<span data-ttu-id="87048-113">Jednoargumentowy</span><span class="sxs-lookup"><span data-stu-id="87048-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="87048-114">3</span><span class="sxs-lookup"><span data-stu-id="87048-114">3</span></span>|<span data-ttu-id="87048-115">Mnożenie</span><span class="sxs-lookup"><span data-stu-id="87048-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="87048-116">4</span><span class="sxs-lookup"><span data-stu-id="87048-116">4</span></span>|<span data-ttu-id="87048-117">Dodawanie</span><span class="sxs-lookup"><span data-stu-id="87048-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="87048-118">5</span><span class="sxs-lookup"><span data-stu-id="87048-118">5</span></span>|<span data-ttu-id="87048-119">Zamawianie</span><span class="sxs-lookup"><span data-stu-id="87048-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="87048-120">6</span><span class="sxs-lookup"><span data-stu-id="87048-120">6</span></span>|<span data-ttu-id="87048-121">Równość</span><span class="sxs-lookup"><span data-stu-id="87048-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="87048-122">7</span><span class="sxs-lookup"><span data-stu-id="87048-122">7</span></span>|<span data-ttu-id="87048-123">AND warunkowe</span><span class="sxs-lookup"><span data-stu-id="87048-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="87048-124">8</span><span class="sxs-lookup"><span data-stu-id="87048-124">8</span></span>|<span data-ttu-id="87048-125">OR warunkowe</span><span class="sxs-lookup"><span data-stu-id="87048-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="87048-126">Gdy dwa operatory w wyrażeniu mają ten sam poziom pierwszeństwa operatora, są oceniane od lewej do prawej na podstawie ich pozycji w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="87048-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="87048-127">Na przykład, `x+y-z` jest oceniane jako `(x+y)-z` .</span><span class="sxs-lookup"><span data-stu-id="87048-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="87048-128">Możesz użyć nawiasów, aby przesłonić zdefiniowane pierwszeństwo operatorów w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="87048-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="87048-129">Wszystkie elementy w nawiasach są oceniane jako pierwsze w celu uzyskania pojedynczego wyniku, zanim ten wynik może być używany przez dowolny operator poza nawiasami.</span><span class="sxs-lookup"><span data-stu-id="87048-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="87048-130">Na przykład `x+y*z` mnoży `y` wartość przez, `z` a następnie dodaje `x` , ale `(x+y)*z` dodaje `x` do, `y` a następnie mnoży wynik przez `z` .</span><span class="sxs-lookup"><span data-stu-id="87048-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87048-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="87048-131">See also</span></span>

- [<span data-ttu-id="87048-132">Omówienie jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="87048-132">Entity SQL Overview</span></span>](entity-sql-overview.md)
