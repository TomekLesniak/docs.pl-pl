---
title: Używanie (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: bdab81ed8acae5e757de0a669922dc79d0303ee4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203595"
---
# <a name="using-entity-sql"></a>Używanie (Entity SQL)

Określa przestrzenie nazw używane w wyrażeniu zapytania.  
  
## <a name="syntax"></a>Składnia  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a>Argumenty  

 `alias`  
 Określa krótszy alias do kwalifikowania przestrzeni nazw za pomocą.  
  
 `namespace`  
 Dowolna prawidłowa przestrzeń nazw.  
  
## <a name="example"></a>Przykład  

 Poniższe zapytanie Entity SQL używa operatora USING, aby określić przestrzenie nazw używane w wyrażeniu zapytania. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1. Postępuj zgodnie z procedurą w [instrukcje: wykonywanie zapytania, które zwraca wyniki typu pierwotnego](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Przekaż następujące zapytanie jako argument do `ExecutePrimitiveTypeQuery` metody:  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>Zobacz też

- [Przestrzenie nazw](namespaces-entity-sql.md)
- [Odwołanie do jednostki SQL](entity-sql-reference.md)
