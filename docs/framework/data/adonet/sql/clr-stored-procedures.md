---
title: Procedury składowane CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: aa14c96ed226ac80a9613d3e229f35dbf5085f3b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173617"
---
# <a name="clr-stored-procedures"></a>Procedury składowane CLR

Procedury składowane są procedurami, których nie można używać w wyrażeniach skalarnych. Mogą zwracać wyniki tabelaryczne i komunikaty do klienta, wywoływać instrukcje języka definicji danych (DDL) i języka manipulowania danymi oraz zwracać parametry wyjściowe.  
  
> [!NOTE]
> Firma Microsoft Visual Basic nie obsługuje parametrów wyjściowych w taki sam sposób, jak w programie Microsoft Visual C#. Należy określić, aby przekazać parametr przez odwołanie i zastosować \<Out()> atrybut do reprezentowania parametru wyjściowego, jak w następujących przypadkach:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
Aby uzyskać szczegółowe informacje, zobacz wersję [dokumentacji SQL Server](/sql) dla używanej wersji SQL Server.
  
 **Dokumentacja SQL Server**

1. [Procedury składowane CLR](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))  
  
## <a name="see-also"></a>Zobacz też

- [Tworzenie obiektów SQL Server 2005 w kodzie zarządzanym](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [Omówienie ADO.NET](../ado-net-overview.md)
