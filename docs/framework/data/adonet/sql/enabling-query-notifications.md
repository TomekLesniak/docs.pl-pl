---
title: Włączanie powiadomień o zapytaniach
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: 4e9b3a2e1f176a9d01e983bc469cc4032fa5d730
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156176"
---
# <a name="enabling-query-notifications"></a>Włączanie powiadomień o zapytaniach

Aplikacje korzystające z powiadomień o zapytaniach mają wspólny zestaw wymagań. Źródło danych musi być poprawnie skonfigurowane do obsługi powiadomień zapytań SQL, a użytkownik musi mieć odpowiednie uprawnienia po stronie klienta i serwera.  
  
 Aby używać powiadomień o zapytaniach, musisz:  
  
- Włącz powiadomienia o zapytaniach dla bazy danych.  
  
- Upewnij się, że identyfikator użytkownika użyty do nawiązania połączenia z bazą danych ma wymagane uprawnienia.  
  
- Użyj <xref:System.Data.SqlClient.SqlCommand> obiektu, aby wykonać prawidłową instrukcję SELECT ze skojarzonym obiektem powiadomienia — albo <xref:System.Data.SqlClient.SqlDependency> <xref:System.Data.Sql.SqlNotificationRequest> .  
  
- Podaj kod, aby przetworzyć powiadomienie, jeśli monitorowane zmiany.  
  
## <a name="query-notifications-requirements"></a>Wymagania dotyczące powiadomień o zapytaniach  

 Powiadomienia o zapytaniach są obsługiwane tylko w przypadku instrukcji SELECT, które spełniają określone wymagania. Poniższa tabela zawiera linki do dokumentacji Service Broker i powiadomień o zapytaniach w temacie SQL Server Books Online.  
  
 **Dokumentacja SQL Server**  
  
- [Tworzenie zapytania dla powiadomienia](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Zagadnienia dotyczące zabezpieczeń Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))  
  
- [Zabezpieczenia i ochrona (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))  
  
- [Zagadnienia dotyczące zabezpieczeń dla usług powiadomień](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))  
  
- [Uprawnienia do powiadomień o zapytaniach](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))  
  
- [Zagadnienia międzynarodowe dotyczące Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))  
  
- [Zagadnienia dotyczące projektowania rozwiązań (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))  
  
- [Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Przewodnik dewelopera (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a>Włączanie powiadomień o zapytaniach w celu uruchomienia przykładowego kodu  

 Aby włączyć Service Broker w bazie danych **AdventureWorks** przy użyciu SQL Server Management Studio, wykonaj następującą instrukcję Transact-SQL:  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 Aby przykłady powiadomień o zapytaniach działały prawidłowo, należy wykonać następujące instrukcje języka Transact-SQL na serwerze bazy danych.  
  
```sql
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a>Uprawnienia do wysyłania zapytań  

 Użytkownicy, którzy uruchamiają polecenia żądające powiadomienia, muszą mieć na serwerze uprawnienia do bazy danych powiadomień o zapytaniach dotyczących subskrypcji.  
  
 Kod po stronie klienta, który działa w ramach częściowej sytuacji zaufania, wymaga <xref:System.Data.SqlClient.SqlClientPermission> .  
  
 Poniższy kod tworzy <xref:System.Data.SqlClient.SqlClientPermission> obiekt, ustawiając polecenie <xref:System.Security.Permissions.PermissionState> na <xref:System.Security.Permissions.PermissionState.Unrestricted> . <xref:System.Security.CodeAccessPermission.Demand%2A>Wymusi <xref:System.Security.SecurityException> w czasie wykonywania, jeśli wszyscy wywołujący znajdujący się wyżej w stosie wywołań nie uzyskali uprawnienia.  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a>Wybieranie obiektu powiadomienia  

 Interfejs API powiadomień o zapytaniach zawiera dwa obiekty do przetwarzania powiadomień: <xref:System.Data.SqlClient.SqlDependency> i <xref:System.Data.Sql.SqlNotificationRequest> . Ogólnie rzecz biorąc większość aplikacji non-ASP.NET powinna używać <xref:System.Data.SqlClient.SqlDependency> obiektu. Aplikacje ASP.NET powinny korzystać z wyższego poziomu <xref:System.Web.Caching.SqlCacheDependency> , który zawija <xref:System.Data.SqlClient.SqlDependency> i udostępnia strukturę służącą do administrowania obiektami powiadomień i pamięci podręcznej.  
  
### <a name="using-sqldependency"></a>Korzystanie z elementu SqlDependency  

 Aby korzystać z programu <xref:System.Data.SqlClient.SqlDependency> , Service Broker musi być włączona dla używanej bazy danych SQL Server, a użytkownicy muszą mieć uprawnienia do odbierania powiadomień. Obiekty Service Broker, takie jak Kolejka powiadomień, są wstępnie zdefiniowane.  
  
 Ponadto program <xref:System.Data.SqlClient.SqlDependency> automatycznie uruchamia wątek roboczy, aby przetwarzać powiadomienia w momencie ich opublikowania w kolejce. analizuje również komunikat Service Broker, uwidaczniając informacje jako dane argumentu zdarzenia. <xref:System.Data.SqlClient.SqlDependency> musi być inicjowany przez wywołanie `Start` metody w celu ustanowienia zależności z bazą danych. Jest to metoda statyczna, która musi być wywoływana tylko raz podczas inicjowania aplikacji dla wszystkich wymaganych połączeń z bazą danych. `Stop`Metoda powinna być wywoływana podczas kończenia aplikacji dla każdego połączenia zależności, które zostało wykonane.  
  
### <a name="using-sqlnotificationrequest"></a>Korzystanie z SqlNotificationRequest  

 Z drugiej strony, <xref:System.Data.Sql.SqlNotificationRequest> wymaga zaimplementowania całej infrastruktury nasłuchiwania. Ponadto należy zdefiniować wszystkie pomocnicze obiekty Service Broker, takie jak kolejka, usługa i typy komunikatów obsługiwane przez kolejkę. To podejście ręczne jest przydatne, jeśli aplikacja wymaga specjalnych komunikatów powiadomień lub zachowań powiadomień lub jeśli aplikacja jest częścią aplikacji o większej Service Broker.  
  
## <a name="see-also"></a>Zobacz też

- [Powiadomienia zapytań w programie SQL Server](query-notifications-in-sql-server.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
