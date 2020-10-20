---
title: Połącz platformę .NET dla Apache Spark z SQL Server
description: Dowiedz się, jak nawiązać połączenie z wystąpieniem SQL Server z poziomu aplikacji .NET for Apache Spark.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: b20710000d8717b5df238aa9a782371fbe586037
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224025"
---
# <a name="connect-net-for-apache-spark-to-sql-server"></a><span data-ttu-id="7e5ef-103">Połącz platformę .NET dla Apache Spark z SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e5ef-103">Connect .NET for Apache Spark to SQL Server</span></span>

<span data-ttu-id="7e5ef-104">W tym artykule dowiesz się, jak nawiązać połączenie z wystąpieniem programu SQL Server z aplikacji [.net for Apache Spark](https://github.com/dotnet/spark) .</span><span class="sxs-lookup"><span data-stu-id="7e5ef-104">In this article, you learn how to connect to an SQL server instance from your [.NET for Apache Spark](https://github.com/dotnet/spark) application.</span></span>

## <a name="configure-sql-server-to-grant-your-application-access"></a><span data-ttu-id="7e5ef-105">Skonfiguruj SQL Server, aby udzielić dostępu do aplikacji</span><span class="sxs-lookup"><span data-stu-id="7e5ef-105">Configure SQL Server to grant your application access</span></span>

1. <span data-ttu-id="7e5ef-106">Dodaj użytkownika i hasło logowania, wybierając SQL Server uwierzytelniania do wystąpienia SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7e5ef-106">Add a login user and password choosing SQL Server authentication to your SQL Server instance.</span></span>
2. <span data-ttu-id="7e5ef-107">Nadaj użytkownikom zalogowanym odpowiednie uprawnienia na poziomie bazy danych, jak pokazano poniżej:</span><span class="sxs-lookup"><span data-stu-id="7e5ef-107">Give that login user necessary permissions at the relevant database level as shown below:</span></span>

    ![Uprawnienia SQL Server](./media/connect-external-sources/SqlServerAuth.png)

3. <span data-ttu-id="7e5ef-109">Upewnij się, że domyślny port dla SQL Server `1433` jest dozwolony przez zaporę.</span><span class="sxs-lookup"><span data-stu-id="7e5ef-109">Make sure the default port for SQL Server `1433` is allowed through the firewall.</span></span>
4. <span data-ttu-id="7e5ef-110">Otwórz Menedżera konfiguracji programu SQL Server, aby włączyć protokół TCP/IP za pomocą konfiguracji sieci, jak pokazano poniżej:</span><span class="sxs-lookup"><span data-stu-id="7e5ef-110">Open SQL configure manager to enable TCP/IP through the network configuration as shown below:</span></span>

    ![SQL Server Włączanie protokołu TCP/IP](./media/connect-external-sources/SqlServerTCPIP.png)

    <span data-ttu-id="7e5ef-112">Należy również zwrócić uwagę na wartość **Wysłuchaj wszystko** na powyższej karcie w obszarze **Protokół**.</span><span class="sxs-lookup"><span data-stu-id="7e5ef-112">Also note the value of **Listen All** in above tab under **Protocol**.</span></span>

5. <span data-ttu-id="7e5ef-113">Skonfiguruj port TCP/IP do 1433 dla wszystkich wymaganych adresów IP, jeśli `Listen All` jest ustawiony na `No` .</span><span class="sxs-lookup"><span data-stu-id="7e5ef-113">Configure the TCP/IP port to 1433 for all required IP addresses if the `Listen All` is set to `No`.</span></span> <span data-ttu-id="7e5ef-114">W przeciwnym razie Ustaw port TCP w IPAll.</span><span class="sxs-lookup"><span data-stu-id="7e5ef-114">Otherwise, set the TCP Port in IPAll.</span></span>

    ![SQL Server Port TCP/IP](./media/connect-external-sources/SQLServerTCPIIPPort.png)

## <a name="connect-to-sql-server-from-your-application"></a><span data-ttu-id="7e5ef-116">Nawiązywanie połączenia z SQL Server aplikacji</span><span class="sxs-lookup"><span data-stu-id="7e5ef-116">Connect to SQL Server from your application</span></span>

1. <span data-ttu-id="7e5ef-117">Użyj sterownika JDBC firmy Microsoft SQL Server w celu zapewnienia łączności z bazą danych za pośrednictwem aplikacji (Pobierz z [tej oficjalnej witryny sieci Web](https://docs.microsoft.com/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)).</span><span class="sxs-lookup"><span data-stu-id="7e5ef-117">Use the Microsoft JDBC Driver for SQL Server to provide database connectivity through your application (download from [this official website](https://docs.microsoft.com/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)).</span></span>
2. <span data-ttu-id="7e5ef-118">Ustaw następujące konfiguracje, aby nawiązać połączenie z wystąpieniem programu SQL Server i bazą danych z aplikacji:</span><span class="sxs-lookup"><span data-stu-id="7e5ef-118">Set the following configurations to connect to the SQL server instance and database from your application:</span></span>
    1. <span data-ttu-id="7e5ef-119">**connection_url**: jest to adres URL służący do nawiązywania połączenia z wystąpieniem lub bazą danych programu SQL Server i ma następujący format:</span><span class="sxs-lookup"><span data-stu-id="7e5ef-119">**connection_url**: This is the URL used to connect to the SQL server instance/database and has the following format:</span></span>

        ```
        jdbc:sqlserver://<SQL_server_IP_address>:1433;instanceName=<instance_name>;databaseName=<database_name>;
        ```

    2. <span data-ttu-id="7e5ef-120">**DbTable**: Nazwa tabeli, do której uzyskuje się dostęp.</span><span class="sxs-lookup"><span data-stu-id="7e5ef-120">**dbtable**: Name of table being accessed.</span></span>
    3. <span data-ttu-id="7e5ef-121">**użytkownik**: Zaloguj użytkownika w kroku 1 konfigurowania programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7e5ef-121">**user**: Login user set up in Step 1 of configuring the SQL server.</span></span>
    4. <span data-ttu-id="7e5ef-122">**hasło**: Hasło skonfigurowane w kroku 1 konfigurowania programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7e5ef-122">**password**: Password of user set up in Step 1 of configuring the SQL server.</span></span>
3. <span data-ttu-id="7e5ef-123">Użyj powyższej konfiguracji w kodzie aplikacji, aby odczytać dane z tabeli, jak pokazano poniżej:</span><span class="sxs-lookup"><span data-stu-id="7e5ef-123">Use the above configuration in your application code to read the data from a table as shown below:</span></span>

    ```csharp
    static void Main()
    {
        SparkSession spark = SparkSession
            .Builder()
            .AppName("Connect to SQL Server")
            .GetOrCreate();

        string connection_url = "<URL to connect to SQL server instance>";
        string dbtable = "<database table to access>";
        string user = "<Login user name>";
        string password = "<Login user password>";

        DataFrame jdbcDF = spark.Read()
            .Format("jdbc")
            .Option("driver", "com.microsoft.sqlserver.jdbc.SQLServerDriver")
            .Option("url", connection_url)
            .Option("dbtable", dbtable)
            .Option("user", user)
            .Option("password", password).Load();
        jdbcDF.Show(); // Displays the content of the SQL table as a DataFrame
    }
    ```
