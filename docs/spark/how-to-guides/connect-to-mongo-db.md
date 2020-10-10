---
title: Połącz platformę .NET dla Apache Spark z programem MongoDB
description: Dowiedz się, jak nawiązać połączenie z wystąpieniem usługi MongoDB z poziomu aplikacji .NET for Apache Spark.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 4cb78998ddb54621a84e9d224a814047e3c40246
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877901"
---
# <a name="connect-net-for-apache-spark-to-mongodb"></a>Połącz platformę .NET dla Apache Spark z programem MongoDB

W tym artykule dowiesz się, jak nawiązać połączenie z wystąpieniem usługi MongoDB z poziomu aplikacji .NET for Apache Spark.

## <a name="prerequisites"></a>Wymagania wstępne

1. Przygotuj serwer MongoDB z [bazą danych i](https://docs.mongodb.com/manual/core/databases-and-collections/) dodaliśmy do niego kolekcję (Pobierz [ten serwer Community](https://www.mongodb.com/try/download/community) na serwer lokalny lub wypróbuj usługę [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) w przypadku usługi Cloud MongoDB).

## <a name="set-up-your-mongodb-instance"></a>Skonfiguruj wystąpienie MongoDB

Aby umożliwić programowi .NET Apache Spark komunikowanie się z wystąpieniem usługi MongoDB, upewnij się, że został on poprawnie skonfigurowany, wykonując następujące czynności:

1. Utwórz nazwę użytkownika i hasło dla aplikacji, aby nawiązać połączenie, i nadaj użytkownikowi wymagane uprawnienia/role przy użyciu następującego polecenia za pośrednictwem powłoki Mongo:

    ```bash
    use database
    db.createUser(
      {
        user: "mySparkUser",
        pwd: "<password>",
        roles: [ { role: "userAdminAnyDatabase", db: "admin" }, "readWriteAnyDatabase" ]
      }
    )
    ```

2. Upewnij się, że adres IP komputera, na którym działa aplikacja .NET dla Apache Spark, jest listy dozwolonych, aby serwer MongoDB mógł nawiązać połączenie z usługą. Możesz zapoznać się z [tym przewodnikiem](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/) , aby dowiedzieć się, jak to zrobić.

## <a name="configure-your-net-for-apache-spark-application"></a>Skonfiguruj platformę .NET dla aplikacji Apache Spark

1. Aby skonfigurować aplikację do komunikacji z wystąpieniem MongoDB i odczytać z kolekcji, należy ustawić następujące zmienne.
    1. **authURI**: "parametry połączenia upoważniające aplikację do łączenia się z wymaganym wystąpieniem MongoDB". Jest to następujący format:

        ```
        "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>"
        ```

    2. **Nazwa użytkownika**: Nazwa użytkownika konta utworzonego w kroku 1 poprzedniej sekcji
    3. **hasło**: hasło utworzonego konta użytkownika
    4. **cluster_address**: Nazwa hosta/adres klastra MongoDB
    5. **baza danych**: baza danych MongoDB, z którą chcesz nawiązać połączenie
    6. **Kolekcja**: Kolekcja MongoDB, którą chcesz odczytać. (W tym przykładzie użyto standardowego [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) przykładowego pliku dostarczonego z każdą instalacją Apache Spark).

2. Użyj `com.mongodb.spark.sql.DefaultSource` formatu `spark.Read()` , jak pokazano poniżej w prostym fragmencie kodu:

    ```csharp
    class Program
    {
        static void Main()
        {
            var authURI = "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>?retryWrites=true&w=majority";
            SparkSession spark = SparkSession
                .Builder()
                .AppName("Connect to Mongo DB example")
                .Config("spark.mongodb.input.uri", authURI)
                .GetOrCreate();

            DataFrame df = spark.Read().Format("com.mongodb.spark.sql.DefaultSource").Load();
            df.PrintSchema();
            df.Show();
            spark.Stop();
        }
    }
    ```

## <a name="run-your-application"></a>Uruchamianie aplikacji

Aby można było uruchomić aplikację .NET for Apache Spark, należy zdefiniować `mongo-spark-connector` moduł jako część definicji kompilacji w projekcie platformy Spark, używając `libraryDependency` w tym `build.sbt` celu projektów SBT. W przypadku środowisk Spark, takich jak `spark-submit` (lub `spark-shell` ) należy użyć `--packages` opcji wiersza polecenia, takiej jak:

```bash
spark-submit --master local --packages org.mongodb.spark:mongo-spark-connector_2.12:3.0.0 --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-<version>.jar yourApp.exe
```

> [!NOTE]
> Upewnij się, że dołączasz wersję pakietu zgodnie z uruchomioną wersją platformy Spark.

Wynik jest wyświetlany jako ramka danych ( `df` ), jak pokazano poniżej:

```text
+--------------------+----+-------+
|                 _id| age|   name|
+--------------------+----+-------+
|[5f7c28438029a134...|null|Michael|
|[5f7c287f8029a134...|  30|   Andy|
|[5f7c289a8029a134...|  19| Justin|
+--------------------+----+-------+
```
