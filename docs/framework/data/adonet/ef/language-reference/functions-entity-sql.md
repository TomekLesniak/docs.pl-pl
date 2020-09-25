---
title: Funkcje (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: bef959ae6a835b5d1d696162528a8f904c59e8e5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201073"
---
# <a name="functions-entity-sql"></a>Funkcje (Entity SQL)

Entity SQL obsługuje funkcje zdefiniowane przez użytkownika, funkcje kanoniczne i funkcje specyficzne dla dostawcy. Funkcje zdefiniowane przez użytkownika są określone w modelu koncepcyjnym lub wbudowane w zapytaniu. Aby uzyskać więcej informacji, zobacz [funkcje zdefiniowane przez użytkownika](user-defined-functions-entity-sql.md).  
  
 Funkcje kanoniczne są wstępnie zdefiniowane w Entity Framework i powinny być obsługiwane przez dostawców danych. Entity SQL polecenia zakończą się niepowodzeniem, jeśli użytkownik wywoła funkcję, która nie jest obsługiwana przez dostawcę. W związku z tym funkcje kanoniczne są zwykle zalecane w stosunku do funkcji specyficznych dla magazynu, które znajdują się w przestrzeni nazw specyficznej dla dostawcy. Aby uzyskać więcej informacji, zobacz [funkcje kanoniczne](canonical-functions.md).  
  
 Dostawca zarządzany przez klienta programu Microsoft SQL Server udostępnia zestaw funkcji specyficznych dla dostawcy. Aby uzyskać więcej informacji, zobacz temat [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Funkcje zdefiniowane przez użytkownika](user-defined-functions-entity-sql.md)  
  
 [Rozpoznanie przeciążenia funkcji](function-overload-resolution-entity-sql.md)  
  
 [Funkcje agregujące](../aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>Zobacz też

- [Omówienie jednostki SQL](entity-sql-overview.md)
