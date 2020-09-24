---
title: Transakcje rozproszone Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: a21134c3283d3d9d8d7660eecaaf74d60ecf6662
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166524"
---
# <a name="oracle-distributed-transactions"></a>Transakcje rozproszone Oracle

<xref:System.Data.OracleClient.OracleConnection>Obiekt jest automatycznie zarejestrowany w istniejącej transakcji rozproszonej, jeśli określa, że transakcja jest aktywna. Automatyczne rejestracje transakcji odbywa się po otwarciu lub pobraniu połączenia z puli połączeń. Funkcję autorejestracji można wyłączyć w istniejących transakcjach, określając  
  
```csharp  
Enlist=false  
```  
  
 jako parametr parametrów połączenia dla <xref:System.Data.OracleClient.OracleConnection> .  
  
## <a name="see-also"></a>Zobacz też

- [Oracle i ADO.NET](oracle-and-adonet.md)
- [Omówienie ADO.NET](ado-net-overview.md)
