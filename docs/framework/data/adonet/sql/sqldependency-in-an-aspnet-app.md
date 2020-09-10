---
title: Element SqlDependency w aplikacji ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 2ec9415f63151443d5008fbce471fabeb89cdb91
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656174"
---
# <a name="sqldependency-in-an-aspnet-application"></a>Element SqlDependency w aplikacji ASP.NET
W przykładzie w tej sekcji pokazano, jak używać <xref:System.Data.SqlClient.SqlDependency> pośrednio, wykorzystując obiekt ASP.NET <xref:System.Web.Caching.SqlCacheDependency> . <xref:System.Web.Caching.SqlCacheDependency>Obiekt używa obiektu <xref:System.Data.SqlClient.SqlDependency> do nasłuchiwania powiadomień i poprawnie zaktualizować pamięć podręczną.  
  
> [!NOTE]
> Przykładowy kod założono, że włączono powiadomienia o zapytaniach przez wykonanie skryptów w temacie [Włączanie powiadomień o zapytaniach](enabling-query-notifications.md).  
  
## <a name="about-the-sample-application"></a>Informacje o aplikacji przykładowej  
 Aplikacja Przykładowa używa pojedynczej strony sieci Web ASP.NET do wyświetlania informacji o produkcie z bazy danych SQL Server **AdventureWorks** w <xref:System.Web.UI.WebControls.GridView> kontrolce. Po załadowaniu strony kod zapisuje bieżący czas do <xref:System.Web.UI.WebControls.Label> kontrolki. Następnie definiuje <xref:System.Web.Caching.SqlCacheDependency> obiekt i ustawia właściwości dla <xref:System.Web.Caching.Cache> obiektu w celu przechowywania danych w pamięci podręcznej przez maksymalnie trzy minuty. Kod następnie łączy się z bazą danych i pobiera dane. Po załadowaniu strony i uruchomieniu aplikacji ASP.NET pobierze dane z pamięci podręcznej, którą można zweryfikować, zwracając uwagę, że czas na stronie nie ulegnie zmianie. Jeśli monitorowane dane zmieniają się, ASP.NET unieważnia pamięć podręczną i ponownie wypełnia `GridView` kontrolę przy użyciu nowych danych, aktualizując czas wyświetlany w `Label` kontrolce.  
  
## <a name="creating-the-sample-application"></a>Tworzenie przykładowej aplikacji  
 Wykonaj następujące kroki, aby utworzyć i uruchomić przykładową aplikację:  
  
1. Utwórz nową witrynę sieci Web ASP.NET.  
  
2. Dodaj <xref:System.Web.UI.WebControls.Label> <xref:System.Web.UI.WebControls.GridView> kontrolkę i do domyślnej strony. aspx.  
  
3. Otwórz moduł klasy strony i Dodaj następujące dyrektywy:  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. Dodaj następujący kod do `Page_Load` zdarzenia strony:  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. Dodaj dwie metody pomocnika `GetConnectionString` i `GetSQL` . Zdefiniowane parametry połączenia korzystają ze zintegrowanych zabezpieczeń. Musisz sprawdzić, czy konto, którego używasz, ma wymagane uprawnienia do bazy danych i czy Przykładowa baza danych, **AdventureWorks**ma włączone powiadomienia.
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a>Testowanie aplikacji  
 Aplikacja buforuje dane wyświetlane w formularzu sieci Web i odświeża je co trzy minuty w przypadku braku aktywności. Jeśli nastąpi zmiana do bazy danych, pamięć podręczna jest odświeżana natychmiast. Uruchom aplikację z programu Visual Studio, która ładuje stronę do przeglądarki. Wyświetlany czas odświeżania pamięci podręcznej wskazuje, kiedy ostatnio odświeżono pamięć podręczną. Odczekaj trzy minuty, a następnie Odśwież stronę, powodując wystąpienie zdarzenia ogłaszania zwrotnego. Zauważ, że czas wyświetlany na stronie został zmieniony. Po odświeżeniu strony w czasie krótszym niż trzy minuty godzina wyświetlana na stronie pozostanie taka sama.  
  
 Teraz zaktualizuj dane w bazie danych przy użyciu polecenia Transact-SQL UPDATE i Odśwież stronę. Czas wyświetlania teraz wskazuje, że pamięć podręczna została odświeżona przy użyciu nowych danych z bazy danych. Należy pamiętać, że mimo że pamięć podręczna jest aktualizowana, czas wyświetlania na stronie nie zmienia się, dopóki nie wystąpi zdarzenie ogłaszania zwrotnego.  

## <a name="distributed-cache-synchronization-using-sql-dependency"></a>Synchronizacja rozproszonej pamięci podręcznej przy użyciu zależności SQL

Niektóre z rozproszonych pamięci podręcznych innych firm, takie jak [NCache](https://www.alachisoft.com/ncache) , zapewniają obsługę synchronizacji bazy danych SQL i pamięci podręcznej przy użyciu [zależności SQL](https://www.alachisoft.com/resources/docs/ncache/prog-guide/sql-dependency.html). Aby uzyskać więcej informacji i przykładową implementację kodu źródłowego, zobacz [przykład zależności SQL rozproszonej pamięci podręcznej](https://github.com/Alachisoft/NCache-Samples/tree/master/dotnet/Dependencies/SQLDependency).

## <a name="see-also"></a>Zobacz także

- [Powiadomienia zapytań w programie SQL Server](query-notifications-in-sql-server.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
