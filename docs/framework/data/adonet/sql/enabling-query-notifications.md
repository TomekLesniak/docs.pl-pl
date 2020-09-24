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
# <a name="enabling-query-notifications"></a><span data-ttu-id="57a0e-102">Włączanie powiadomień o zapytaniach</span><span class="sxs-lookup"><span data-stu-id="57a0e-102">Enabling Query Notifications</span></span>

<span data-ttu-id="57a0e-103">Aplikacje korzystające z powiadomień o zapytaniach mają wspólny zestaw wymagań.</span><span class="sxs-lookup"><span data-stu-id="57a0e-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="57a0e-104">Źródło danych musi być poprawnie skonfigurowane do obsługi powiadomień zapytań SQL, a użytkownik musi mieć odpowiednie uprawnienia po stronie klienta i serwera.</span><span class="sxs-lookup"><span data-stu-id="57a0e-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="57a0e-105">Aby używać powiadomień o zapytaniach, musisz:</span><span class="sxs-lookup"><span data-stu-id="57a0e-105">To use query notifications you must:</span></span>  
  
- <span data-ttu-id="57a0e-106">Włącz powiadomienia o zapytaniach dla bazy danych.</span><span class="sxs-lookup"><span data-stu-id="57a0e-106">Enable query notifications for your database.</span></span>  
  
- <span data-ttu-id="57a0e-107">Upewnij się, że identyfikator użytkownika użyty do nawiązania połączenia z bazą danych ma wymagane uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="57a0e-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
- <span data-ttu-id="57a0e-108">Użyj <xref:System.Data.SqlClient.SqlCommand> obiektu, aby wykonać prawidłową instrukcję SELECT ze skojarzonym obiektem powiadomienia — albo <xref:System.Data.SqlClient.SqlDependency> <xref:System.Data.Sql.SqlNotificationRequest> .</span><span class="sxs-lookup"><span data-stu-id="57a0e-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
- <span data-ttu-id="57a0e-109">Podaj kod, aby przetworzyć powiadomienie, jeśli monitorowane zmiany.</span><span class="sxs-lookup"><span data-stu-id="57a0e-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="57a0e-110">Wymagania dotyczące powiadomień o zapytaniach</span><span class="sxs-lookup"><span data-stu-id="57a0e-110">Query Notifications Requirements</span></span>  

 <span data-ttu-id="57a0e-111">Powiadomienia o zapytaniach są obsługiwane tylko w przypadku instrukcji SELECT, które spełniają określone wymagania.</span><span class="sxs-lookup"><span data-stu-id="57a0e-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="57a0e-112">Poniższa tabela zawiera linki do dokumentacji Service Broker i powiadomień o zapytaniach w temacie SQL Server Books Online.</span><span class="sxs-lookup"><span data-stu-id="57a0e-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="57a0e-113">**Dokumentacja SQL Server**</span><span class="sxs-lookup"><span data-stu-id="57a0e-113">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="57a0e-114">[Tworzenie zapytania dla powiadomienia](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="57a0e-114">[Creating a Query for Notification](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="57a0e-115">[Zagadnienia dotyczące zabezpieczeń Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="57a0e-115">[Security Considerations for Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span></span>  
  
- <span data-ttu-id="57a0e-116">[Zabezpieczenia i ochrona (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="57a0e-116">[Security and Protection (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span></span>  
  
- <span data-ttu-id="57a0e-117">[Zagadnienia dotyczące zabezpieczeń dla usług powiadomień](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="57a0e-117">[Security Considerations for Notifications Services](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span></span>  
  
- <span data-ttu-id="57a0e-118">[Uprawnienia do powiadomień o zapytaniach](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="57a0e-118">[Query Notification Permissions](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span></span>  
  
- <span data-ttu-id="57a0e-119">[Zagadnienia międzynarodowe dotyczące Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="57a0e-119">[International Considerations for Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span></span>  
  
- <span data-ttu-id="57a0e-120">[Zagadnienia dotyczące projektowania rozwiązań (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="57a0e-120">[Solution Design Considerations (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span></span>  
  
- <span data-ttu-id="57a0e-121">[Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="57a0e-121">[Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="57a0e-122">[Przewodnik dewelopera (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="57a0e-122">[Developer's Guide (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="57a0e-123">Włączanie powiadomień o zapytaniach w celu uruchomienia przykładowego kodu</span><span class="sxs-lookup"><span data-stu-id="57a0e-123">Enabling Query Notifications to Run Sample Code</span></span>  

 <span data-ttu-id="57a0e-124">Aby włączyć Service Broker w bazie danych **AdventureWorks** przy użyciu SQL Server Management Studio, wykonaj następującą instrukcję Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="57a0e-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="57a0e-125">Aby przykłady powiadomień o zapytaniach działały prawidłowo, należy wykonać następujące instrukcje języka Transact-SQL na serwerze bazy danych.</span><span class="sxs-lookup"><span data-stu-id="57a0e-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```sql
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="57a0e-126">Uprawnienia do wysyłania zapytań</span><span class="sxs-lookup"><span data-stu-id="57a0e-126">Query Notifications Permissions</span></span>  

 <span data-ttu-id="57a0e-127">Użytkownicy, którzy uruchamiają polecenia żądające powiadomienia, muszą mieć na serwerze uprawnienia do bazy danych powiadomień o zapytaniach dotyczących subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="57a0e-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="57a0e-128">Kod po stronie klienta, który działa w ramach częściowej sytuacji zaufania, wymaga <xref:System.Data.SqlClient.SqlClientPermission> .</span><span class="sxs-lookup"><span data-stu-id="57a0e-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="57a0e-129">Poniższy kod tworzy <xref:System.Data.SqlClient.SqlClientPermission> obiekt, ustawiając polecenie <xref:System.Security.Permissions.PermissionState> na <xref:System.Security.Permissions.PermissionState.Unrestricted> .</span><span class="sxs-lookup"><span data-stu-id="57a0e-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="57a0e-130"><xref:System.Security.CodeAccessPermission.Demand%2A>Wymusi <xref:System.Security.SecurityException> w czasie wykonywania, jeśli wszyscy wywołujący znajdujący się wyżej w stosie wywołań nie uzyskali uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="57a0e-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="57a0e-131">Wybieranie obiektu powiadomienia</span><span class="sxs-lookup"><span data-stu-id="57a0e-131">Choosing a Notification Object</span></span>  

 <span data-ttu-id="57a0e-132">Interfejs API powiadomień o zapytaniach zawiera dwa obiekty do przetwarzania powiadomień: <xref:System.Data.SqlClient.SqlDependency> i <xref:System.Data.Sql.SqlNotificationRequest> .</span><span class="sxs-lookup"><span data-stu-id="57a0e-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="57a0e-133">Ogólnie rzecz biorąc większość aplikacji non-ASP.NET powinna używać <xref:System.Data.SqlClient.SqlDependency> obiektu.</span><span class="sxs-lookup"><span data-stu-id="57a0e-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="57a0e-134">Aplikacje ASP.NET powinny korzystać z wyższego poziomu <xref:System.Web.Caching.SqlCacheDependency> , który zawija <xref:System.Data.SqlClient.SqlDependency> i udostępnia strukturę służącą do administrowania obiektami powiadomień i pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="57a0e-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="57a0e-135">Korzystanie z elementu SqlDependency</span><span class="sxs-lookup"><span data-stu-id="57a0e-135">Using SqlDependency</span></span>  

 <span data-ttu-id="57a0e-136">Aby korzystać z programu <xref:System.Data.SqlClient.SqlDependency> , Service Broker musi być włączona dla używanej bazy danych SQL Server, a użytkownicy muszą mieć uprawnienia do odbierania powiadomień.</span><span class="sxs-lookup"><span data-stu-id="57a0e-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="57a0e-137">Obiekty Service Broker, takie jak Kolejka powiadomień, są wstępnie zdefiniowane.</span><span class="sxs-lookup"><span data-stu-id="57a0e-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="57a0e-138">Ponadto program <xref:System.Data.SqlClient.SqlDependency> automatycznie uruchamia wątek roboczy, aby przetwarzać powiadomienia w momencie ich opublikowania w kolejce. analizuje również komunikat Service Broker, uwidaczniając informacje jako dane argumentu zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="57a0e-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="57a0e-139"><xref:System.Data.SqlClient.SqlDependency> musi być inicjowany przez wywołanie `Start` metody w celu ustanowienia zależności z bazą danych.</span><span class="sxs-lookup"><span data-stu-id="57a0e-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="57a0e-140">Jest to metoda statyczna, która musi być wywoływana tylko raz podczas inicjowania aplikacji dla wszystkich wymaganych połączeń z bazą danych.</span><span class="sxs-lookup"><span data-stu-id="57a0e-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="57a0e-141">`Stop`Metoda powinna być wywoływana podczas kończenia aplikacji dla każdego połączenia zależności, które zostało wykonane.</span><span class="sxs-lookup"><span data-stu-id="57a0e-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="57a0e-142">Korzystanie z SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="57a0e-142">Using SqlNotificationRequest</span></span>  

 <span data-ttu-id="57a0e-143">Z drugiej strony, <xref:System.Data.Sql.SqlNotificationRequest> wymaga zaimplementowania całej infrastruktury nasłuchiwania.</span><span class="sxs-lookup"><span data-stu-id="57a0e-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="57a0e-144">Ponadto należy zdefiniować wszystkie pomocnicze obiekty Service Broker, takie jak kolejka, usługa i typy komunikatów obsługiwane przez kolejkę.</span><span class="sxs-lookup"><span data-stu-id="57a0e-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="57a0e-145">To podejście ręczne jest przydatne, jeśli aplikacja wymaga specjalnych komunikatów powiadomień lub zachowań powiadomień lub jeśli aplikacja jest częścią aplikacji o większej Service Broker.</span><span class="sxs-lookup"><span data-stu-id="57a0e-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a0e-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="57a0e-146">See also</span></span>

- [<span data-ttu-id="57a0e-147">Powiadomienia zapytań w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="57a0e-147">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="57a0e-148">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="57a0e-148">ADO.NET Overview</span></span>](../ado-net-overview.md)
