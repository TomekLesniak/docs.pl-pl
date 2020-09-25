---
title: Zmienne (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: af6d586a22f14a04bfc7ec339d0aa8e9ba7c66c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181001"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="f1472-102">Zmienne (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f1472-102">Variables (Entity SQL)</span></span>

## <a name="variable"></a><span data-ttu-id="f1472-103">Zmienna</span><span class="sxs-lookup"><span data-stu-id="f1472-103">Variable</span></span>  

 <span data-ttu-id="f1472-104">Wyrażenie zmiennej jest odwołaniem do nazwanego wyrażenia zdefiniowanego w bieżącym zakresie.</span><span class="sxs-lookup"><span data-stu-id="f1472-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="f1472-105">Odwołanie do zmiennej musi być prawidłowym [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identyfikatorem, zgodnie z definicją w [identyfikatorach](identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f1472-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="f1472-106">W poniższym przykładzie pokazano użycie zmiennej w wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="f1472-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="f1472-107">`c`W klauzuli FROM jest definicją zmiennej.</span><span class="sxs-lookup"><span data-stu-id="f1472-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="f1472-108">Użycie `c` w klauzuli select reprezentuje odwołanie do zmiennej.</span><span class="sxs-lookup"><span data-stu-id="f1472-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1472-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f1472-109">See also</span></span>

- [<span data-ttu-id="f1472-110">Identyfikatory</span><span class="sxs-lookup"><span data-stu-id="f1472-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="f1472-111">Parametry</span><span class="sxs-lookup"><span data-stu-id="f1472-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="f1472-112">Omówienie jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="f1472-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
