---
title: Element SqlDependency w aplikacji ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 7c982550533cb6d8547ab2ce78ad2e814d07857f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184797"
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="3c72a-102">Element SqlDependency w aplikacji ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3c72a-102">SqlDependency in an ASP.NET Application</span></span>

<span data-ttu-id="3c72a-103">W przykładzie w tej sekcji pokazano, jak używać <xref:System.Data.SqlClient.SqlDependency> pośrednio, wykorzystując obiekt ASP.NET <xref:System.Web.Caching.SqlCacheDependency> .</span><span class="sxs-lookup"><span data-stu-id="3c72a-103">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="3c72a-104"><xref:System.Web.Caching.SqlCacheDependency>Obiekt używa obiektu <xref:System.Data.SqlClient.SqlDependency> do nasłuchiwania powiadomień i poprawnie zaktualizować pamięć podręczną.</span><span class="sxs-lookup"><span data-stu-id="3c72a-104">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c72a-105">Przykładowy kod założono, że włączono powiadomienia o zapytaniach przez wykonanie skryptów w temacie [Włączanie powiadomień o zapytaniach](enabling-query-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="3c72a-105">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="3c72a-106">Informacje o aplikacji przykładowej</span><span class="sxs-lookup"><span data-stu-id="3c72a-106">About the Sample Application</span></span>  

 <span data-ttu-id="3c72a-107">Aplikacja Przykładowa używa pojedynczej strony sieci Web ASP.NET do wyświetlania informacji o produkcie z bazy danych SQL Server **AdventureWorks** w <xref:System.Web.UI.WebControls.GridView> kontrolce.</span><span class="sxs-lookup"><span data-stu-id="3c72a-107">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="3c72a-108">Po załadowaniu strony kod zapisuje bieżący czas do <xref:System.Web.UI.WebControls.Label> kontrolki.</span><span class="sxs-lookup"><span data-stu-id="3c72a-108">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="3c72a-109">Następnie definiuje <xref:System.Web.Caching.SqlCacheDependency> obiekt i ustawia właściwości dla <xref:System.Web.Caching.Cache> obiektu w celu przechowywania danych w pamięci podręcznej przez maksymalnie trzy minuty.</span><span class="sxs-lookup"><span data-stu-id="3c72a-109">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="3c72a-110">Kod następnie łączy się z bazą danych i pobiera dane.</span><span class="sxs-lookup"><span data-stu-id="3c72a-110">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="3c72a-111">Po załadowaniu strony i uruchomieniu aplikacji ASP.NET pobierze dane z pamięci podręcznej, którą można zweryfikować, zwracając uwagę, że czas na stronie nie ulegnie zmianie.</span><span class="sxs-lookup"><span data-stu-id="3c72a-111">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="3c72a-112">Jeśli monitorowane dane zmieniają się, ASP.NET unieważnia pamięć podręczną i ponownie wypełnia `GridView` kontrolę przy użyciu nowych danych, aktualizując czas wyświetlany w `Label` kontrolce.</span><span class="sxs-lookup"><span data-stu-id="3c72a-112">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="3c72a-113">Tworzenie przykładowej aplikacji</span><span class="sxs-lookup"><span data-stu-id="3c72a-113">Creating the Sample Application</span></span>  

 <span data-ttu-id="3c72a-114">Wykonaj następujące kroki, aby utworzyć i uruchomić przykładową aplikację:</span><span class="sxs-lookup"><span data-stu-id="3c72a-114">Follow these steps to create and run the sample application:</span></span>  
  
1. <span data-ttu-id="3c72a-115">Utwórz nową witrynę sieci Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3c72a-115">Create a new ASP.NET Web site.</span></span>  
  
2. <span data-ttu-id="3c72a-116">Dodaj <xref:System.Web.UI.WebControls.Label> <xref:System.Web.UI.WebControls.GridView> kontrolkę i do domyślnej strony. aspx.</span><span class="sxs-lookup"><span data-stu-id="3c72a-116">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3. <span data-ttu-id="3c72a-117">Otwórz moduł klasy strony i Dodaj następujące dyrektywy:</span><span class="sxs-lookup"><span data-stu-id="3c72a-117">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. <span data-ttu-id="3c72a-118">Dodaj następujący kod do `Page_Load` zdarzenia strony:</span><span class="sxs-lookup"><span data-stu-id="3c72a-118">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. <span data-ttu-id="3c72a-119">Dodaj dwie metody pomocnika `GetConnectionString` i `GetSQL` .</span><span class="sxs-lookup"><span data-stu-id="3c72a-119">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="3c72a-120">Zdefiniowane parametry połączenia korzystają ze zintegrowanych zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="3c72a-120">The connection string defined uses integrated security.</span></span> <span data-ttu-id="3c72a-121">Musisz sprawdzić, czy konto, którego używasz, ma wymagane uprawnienia do bazy danych i czy Przykładowa baza danych, **AdventureWorks**ma włączone powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="3c72a-121">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span>
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="3c72a-122">Testowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="3c72a-122">Testing the Application</span></span>  

 <span data-ttu-id="3c72a-123">Aplikacja buforuje dane wyświetlane w formularzu sieci Web i odświeża je co trzy minuty w przypadku braku aktywności.</span><span class="sxs-lookup"><span data-stu-id="3c72a-123">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="3c72a-124">Jeśli nastąpi zmiana do bazy danych, pamięć podręczna jest odświeżana natychmiast.</span><span class="sxs-lookup"><span data-stu-id="3c72a-124">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="3c72a-125">Uruchom aplikację z programu Visual Studio, która ładuje stronę do przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="3c72a-125">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="3c72a-126">Wyświetlany czas odświeżania pamięci podręcznej wskazuje, kiedy ostatnio odświeżono pamięć podręczną.</span><span class="sxs-lookup"><span data-stu-id="3c72a-126">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="3c72a-127">Odczekaj trzy minuty, a następnie Odśwież stronę, powodując wystąpienie zdarzenia ogłaszania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="3c72a-127">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="3c72a-128">Zauważ, że czas wyświetlany na stronie został zmieniony.</span><span class="sxs-lookup"><span data-stu-id="3c72a-128">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="3c72a-129">Po odświeżeniu strony w czasie krótszym niż trzy minuty godzina wyświetlana na stronie pozostanie taka sama.</span><span class="sxs-lookup"><span data-stu-id="3c72a-129">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="3c72a-130">Teraz zaktualizuj dane w bazie danych przy użyciu polecenia Transact-SQL UPDATE i Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="3c72a-130">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="3c72a-131">Czas wyświetlania teraz wskazuje, że pamięć podręczna została odświeżona przy użyciu nowych danych z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="3c72a-131">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="3c72a-132">Należy pamiętać, że mimo że pamięć podręczna jest aktualizowana, czas wyświetlania na stronie nie zmienia się, dopóki nie wystąpi zdarzenie ogłaszania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="3c72a-132">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  

## <a name="distributed-cache-synchronization-using-sql-dependency"></a><span data-ttu-id="3c72a-133">Synchronizacja rozproszonej pamięci podręcznej przy użyciu zależności SQL</span><span class="sxs-lookup"><span data-stu-id="3c72a-133">Distributed cache synchronization using SQL Dependency</span></span>

<span data-ttu-id="3c72a-134">Niektóre z rozproszonych pamięci podręcznych innych firm, takie jak [NCache](https://www.alachisoft.com/ncache) , zapewniają obsługę synchronizacji bazy danych SQL i pamięci podręcznej przy użyciu [zależności SQL](https://www.alachisoft.com/resources/docs/ncache/prog-guide/sql-dependency.html).</span><span class="sxs-lookup"><span data-stu-id="3c72a-134">Some of the third-party distributed caches such as [NCache](https://www.alachisoft.com/ncache) provide support to synchronize the SQL database and cache using [SQL Dependency](https://www.alachisoft.com/resources/docs/ncache/prog-guide/sql-dependency.html).</span></span> <span data-ttu-id="3c72a-135">Aby uzyskać więcej informacji i przykładową implementację kodu źródłowego, zobacz [przykład zależności SQL rozproszonej pamięci podręcznej](https://github.com/Alachisoft/NCache-Samples/tree/master/dotnet/Dependencies/SQLDependency).</span><span class="sxs-lookup"><span data-stu-id="3c72a-135">For more information and an example source code implementation, see [Distributed cache SQL Dependency sample](https://github.com/Alachisoft/NCache-Samples/tree/master/dotnet/Dependencies/SQLDependency).</span></span>

## <a name="see-also"></a><span data-ttu-id="3c72a-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3c72a-136">See also</span></span>

- [<span data-ttu-id="3c72a-137">Powiadomienia zapytań w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="3c72a-137">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="3c72a-138">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3c72a-138">ADO.NET Overview</span></span>](../ado-net-overview.md)
