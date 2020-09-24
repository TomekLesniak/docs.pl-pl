---
title: Parametry (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 759452902461e1a460b69774bb33f92bbd532ed0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177521"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="5b98e-102">Parametry (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5b98e-102">Parameters (Entity SQL)</span></span>

<span data-ttu-id="5b98e-103">Parametry są zmiennymi, które są zdefiniowane poza [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , zwykle za pomocą powiązania interfejsu API, który jest używany przez język hosta.</span><span class="sxs-lookup"><span data-stu-id="5b98e-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="5b98e-104">Każdy parametr ma nazwę i typ.</span><span class="sxs-lookup"><span data-stu-id="5b98e-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="5b98e-105">Nazwy parametrów są zdefiniowane w wyrażeniach zapytania z symbolem at (@) jako prefiksem.</span><span class="sxs-lookup"><span data-stu-id="5b98e-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="5b98e-106">Pozwala to odróżnić je od nazw właściwości lub innych nazw zdefiniowanych w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="5b98e-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="5b98e-107">Interfejs API powiązania języka hosta udostępnia interfejsy API dla parametrów powiązań.</span><span class="sxs-lookup"><span data-stu-id="5b98e-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b98e-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="5b98e-108">Example</span></span>  
  
```sql  
SELECT c
      FROM LOB.Customers AS c
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b98e-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5b98e-109">See also</span></span>

- [<span data-ttu-id="5b98e-110">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="5b98e-110">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="5b98e-111">Omówienie jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="5b98e-111">Entity SQL Overview</span></span>](entity-sql-overview.md)
