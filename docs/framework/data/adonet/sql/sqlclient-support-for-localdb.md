---
title: Obsługa SqlClient w bazie danych LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 55ab1346de6f5c14f15d01344a984c18edf30e02
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824483"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="8a1ba-102">Obsługa SqlClient w bazie danych LocalDB</span><span class="sxs-lookup"><span data-stu-id="8a1ba-102">SqlClient Support for LocalDB</span></span>

<span data-ttu-id="8a1ba-103">W tym artykule omówiono sposób nawiązywania połączenia z bazą danych LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-103">This article discusses how to connect to a LocalDB database.</span></span> <span data-ttu-id="8a1ba-104">LocalDB to uproszczona wersja SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-104">LocalDB is a lightweight version of SQL Server.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8a1ba-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8a1ba-105">Remarks</span></span>
  
 <span data-ttu-id="8a1ba-106">Aby podsumować, co możesz zrobić z LocalDB:</span><span class="sxs-lookup"><span data-stu-id="8a1ba-106">To summarize what you can do with LocalDB:</span></span>  
  
- <span data-ttu-id="8a1ba-107">Twórz i uruchamiaj wystąpienia LocalDB za pomocą sqllocaldb.exe lub pliku app.config.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-107">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
- <span data-ttu-id="8a1ba-108">Użyj sqlcmd.exe, aby dodać i zmodyfikować bazy danych w wystąpieniu LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-108">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="8a1ba-109">Na przykład `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-109">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
- <span data-ttu-id="8a1ba-110">Użyj `AttachDBFilename` słowa kluczowego Connection, aby dodać bazę danych do wystąpienia usługi LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-110">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="8a1ba-111">Jeśli używasz `AttachDBFilename` , jeśli nie określisz nazwy bazy danych za pomocą `Database` słowa kluczowego Connection, baza danych zostanie usunięta z wystąpienia LocalDB, gdy aplikacja zostanie zamknięta.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-111">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
- <span data-ttu-id="8a1ba-112">Określ wystąpienie LocalDB w parametrach połączenia.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-112">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="8a1ba-113">Na przykład nazwa wystąpienia to `myInstance` , ciąg połączenia:</span><span class="sxs-lookup"><span data-stu-id="8a1ba-113">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    `server=(localdb)\\myInstance`  
  
 <span data-ttu-id="8a1ba-114">`User Instance=True` nie jest dozwolone podczas nawiązywania połączenia z bazą danych LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-114">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
<span data-ttu-id="8a1ba-115">Informacje o instalowaniu LocalDB można znaleźć w temacie [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).</span><span class="sxs-lookup"><span data-stu-id="8a1ba-115">For information about installing LocalDB, see [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).</span></span>
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="8a1ba-116">Programowe tworzenie nazwanego wystąpienia</span><span class="sxs-lookup"><span data-stu-id="8a1ba-116">Programmatically Create a Named Instance</span></span>  

 <span data-ttu-id="8a1ba-117">Aplikacja może utworzyć nazwane wystąpienie i określić bazę danych w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="8a1ba-117">An application can create a named instance and specify a database as follows:</span></span>  
  
- <span data-ttu-id="8a1ba-118">Określ wystąpienia LocalDB do utworzenia w pliku app.config w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-118">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="8a1ba-119">Numer wersji wystąpienia powinien być taki sam jak numer wersji instalacji programu LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-119">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
- <span data-ttu-id="8a1ba-120">Określ nazwę wystąpienia za pomocą `server` słowa kluczowego parametrów połączenia.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-120">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="8a1ba-121">Nazwa wystąpienia określona w `server` słowie kluczowym parametrów połączenia musi być zgodna z nazwą określoną w pliku app.config.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-121">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
- <span data-ttu-id="8a1ba-122">Użyj `AttachDBFilename` słowa kluczowego Connection, aby określić. Plik MDF.</span><span class="sxs-lookup"><span data-stu-id="8a1ba-122">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a1ba-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8a1ba-123">See also</span></span>

- [<span data-ttu-id="8a1ba-124">Funkcje Serwera SQL i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8a1ba-124">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)
- [<span data-ttu-id="8a1ba-125">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8a1ba-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
