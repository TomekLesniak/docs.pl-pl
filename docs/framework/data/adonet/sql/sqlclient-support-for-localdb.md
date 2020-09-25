---
title: Obsługa SqlClient w bazie danych LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 841c455605b0b32668d26cab16a6207dc1c0f716
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203426"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="d16de-102">Obsługa SqlClient w bazie danych LocalDB</span><span class="sxs-lookup"><span data-stu-id="d16de-102">SqlClient Support for LocalDB</span></span>

<span data-ttu-id="d16de-103">Począwszy od SQL Server nazwy Denali, zostanie udostępniona uproszczona wersja SQL Server o nazwie LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d16de-103">Beginning in SQL Server code name Denali, a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="d16de-104">W tym temacie omówiono sposób nawiązywania połączenia z bazą danych LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d16de-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d16de-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d16de-105">Remarks</span></span>  

 <span data-ttu-id="d16de-106">Aby uzyskać więcej informacji na temat LocalDB, w tym sposobu instalowania LocalDB i konfigurowania wystąpienia LocalDB, zobacz SQL Server Books Online.</span><span class="sxs-lookup"><span data-stu-id="d16de-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="d16de-107">Aby podsumować, co możesz zrobić z LocalDB:</span><span class="sxs-lookup"><span data-stu-id="d16de-107">To summarize what you can do with LocalDB:</span></span>  
  
- <span data-ttu-id="d16de-108">Twórz i uruchamiaj wystąpienia LocalDB za pomocą sqllocaldb.exe lub pliku app.config.</span><span class="sxs-lookup"><span data-stu-id="d16de-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
- <span data-ttu-id="d16de-109">Użyj sqlcmd.exe, aby dodać i zmodyfikować bazy danych w wystąpieniu LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d16de-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="d16de-110">Na przykład `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="d16de-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
- <span data-ttu-id="d16de-111">Użyj `AttachDBFilename` słowa kluczowego Connection, aby dodać bazę danych do wystąpienia usługi LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d16de-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="d16de-112">Jeśli używasz `AttachDBFilename` , jeśli nie określisz nazwy bazy danych za pomocą `Database` słowa kluczowego Connection, baza danych zostanie usunięta z wystąpienia LocalDB, gdy aplikacja zostanie zamknięta.</span><span class="sxs-lookup"><span data-stu-id="d16de-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
- <span data-ttu-id="d16de-113">Określ wystąpienie LocalDB w parametrach połączenia.</span><span class="sxs-lookup"><span data-stu-id="d16de-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="d16de-114">Na przykład nazwa wystąpienia to `myInstance` , ciąg połączenia:</span><span class="sxs-lookup"><span data-stu-id="d16de-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    `server=(localdb)\\myInstance`  
  
 <span data-ttu-id="d16de-115">`User Instance=True` nie jest dozwolone podczas nawiązywania połączenia z bazą danych LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d16de-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="d16de-116">Możesz pobrać LocalDB z [pakietu Feature Pack Microsoft SQL Server 2012](https://www.microsoft.com/download/en/details.aspx?id=29065).</span><span class="sxs-lookup"><span data-stu-id="d16de-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="d16de-117">Jeśli będziesz używać sqlcmd.exe do modyfikowania danych w wystąpieniu usługi LocalDB, będziesz potrzebować narzędzia sqlcmd z SQL Server 2012, które można także pobrać z pakietu funkcji SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="d16de-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from SQL Server 2012, which you can also get from the SQL Server 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="d16de-118">Programowe tworzenie nazwanego wystąpienia</span><span class="sxs-lookup"><span data-stu-id="d16de-118">Programmatically Create a Named Instance</span></span>  

 <span data-ttu-id="d16de-119">Aplikacja może utworzyć nazwane wystąpienie i określić bazę danych w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="d16de-119">An application can create a named instance and specify a database as follows:</span></span>  
  
- <span data-ttu-id="d16de-120">Określ wystąpienia LocalDB do utworzenia w pliku app.config w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="d16de-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="d16de-121">Numer wersji wystąpienia powinien być taki sam jak numer wersji instalacji programu LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d16de-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
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
  
- <span data-ttu-id="d16de-122">Określ nazwę wystąpienia za pomocą `server` słowa kluczowego parametrów połączenia.</span><span class="sxs-lookup"><span data-stu-id="d16de-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="d16de-123">Nazwa wystąpienia określona w `server` słowie kluczowym parametrów połączenia musi być zgodna z nazwą określoną w pliku app.config.</span><span class="sxs-lookup"><span data-stu-id="d16de-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
- <span data-ttu-id="d16de-124">Użyj `AttachDBFilename` słowa kluczowego Connection, aby określić. Plik MDF.</span><span class="sxs-lookup"><span data-stu-id="d16de-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d16de-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d16de-125">See also</span></span>

- [<span data-ttu-id="d16de-126">Funkcje Serwera SQL i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d16de-126">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)
- [<span data-ttu-id="d16de-127">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d16de-127">ADO.NET Overview</span></span>](../ado-net-overview.md)
