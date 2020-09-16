---
title: Powiadomienia zapytań w programie SQL Server
description: Informacje na temat używania powiadomień o zapytaniach w celu powiadomienia aplikacji o zmianie danych w bazie danych SQL Server, na przykład w celu odświeżenia wyświetlania aplikacji.
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 43b496db74f7e6fc9bc9f17d946bf34398b32312
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543988"
---
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="98ee4-103">Powiadomienia zapytań w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="98ee4-103">Query Notifications in SQL Server</span></span>
<span data-ttu-id="98ee4-104">W oparciu o infrastrukturę Service Broker powiadomienia o zapytaniach umożliwiają powiadamianie aplikacji o zmianach danych.</span><span class="sxs-lookup"><span data-stu-id="98ee4-104">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="98ee4-105">Ta funkcja jest szczególnie przydatna w przypadku aplikacji, które udostępniają pamięć podręczną informacji z bazy danych, takiej jak aplikacja sieci Web, i należy powiadamiać o zmianach danych źródłowych.</span><span class="sxs-lookup"><span data-stu-id="98ee4-105">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="98ee4-106">Istnieją trzy sposoby implementacji powiadomień o zapytaniach przy użyciu ADO.NET:</span><span class="sxs-lookup"><span data-stu-id="98ee4-106">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1. <span data-ttu-id="98ee4-107">Implementacja niskiego poziomu jest dostarczana przez `SqlNotificationRequest` klasę, która udostępnia funkcje po stronie serwera, co umożliwia wykonywanie poleceń z żądaniem powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="98ee4-107">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2. <span data-ttu-id="98ee4-108">Implementacja wysokiego poziomu jest dostarczana przez `SqlDependency` klasę, która jest klasą, która zapewnia abstrakcję wysokiego poziomu funkcji powiadomień między aplikacją źródłową i SQL Server, co pozwala na używanie zależności do wykrywania zmian na serwerze.</span><span class="sxs-lookup"><span data-stu-id="98ee4-108">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="98ee4-109">W większości przypadków jest to najprostszy i najbardziej efektywny sposób, aby wykorzystać możliwości SQL Server powiadomień przez zarządzane aplikacje klienckie przy użyciu Dostawca danych .NET Framework dla SQL Server.</span><span class="sxs-lookup"><span data-stu-id="98ee4-109">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3. <span data-ttu-id="98ee4-110">Ponadto aplikacje sieci Web skompilowane przy użyciu ASP.NET 2,0 lub nowszej mogą używać `SqlCacheDependency` klas pomocnika.</span><span class="sxs-lookup"><span data-stu-id="98ee4-110">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="98ee4-111">Powiadomienia o zapytaniach są używane w przypadku aplikacji, które wymagają odświeżenia wyświetlania lub buforowania w odpowiedzi na zmiany danych bazowych.</span><span class="sxs-lookup"><span data-stu-id="98ee4-111">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="98ee4-112">Microsoft SQL Server umożliwia aplikacjom .NET Framework wysyłanie polecenia do SQL Server i żądanie powiadomienia, jeśli wykonanie tego samego polecenia spowoduje wygenerowanie zestawów wynikowych innych niż pobrane początkowo.</span><span class="sxs-lookup"><span data-stu-id="98ee4-112">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="98ee4-113">Powiadomienia generowane na serwerze są wysyłane przez kolejki, aby można je było przetworzyć później.</span><span class="sxs-lookup"><span data-stu-id="98ee4-113">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="98ee4-114">Możesz skonfigurować powiadomienia dla instrukcji SELECT i EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="98ee4-114">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="98ee4-115">Przy użyciu instrukcji EXECUTE SQL Server rejestruje powiadomienie dla wykonywanego polecenia, a nie samą instrukcję EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="98ee4-115">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="98ee4-116">Polecenie musi spełniać wymagania i ograniczenia dotyczące instrukcji SELECT.</span><span class="sxs-lookup"><span data-stu-id="98ee4-116">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="98ee4-117">Gdy polecenie rejestrujące powiadomienie zawiera więcej niż jedną instrukcję, aparat bazy danych tworzy powiadomienie dla każdej instrukcji w partii.</span><span class="sxs-lookup"><span data-stu-id="98ee4-117">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="98ee4-118">Jeśli tworzysz aplikację, w której potrzebujesz niezawodnych powiadomień podrzędnych w przypadku zmiany danych, zapoznaj się z sekcją **Planowanie wydajnej strategii powiadomień o zapytaniach** i **alternatywy do wysyłania zapytań do powiadomień** w artykule [Planowanie powiadomień](/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) .</span><span class="sxs-lookup"><span data-stu-id="98ee4-118">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) article.</span></span> <span data-ttu-id="98ee4-119">Aby uzyskać więcej informacji na temat powiadomień o zapytaniach i SQL Server Service Broker, zobacz następujące linki do artykułów w dokumentacji SQL Server.</span><span class="sxs-lookup"><span data-stu-id="98ee4-119">For more information about Query Notifications and SQL Server Service Broker, see the following links to articles in the SQL Server documentation.</span></span>  
  
 <span data-ttu-id="98ee4-120">**Dokumentacja SQL Server**</span><span class="sxs-lookup"><span data-stu-id="98ee4-120">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="98ee4-121">[Korzystanie z powiadomień o zapytaniach](/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="98ee4-121">[Using Query Notifications](/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))</span></span>  
  
- <span data-ttu-id="98ee4-122">[Tworzenie zapytania dla powiadomienia](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="98ee4-122">[Creating a Query for Notification](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="98ee4-123">[Programowanie (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="98ee4-123">[Development (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))</span></span>  
  
- <span data-ttu-id="98ee4-124">[Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="98ee4-124">[Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="98ee4-125">[Przewodnik dewelopera (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="98ee4-125">[Developer's Guide (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98ee4-126">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="98ee4-126">In This Section</span></span>  
 [<span data-ttu-id="98ee4-127">Włączanie powiadomień o zapytaniach</span><span class="sxs-lookup"><span data-stu-id="98ee4-127">Enabling Query Notifications</span></span>](enabling-query-notifications.md)  
 <span data-ttu-id="98ee4-128">W tym artykule omówiono sposób używania powiadomień o zapytaniach, w tym wymagania dotyczące włączania i korzystania z nich.</span><span class="sxs-lookup"><span data-stu-id="98ee4-128">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="98ee4-129">Element SqlDependency w aplikacji ASP.NET</span><span class="sxs-lookup"><span data-stu-id="98ee4-129">SqlDependency in an ASP.NET Application</span></span>](sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="98ee4-130">Pokazuje, jak używać powiadomień o zapytaniach z aplikacji ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="98ee4-130">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="98ee4-131">Wykrywanie zmian za pomocą elementu SqlDependency</span><span class="sxs-lookup"><span data-stu-id="98ee4-131">Detecting Changes with SqlDependency</span></span>](detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="98ee4-132">Pokazuje, w jaki sposób wykryć, kiedy wyniki zapytania będą inne niż te, które zostały pierwotnie odebrane.</span><span class="sxs-lookup"><span data-stu-id="98ee4-132">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="98ee4-133">Wykonywanie polecenia SqlCommand za pomocą SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="98ee4-133">SqlCommand Execution with a SqlNotificationRequest</span></span>](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="98ee4-134">Demonstruje Konfigurowanie <xref:System.Data.SqlClient.SqlCommand> obiektu do pracy z powiadomieniem o zapytaniach.</span><span class="sxs-lookup"><span data-stu-id="98ee4-134">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="98ee4-135">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="98ee4-135">Reference</span></span>  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="98ee4-136">Opisuje <xref:System.Data.Sql.SqlNotificationRequest> klasę i wszystkich jej członków.</span><span class="sxs-lookup"><span data-stu-id="98ee4-136">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="98ee4-137">Opisuje <xref:System.Data.SqlClient.SqlDependency> klasę i wszystkich jej członków.</span><span class="sxs-lookup"><span data-stu-id="98ee4-137">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="98ee4-138">Opisuje <xref:System.Web.Caching.SqlCacheDependency> klasę i wszystkich jej członków.</span><span class="sxs-lookup"><span data-stu-id="98ee4-138">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ee4-139">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="98ee4-139">See also</span></span>

- [<span data-ttu-id="98ee4-140">SQL Server i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="98ee4-140">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="98ee4-141">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="98ee4-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
