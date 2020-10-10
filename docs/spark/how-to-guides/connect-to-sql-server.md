---
title: Połącz platformę .NET dla Apache Spark z SQL Server
description: Dowiedz się, jak nawiązać połączenie z wystąpieniem SQL Server z poziomu aplikacji .NET for Apache Spark.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 773e743a67c066438cb86d983ebfa34f73692c2d
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877889"
---
# <a name="connect-net-for-apache-spark-to-sql-server"></a>Połącz platformę .NET dla Apache Spark z SQL Server

W tym artykule dowiesz się, jak nawiązać połączenie z wystąpieniem programu SQL Server z aplikacji [.net for Apache Spark](https://github.com/dotnet/spark) .

## <a name="configure-sql-server-to-grant-your-application-access"></a>Skonfiguruj SQL Server, aby udzielić dostępu do aplikacji

1. Dodaj użytkownika i hasło logowania, wybierając SQL Server uwierzytelniania do wystąpienia SQL Server.
2. Nadaj użytkownikom zalogowanym odpowiednie uprawnienia na poziomie bazy danych, jak pokazano poniżej:

    ![Uprawnienia SQL Server](./media/connect-external-sources/SqlServerAuth.png)

3. Upewnij się, że domyślny port dla SQL Server `1433` jest dozwolony przez zaporę.
4. Otwórz Menedżera konfiguracji programu SQL Server, aby włączyć protokół TCP/IP za pomocą konfiguracji sieci, jak pokazano poniżej:

    ![SQL Server Włączanie protokołu TCP/IP](./media/connect-external-sources/SqlServerTCPIP.png)

    Należy również zwrócić uwagę na wartość **Wysłuchaj wszystko** na powyższej karcie w obszarze **Protokół**.

5. Skonfiguruj port TCP/IP do 1433 dla wszystkich wymaganych adresów IP, jeśli `Listen All` jest ustawiony na `No` . W przeciwnym razie Ustaw port TCP w IPAll.

    ![SQL Server Port TCP/IP](./media/connect-external-sources/SQLServerTCPIIPPort.png)

## <a name="connect-to-sql-server-from-your-application"></a>Nawiązywanie połączenia z SQL Server aplikacji

1. Użyj sterownika JDBC firmy Microsoft SQL Server w celu zapewnienia łączności z bazą danych za pośrednictwem aplikacji (Pobierz z [tej oficjalnej witryny sieci Web](https://docs.microsoft.com/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)).
2. Ustaw następujące konfiguracje, aby nawiązać połączenie z wystąpieniem programu SQL Server i bazą danych z aplikacji:
    1. **connection_url**: jest to adres URL służący do nawiązywania połączenia z wystąpieniem lub bazą danych programu SQL Server i ma następujący format:

        ```
        jdbc:sqlserver://<SQL_server_IP_address>:1433;instanceName=<instance_name>;databaseName=<database_name>;
        ```

    2. **DbTable**: Nazwa tabeli, do której uzyskuje się dostęp.
    3. **użytkownik**: Zaloguj użytkownika w kroku 1 konfigurowania programu SQL Server.
    4. **hasło**: Hasło skonfigurowane w kroku 1 konfigurowania programu SQL Server.
3. Użyj powyższej konfiguracji w kodzie aplikacji, aby odczytać dane z tabeli, jak pokazano poniżej:

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
