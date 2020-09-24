---
title: Wystąpienia użytkownika programu SQL Server Express
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 00c12376-cb26-4317-86ad-e6e9c089be57
ms.openlocfilehash: 401b62f56918e8ac406a5ee2dda2252d328592bc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147583"
---
# <a name="sql-server-express-user-instances"></a>Wystąpienia użytkownika programu SQL Server Express

Microsoft SQL Server Express Edition (SQL Server Express) obsługuje funkcję wystąpienia użytkownika, która jest dostępna tylko w przypadku używania .NET Framework Dostawca danych dla SQL Server ( `SqlClient` ). Wystąpienie użytkownika jest osobnym wystąpieniem aparatu bazy danych SQL Server Express, który jest generowany przez wystąpienie nadrzędne. Wystąpienia użytkowników umożliwiają użytkownikom, którzy nie są administratorami na swoich komputerach lokalnych, dołączania do SQL Server Express baz danych i łączenia się z nimi. Każde wystąpienie jest uruchamiane w kontekście zabezpieczeń poszczególnych użytkowników, na podstawie jednego wystąpienia na użytkownika.  
  
## <a name="user-instance-capabilities"></a>Możliwości wystąpienia użytkownika  

 Wystąpienia użytkownika są przydatne w przypadku użytkowników, którzy używają systemu Windows w ramach konta użytkownika z najniższymi uprawnieniami (LUA). Każdy użytkownik ma uprawnienia administratora systemu SQL Server ( `sysadmin` ) względem wystąpienia uruchomionego na komputerze bez konieczności uruchamiania jako administrator systemu Windows. Oprogramowanie wykonywane w wystąpieniu użytkownika z ograniczonymi uprawnieniami nie może wprowadzać zmian na poziomie systemu, ponieważ wystąpienie SQL Server Express jest uruchomione na koncie systemu Windows niebędącym administratorem użytkownika, a nie jako usługa. Każde wystąpienie użytkownika jest odizolowane od jego wystąpienia nadrzędnego oraz z dowolnego innego wystąpienia użytkownika działającego na tym samym komputerze. Bazy danych działające w wystąpieniu użytkownika są otwierane tylko w trybie jednego użytkownika i nie jest możliwe, aby wielu użytkowników łączyło się z bazami danych działającymi w wystąpieniu użytkownika. Replikacja i rozproszone zapytania są również wyłączone dla wystąpień użytkownika.
  
> [!NOTE]
> Wystąpienia użytkownika nie są konieczne dla użytkowników, którzy są już administratorami na swoich komputerach, lub scenariuszy obejmujących wielu użytkowników bazy danych.  
  
## <a name="enabling-user-instances"></a>Włączanie wystąpień użytkownika  

 Aby wygenerować wystąpienia użytkownika, musi być uruchomione wystąpienie nadrzędne SQL Server Express. Wystąpienia użytkownika są domyślnie włączone po zainstalowaniu SQL Server Express i mogą być jawnie włączane lub wyłączane przez administratora systemu, wykonując procedurę składowaną systemu **sp_configure** w wystąpieniu nadrzędnym.  
  
```sql  
-- Enable user instances.  
sp_configure 'user instances enabled','1'
  
-- Disable user instances.  
sp_configure 'user instances enabled','0'  
```  
  
 Protokół sieciowy dla wystąpień użytkownika musi być lokalnymi nazwanymi potokami. Wystąpienie użytkownika nie może zostać uruchomione na zdalnym wystąpieniu SQL Server, a logowania SQL Server nie są dozwolone.  
  
## <a name="connecting-to-a-user-instance"></a>Nawiązywanie połączenia z wystąpieniem użytkownika  

 `User Instance` `AttachDBFilename` <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> Słowa kluczowe i umożliwiają <xref:System.Data.SqlClient.SqlConnection> nawiązywanie połączenia z wystąpieniem użytkownika. Wystąpienia użytkownika są również obsługiwane przez <xref:System.Data.SqlClient.SqlConnectionStringBuilder> `UserInstance` właściwości i `AttachDBFilename` .  
  
 Zwróć uwagę na następujące informacje dotyczące przykładowych parametrów połączenia przedstawionych poniżej:  
  
- `Data Source`Słowo kluczowe odwołuje się do wystąpienia nadrzędnego SQL Server Express, które generuje wystąpienie użytkownika. Wystąpienie domyślne to .\SQLEXPRESS.  
  
- `Integrated Security` jest ustawiony na `true` . Aby nawiązać połączenie z wystąpieniem użytkownika, wymagane jest uwierzytelnianie systemu Windows; Nazwy logowania SQL Server nie są obsługiwane.  
  
- `User Instance`Jest ustawiona na `true` , która wywołuje wystąpienie użytkownika. (Wartość domyślna to `false` ).  
  
- `AttachDbFileName`Słowo kluczowe parametrów połączenia służy do dołączania podstawowego pliku bazy danych (. mdf), który musi zawierać pełną nazwę ścieżki. `AttachDbFileName` odnosi się również do kluczy "właściwości rozszerzone" i "początkowa nazwa pliku" w <xref:System.Data.SqlClient.SqlConnection> parametrach połączenia.  
  
- `|DataDirectory|`Ciąg podstawienia ujęty w symbole potoku odwołuje się do katalogu danych aplikacji otwierającej połączenie i udostępnia ścieżkę względną wskazującą lokalizację plików. mdf i. ldf. Jeśli chcesz zlokalizować te pliki w innym miejscu, musisz podać pełną ścieżkę do plików.  
  
```text
Data Source=.\\SQLExpress;Integrated Security=true;  
User Instance=true;AttachDBFilename=|DataDirectory|\InstanceDB.mdf;  
Initial Catalog=InstanceDB;  
```  
  
> [!NOTE]
> Można również użyć <xref:System.Data.SqlClient.SqlConnectionStringBuilder> <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserInstance%2A> właściwości i, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.AttachDBFilename%2A> Aby utworzyć parametry połączenia w czasie wykonywania.  
  
### <a name="using-the-124datadirectory124-substitution-string"></a>Korzystanie z &#124;&#124; ciągu podstawienia usługi DataDirectory  

 `AttachDbFileName` Program został rozszerzony w ADO.NET 2,0, wprowadzając `|DataDirectory|` ciąg podstawienia (ujęty w nawiasy potoku). `DataDirectory` Program jest używany w połączeniu z programem w `AttachDbFileName` celu wskazania ścieżki względnej do pliku danych, dzięki czemu deweloperzy mogą tworzyć parametry połączenia oparte na ścieżce względnej do źródła danych, a nie są wymagane do określenia pełnej ścieżki.  
  
 Fizyczna lokalizacja, która `DataDirectory` wskazuje, zależy od typu aplikacji. W tym przykładzie plik Northwind. mdf, który ma zostać dołączony, znajduje się w folderze \ app_data aplikacji.  
  
```text
Data Source=.\\SQLExpress;Integrated Security=true;  
User Instance=true;  
AttachDBFilename=|DataDirectory|\app_data\Northwind.mdf;  
Initial Catalog=Northwind;  
```  
  
 Gdy `DataDirectory` jest używany, ścieżka pliku wyników nie może być wyższa w strukturze katalogów niż katalog wskazany przez ciąg podstawienia. Jeśli na przykład w pełni rozwinięto `DataDirectory` c:\appdirectory\ App_Data, następnie przykładowe parametry połączenia wyświetlane powyżej działają, ponieważ są poniżej c:\AppDirectory. Jednak próba określenia `DataDirectory` jako `|DataDirectory|\..\data` spowoduje wystąpienie błędu, ponieważ \data nie jest podkatalogiem \AppDirectory.  
  
 Jeśli parametry połączenia mają nieprawidłowo sformatowane ciągi podstawienia, <xref:System.ArgumentException> zostanie zgłoszony.  
  
> [!NOTE]
> <xref:System.Data.SqlClient> rozpoznaje ciągi podstawienia w pełnych ścieżkach do lokalnego systemu plików komputera. W związku z tym, nazwy serwera zdalnego, protokołu HTTP i ścieżki UNC nie są obsługiwane. Wyjątek jest zgłaszany podczas otwierania połączenia, jeśli serwer nie znajduje się na komputerze lokalnym.  
  
 Gdy <xref:System.Data.SqlClient.SqlConnection> jest otwarty, zostaje przekierowany z domyślnego wystąpienia SQL Server Express do wystąpienia zainicjowanego w czasie wykonywania uruchomionego na koncie wywołującym.  
  
> [!NOTE]
> Może być konieczne zwiększenie <xref:System.Data.SqlClient.SqlConnection.ConnectionTimeout%2A> wartości, ponieważ wystąpienia użytkownika mogą trwać dłużej niż zwykłe wystąpienia.  
  
 Poniższy fragment kodu otwiera nowy `SqlConnection` , wyświetla parametry połączenia w oknie konsoli, a następnie zamyka połączenie podczas zamykania `using` bloku kodu.  
  
```vb  
Private Sub OpenSqlConnection()  
    ' Retrieve the connection string.  
    Dim connectionString As String = GetConnectionString()  
  
    Using connection As New SqlConnection(connectionString)  
        connection.Open()  
        Console.WriteLine("ConnectionString: {0}", _  
           connection.ConnectionString)  
    End Using  
End Sub  
```  
  
```csharp  
private static void OpenSqlConnection()  
{  
    // Retrieve the connection string.  
    string connectionString = GetConnectionString();  
  
    using (SqlConnection connection =
        new SqlConnection(connectionString))  
    {  
        connection.Open();  
        Console.WriteLine("ConnectionString: {0}",
             connection.ConnectionString);  
    }  
}  
```  
  
> [!NOTE]
> Wystąpienia użytkownika nie są obsługiwane w kodzie środowiska uruchomieniowego języka wspólnego (CLR), który działa wewnątrz SQL Server. <xref:System.InvalidOperationException>Jest zgłaszany `Open` , jeśli jest wywoływana dla <xref:System.Data.SqlClient.SqlConnection> , który ma `User Instance=true` w parametrach połączenia.  
  
## <a name="lifetime-of-a-user-instance-connection"></a>Okres istnienia połączenia wystąpienia użytkownika  

 W przeciwieństwie do wersji SQL Server, które są uruchamiane jako usługa, wystąpienia SQL Server Express nie muszą być uruchamiane ręcznie ani zatrzymywane. Za każdym razem, gdy użytkownik loguje się i nawiązuje połączenie z wystąpieniem użytkownika, wystąpienie użytkownika zostanie uruchomione, jeśli nie zostało jeszcze uruchomione. Bazy danych wystąpień użytkownika mają `AutoClose` ustawioną opcję, dzięki czemu baza danych jest automatycznie zamykana po okresie braku aktywności. Uruchomiony proces sqlservr.exe jest uruchomiony przez ograniczony limit czasu od momentu zamknięcia ostatniego połączenia z wystąpieniem, dlatego nie trzeba go ponownie uruchomić, jeśli inne połączenie zostanie otwarte przed upływem limitu czasu. Wystąpienie użytkownika zostaje automatycznie zamknięte, jeśli nie zostanie otwarte nowe połączenie przed upływem limitu czasu. Administrator systemu w wystąpieniu nadrzędnym może ustawić czas trwania okresu dla wystąpienia użytkownika przy użyciu **sp_configure** , aby zmienić opcję **limitu czasu wystąpienia użytkownika** . Wartość domyślna to 60 min.  
  
> [!NOTE]
> Jeśli `Min Pool Size` jest używany w parametrach połączenia o wartości większej niż zero, połączenie pulę będzie zawsze obsługiwać kilka otwartych połączeń, a wystąpienie użytkownika nie zostanie automatycznie zamknięte.  
  
## <a name="how-user-instances-work"></a>Jak działają wystąpienia użytkownika  

 Podczas pierwszego generowania wystąpienia użytkownika dla każdego użytkownika bazy danych **Master** i **msdb** są kopiowane z folderu dane szablonu do ścieżki w katalogu repozytorium danych aplikacji lokalnych użytkownika do wyłącznego użytku przez wystąpienie użytkownika. Ta ścieżka jest zwykle `C:\Documents and Settings\<UserName>\Local Settings\Application Data\Microsoft\Microsoft SQL Server Data\SQLEXPRESS` . Po uruchomieniu wystąpienia użytkownika pliki **tempdb**, log i Trace są również zapisywane w tym katalogu. Dla tego wystąpienia jest generowana nazwa, która gwarantuje unikalność dla każdego użytkownika.  
  
 Domyślnie wszyscy członkowie grupy Builtin\Users systemu Windows uzyskują uprawnienia do nawiązywania połączeń na lokalnym wystąpieniu oraz uprawnienia Odczyt i wykonywanie w plikach binarnych SQL Server. Po zweryfikowaniu poświadczeń użytkownika wywołującego, który hostuje wystąpienie użytkownika, ten użytkownik zostanie przypisany do tego `sysadmin` wystąpienia. Tylko pamięć udostępniona jest włączona dla wystąpień użytkownika, co oznacza, że możliwe jest tylko wykonywanie operacji na komputerze lokalnym.  
  
 Użytkownicy muszą mieć uprawnienia do odczytu i zapisu w plikach MDF i ldf określonych w parametrach połączenia.  
  
> [!NOTE]
> Pliki MDF i ldf reprezentują odpowiednio bazę danych i pliki dziennika. Te dwa pliki są zgodne z zestawem, dlatego należy zachować ostrożność podczas operacji wykonywania kopii zapasowych i przywracania. Plik bazy danych zawiera informacje o dokładnej wersji pliku dziennika, a baza danych nie zostanie otwarta, jeśli zostanie ona połączona z nieprawidłowym plikiem dziennika.  
  
 Aby uniknąć uszkodzenia danych, baza danych w wystąpieniu użytkownika jest otwierana z wyłącznym dostępem. Jeśli dwa różne wystąpienia użytkownika współużytkują tę samą bazę danych na tym samym komputerze, użytkownik pierwszego wystąpienia musi zamknąć bazę danych, zanim będzie można ją otworzyć w drugim wystąpieniu.  
  
## <a name="user-instance-scenarios"></a>Scenariusze wystąpienia użytkownika  

 Wystąpienia użytkowników zapewniają deweloperom aplikacji baz danych SQL Server magazynem danych, który nie zależy od deweloperów mających konta administracyjne na swoich komputerach deweloperskich. Wystąpienia użytkowników są oparte na modelu dostępu/aparatu Jet, w którym aplikacja bazy danych po prostu nawiązuje połączenie z plikiem, a użytkownik automatycznie ma pełne uprawnienia do wszystkich obiektów bazy danych bez konieczności interwencji administratora systemu do udzielenia uprawnień. Jest przeznaczony do pracy w sytuacjach, w których użytkownik jest uruchomiony przy użyciu konta użytkownika z najniższymi uprawnieniami (LUA) i nie ma uprawnień administracyjnych na serwerze lub na komputerze lokalnym, ale musi utworzyć obiekty i aplikacje bazy danych. Wystąpienia użytkowników umożliwiają użytkownikom tworzenie wystąpień w czasie wykonywania, które są uruchamiane w kontekście zabezpieczeń użytkownika, a nie w kontekście zabezpieczeń bardziej uprzywilejowanej usługi systemowej.  
  
> [!IMPORTANT]
> Wystąpienia użytkowników powinny być używane tylko w scenariuszach, w których wszystkie używane aplikacje są w pełni zaufane.  
  
 Scenariusze wystąpienia użytkownika obejmują:  
  
- Dowolna aplikacja pojedynczego użytkownika, gdzie udostępnianie danych nie jest wymagana.  
  
- Wdrożenie ClickOnce. Jeśli .NET Framework 2,0 (lub nowszy) i SQL Server Express są już zainstalowane na komputerze docelowym, pakiet instalacyjny pobrany w wyniku akcji ClickOnce może być instalowany i używany przez użytkowników innych niż administratorzy. Należy pamiętać, że administrator musi zainstalować SQL Server Express, jeśli jest częścią instalacji. Aby uzyskać więcej informacji, zobacz [wdrażanie ClickOnce dla Windows Forms](/dotnet/desktop/winforms/clickonce-deployment-for-windows-forms).
  
- Dedykowane hosting ASP.NET przy użyciu uwierzytelniania systemu Windows. Pojedyncze wystąpienie SQL Server Express może być hostowane w intranecie. Aplikacja nawiązuje połączenie przy użyciu konta systemu Windows ASPNET, a nie przy użyciu personifikacji. Wystąpienia użytkownika nie powinny być używane w scenariuszach hostingu innych firm ani udostępnionych, w których wszystkie aplikacje współużytkują to samo wystąpienie użytkownika i nie będą już od siebie odizolowane.  
  
## <a name="see-also"></a>Zobacz też

- [SQL Server i ADO.NET](index.md)
- [Parametry połączenia](../connection-strings.md)
- [Nawiązywanie połączenia ze źródłem danych](../connecting-to-a-data-source.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
