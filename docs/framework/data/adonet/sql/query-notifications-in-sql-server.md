---
title: Powiadomienia zapytań w programie SQL Server
description: Informacje na temat używania powiadomień o zapytaniach w celu powiadomienia aplikacji o zmianie danych w bazie danych SQL Server, na przykład w celu odświeżenia wyświetlania aplikacji.
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 8001f75d7e278a965b6e8e00e4b9af7b770a8bb5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183094"
---
# <a name="query-notifications-in-sql-server"></a>Powiadomienia zapytań w programie SQL Server

W oparciu o infrastrukturę Service Broker powiadomienia o zapytaniach umożliwiają powiadamianie aplikacji o zmianach danych. Ta funkcja jest szczególnie przydatna w przypadku aplikacji, które udostępniają pamięć podręczną informacji z bazy danych, takiej jak aplikacja sieci Web, i należy powiadamiać o zmianach danych źródłowych.  
  
 Istnieją trzy sposoby implementacji powiadomień o zapytaniach przy użyciu ADO.NET:  
  
1. Implementacja niskiego poziomu jest dostarczana przez `SqlNotificationRequest` klasę, która udostępnia funkcje po stronie serwera, co umożliwia wykonywanie poleceń z żądaniem powiadomienia.  
  
2. Implementacja wysokiego poziomu jest dostarczana przez `SqlDependency` klasę, która jest klasą, która zapewnia abstrakcję wysokiego poziomu funkcji powiadomień między aplikacją źródłową i SQL Server, co pozwala na używanie zależności do wykrywania zmian na serwerze. W większości przypadków jest to najprostszy i najbardziej efektywny sposób, aby wykorzystać możliwości SQL Server powiadomień przez zarządzane aplikacje klienckie przy użyciu Dostawca danych .NET Framework dla SQL Server.  
  
3. Ponadto aplikacje sieci Web skompilowane przy użyciu ASP.NET 2,0 lub nowszej mogą używać `SqlCacheDependency` klas pomocnika.  
  
 Powiadomienia o zapytaniach są używane w przypadku aplikacji, które wymagają odświeżenia wyświetlania lub buforowania w odpowiedzi na zmiany danych bazowych. Microsoft SQL Server umożliwia aplikacjom .NET Framework wysyłanie polecenia do SQL Server i żądanie powiadomienia, jeśli wykonanie tego samego polecenia spowoduje wygenerowanie zestawów wynikowych innych niż pobrane początkowo. Powiadomienia generowane na serwerze są wysyłane przez kolejki, aby można je było przetworzyć później.  
  
 Możesz skonfigurować powiadomienia dla instrukcji SELECT i EXECUTE. Przy użyciu instrukcji EXECUTE SQL Server rejestruje powiadomienie dla wykonywanego polecenia, a nie samą instrukcję EXECUTE. Polecenie musi spełniać wymagania i ograniczenia dotyczące instrukcji SELECT. Gdy polecenie rejestrujące powiadomienie zawiera więcej niż jedną instrukcję, aparat bazy danych tworzy powiadomienie dla każdej instrukcji w partii.  
  
 Jeśli tworzysz aplikację, w której potrzebujesz niezawodnych powiadomień podrzędnych w przypadku zmiany danych, zapoznaj się z sekcją **Planowanie wydajnej strategii powiadomień o zapytaniach** i **alternatywy do wysyłania zapytań do powiadomień** w artykule [Planowanie powiadomień](/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) . Aby uzyskać więcej informacji na temat powiadomień o zapytaniach i SQL Server Service Broker, zobacz następujące linki do artykułów w dokumentacji SQL Server.  
  
 **Dokumentacja SQL Server**  
  
- [Korzystanie z powiadomień o zapytaniach](/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))  
  
- [Tworzenie zapytania dla powiadomienia](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Programowanie (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))  
  
- [Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Przewodnik dewelopera (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Włączanie powiadomień o zapytaniach](enabling-query-notifications.md)  
 W tym artykule omówiono sposób używania powiadomień o zapytaniach, w tym wymagania dotyczące włączania i korzystania z nich.  
  
 [Element SqlDependency w aplikacji ASP.NET](sqldependency-in-an-aspnet-app.md)  
 Pokazuje, jak używać powiadomień o zapytaniach z aplikacji ASP.NET.  
  
 [Wykrywanie zmian za pomocą elementu SqlDependency](detecting-changes-with-sqldependency.md)  
 Pokazuje, w jaki sposób wykryć, kiedy wyniki zapytania będą inne niż te, które zostały pierwotnie odebrane.  
  
 [Wykonywanie polecenia SqlCommand za pomocą SqlNotificationRequest](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 Demonstruje Konfigurowanie <xref:System.Data.SqlClient.SqlCommand> obiektu do pracy z powiadomieniem o zapytaniach.  
  
## <a name="reference"></a>Tematy pomocy  

 <xref:System.Data.Sql.SqlNotificationRequest>  
 Opisuje <xref:System.Data.Sql.SqlNotificationRequest> klasę i wszystkich jej członków.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 Opisuje <xref:System.Data.SqlClient.SqlDependency> klasę i wszystkich jej członków.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 Opisuje <xref:System.Web.Caching.SqlCacheDependency> klasę i wszystkich jej członków.  
  
## <a name="see-also"></a>Zobacz też

- [SQL Server i ADO.NET](index.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
