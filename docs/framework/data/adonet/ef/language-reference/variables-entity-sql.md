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
# <a name="variables-entity-sql"></a>Zmienne (Entity SQL)

## <a name="variable"></a>Zmienna  

 Wyrażenie zmiennej jest odwołaniem do nazwanego wyrażenia zdefiniowanego w bieżącym zakresie. Odwołanie do zmiennej musi być prawidłowym [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identyfikatorem, zgodnie z definicją w [identyfikatorach](identifiers-entity-sql.md).  
  
 W poniższym przykładzie pokazano użycie zmiennej w wyrażeniu. `c`W klauzuli FROM jest definicją zmiennej. Użycie `c` w klauzuli select reprezentuje odwołanie do zmiennej.  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a>Zobacz też

- [Identyfikatory](identifiers-entity-sql.md)
- [Parametry](parameters-entity-sql.md)
- [Omówienie jednostki SQL](entity-sql-overview.md)
