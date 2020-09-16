---
title: Procedury składowane CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: 736020695ae40a8884057ddee8aac8abe6e8c1fd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554198"
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
  
## <a name="see-also"></a>Zobacz także

- [Tworzenie obiektów SQL Server 2005 w kodzie zarządzanym](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [Omówienie ADO.NET](../ado-net-overview.md)
