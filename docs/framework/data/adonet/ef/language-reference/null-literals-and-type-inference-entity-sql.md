---
title: Literały o wartości null i wnioskowanie o typie (Entity SQL)
ms.date: 03/30/2017
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
ms.openlocfilehash: 5797c9f55b1a1c89cc27787af6f9ad7bfffc5767
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185070"
---
# <a name="null-literals-and-type-inference-entity-sql"></a><span data-ttu-id="671ad-102">Literały o wartości null i wnioskowanie o typie (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="671ad-102">Null Literals and Type Inference (Entity SQL)</span></span>

<span data-ttu-id="671ad-103">Literały null są zgodne z dowolnym typem w [!INCLUDE[esql](../../../../../../includes/esql-md.md)] systemie typów.</span><span class="sxs-lookup"><span data-stu-id="671ad-103">Null literals are compatible with any type in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] type system.</span></span> <span data-ttu-id="671ad-104">Jednak dla typu literału wartości null, który ma zostać wywnioskowany prawidłowo, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nakłada pewne ograniczenia dotyczące miejsca, w którym można użyć literału o wartości null.</span><span class="sxs-lookup"><span data-stu-id="671ad-104">However, for the type of a null literal to be inferred correctly, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] imposes certain constraints on where a null literal can be used.</span></span>  
  
## <a name="typed-nulls"></a><span data-ttu-id="671ad-105">Wpisane wartości null</span><span class="sxs-lookup"><span data-stu-id="671ad-105">Typed Nulls</span></span>  

 <span data-ttu-id="671ad-106">Wpisane wartości null mogą być używane w dowolnym miejscu.</span><span class="sxs-lookup"><span data-stu-id="671ad-106">Typed nulls can be used anywhere.</span></span> <span data-ttu-id="671ad-107">Wnioskowanie typu nie jest wymagane dla wpisanych wartości null, ponieważ typ jest znany.</span><span class="sxs-lookup"><span data-stu-id="671ad-107">Type inference is not required for typed nulls because the type is known.</span></span> <span data-ttu-id="671ad-108">Na przykład można skonstruować wartość null typu Int16 przy użyciu następującej [!INCLUDE[esql](../../../../../../includes/esql-md.md)] konstrukcji:</span><span class="sxs-lookup"><span data-stu-id="671ad-108">For example, you can construct a null of type Int16 with the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] construct:</span></span>  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a><span data-ttu-id="671ad-109">Bezpłatne, zmiennoprzecinkowe literały o wartości null</span><span class="sxs-lookup"><span data-stu-id="671ad-109">Free-Floating Null Literals</span></span>  

 <span data-ttu-id="671ad-110">W następujących kontekstach można używać wolnych zmiennoprzecinkowych literałów null:</span><span class="sxs-lookup"><span data-stu-id="671ad-110">Free-floating null literals can be used in the following contexts:</span></span>  
  
- <span data-ttu-id="671ad-111">Jako argument do wyrażenia CAST lub TREAT.</span><span class="sxs-lookup"><span data-stu-id="671ad-111">As an argument to a CAST or TREAT expression.</span></span> <span data-ttu-id="671ad-112">Jest to zalecany sposób tworzenia wyrażeniu o wartości null.</span><span class="sxs-lookup"><span data-stu-id="671ad-112">This is the recommended way to produce a typed null expression.</span></span>  
  
- <span data-ttu-id="671ad-113">Jako argument metody lub funkcji.</span><span class="sxs-lookup"><span data-stu-id="671ad-113">As an argument to a method or a function.</span></span> <span data-ttu-id="671ad-114">Obowiązują standardowe reguły przeciążenia.</span><span class="sxs-lookup"><span data-stu-id="671ad-114">Standard overload rules apply.</span></span>  
  
- <span data-ttu-id="671ad-115">Jako jeden z argumentów wyrażenia arytmetycznego, takiego jak +,-lub/.</span><span class="sxs-lookup"><span data-stu-id="671ad-115">As one of the arguments to an arithmetic expression such as +, -, or /.</span></span> <span data-ttu-id="671ad-116">Pozostałe argumenty nie mogą być literałami o wartości null; w przeciwnym razie nie jest możliwe wnioskowanie o typie.</span><span class="sxs-lookup"><span data-stu-id="671ad-116">The other arguments cannot be null literals, otherwise type inference is not possible.</span></span>  
  
- <span data-ttu-id="671ad-117">Jako dowolne argumenty wyrażenia logicznego (i, lub, lub nie).</span><span class="sxs-lookup"><span data-stu-id="671ad-117">As any of the arguments to a logical expression (AND, OR, or NOT).</span></span> <span data-ttu-id="671ad-118">Wszystkie argumenty muszą być typu Boolean.</span><span class="sxs-lookup"><span data-stu-id="671ad-118">All the arguments are known to be of type Boolean.</span></span>  
  
- <span data-ttu-id="671ad-119">Jako że argument ma wartość NULL lub jest wyrażeniem niepustym.</span><span class="sxs-lookup"><span data-stu-id="671ad-119">As the argument to an IS NULL or IS NOT NULL expression.</span></span>  
  
- <span data-ttu-id="671ad-120">Jako jeden lub więcej argumentów wyrażenia LIKE.</span><span class="sxs-lookup"><span data-stu-id="671ad-120">As one or more of the arguments to a LIKE expression.</span></span> <span data-ttu-id="671ad-121">Wszystkie argumenty powinny być ciągami.</span><span class="sxs-lookup"><span data-stu-id="671ad-121">All arguments are expected to be strings.</span></span>  
  
- <span data-ttu-id="671ad-122">Jako jeden lub więcej argumentów konstruktora nazwanego.</span><span class="sxs-lookup"><span data-stu-id="671ad-122">As one or more of the arguments to a named-type constructor.</span></span>  
  
- <span data-ttu-id="671ad-123">Jako jeden lub więcej argumentów konstruktora zestawu wielokrotnego.</span><span class="sxs-lookup"><span data-stu-id="671ad-123">As one or more of the arguments to a multiset constructor.</span></span> <span data-ttu-id="671ad-124">Co najmniej jeden argument w konstruktorze zestawów wielokrotnych musi być wyrażeniem, które nie jest literałem null.</span><span class="sxs-lookup"><span data-stu-id="671ad-124">At least one argument to the multiset constructor must be an expression that is not a null literal.</span></span>  
  
- <span data-ttu-id="671ad-125">Jako co najmniej jedno wyrażenie THEN lub ELSE w wyrażeniu CASE.</span><span class="sxs-lookup"><span data-stu-id="671ad-125">As one or more of the THEN or ELSE expressions in a CASE expression.</span></span> <span data-ttu-id="671ad-126">Co najmniej jedno wyrażenie THEN lub ELSE w wyrażeniu CASE musi być wyrażeniem innym niż literał o wartości null.</span><span class="sxs-lookup"><span data-stu-id="671ad-126">At least one of the THEN or ELSE expressions in the CASE expression must be an expression other than a null literal.</span></span>  
  
 <span data-ttu-id="671ad-127">W innych scenariuszach nie można używać żadnych zmiennoprzecinkowych literałów null.</span><span class="sxs-lookup"><span data-stu-id="671ad-127">Free-floating null literals cannot be used in other scenarios.</span></span> <span data-ttu-id="671ad-128">Na przykład nie mogą być używane jako argumenty konstruktora wiersza.</span><span class="sxs-lookup"><span data-stu-id="671ad-128">For example,  they cannot be used as arguments to a row constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="671ad-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="671ad-129">See also</span></span>

- [<span data-ttu-id="671ad-130">Omówienie jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="671ad-130">Entity SQL Overview</span></span>](entity-sql-overview.md)
