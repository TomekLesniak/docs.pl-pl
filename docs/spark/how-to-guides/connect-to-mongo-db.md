---
title: Połącz platformę .NET dla Apache Spark z programem MongoDB
description: Dowiedz się, jak nawiązać połączenie z wystąpieniem usługi MongoDB z poziomu aplikacji .NET for Apache Spark.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 928cc8e3559e13af66268f3d1b3766cf2df9041f
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223970"
---
# <a name="connect-net-for-apache-spark-to-mongodb"></a><span data-ttu-id="c0af3-103">Połącz platformę .NET dla Apache Spark z programem MongoDB</span><span class="sxs-lookup"><span data-stu-id="c0af3-103">Connect .NET for Apache Spark to MongoDB</span></span>

<span data-ttu-id="c0af3-104">W tym artykule dowiesz się, jak nawiązać połączenie z wystąpieniem usługi MongoDB z poziomu aplikacji .NET for Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="c0af3-104">In this article, you learn how to connect to a MongoDB instance from your .NET for Apache Spark application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c0af3-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="c0af3-105">Prerequisites</span></span>

1. <span data-ttu-id="c0af3-106">Przygotuj serwer MongoDB z [bazą danych i](https://docs.mongodb.com/manual/core/databases-and-collections/) dodaliśmy do niego kolekcję (Pobierz [ten serwer Community](https://www.mongodb.com/try/download/community) na serwer lokalny lub wypróbuj usługę [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) w przypadku usługi Cloud MongoDB).</span><span class="sxs-lookup"><span data-stu-id="c0af3-106">Have a MongoDB server up and running with a [database and some collection](https://docs.mongodb.com/manual/core/databases-and-collections/) added to it (Download [this community server](https://www.mongodb.com/try/download/community) for a local server or you can try [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) for a cloud MongoDB service.)</span></span>

## <a name="set-up-your-mongodb-instance"></a><span data-ttu-id="c0af3-107">Skonfiguruj wystąpienie MongoDB</span><span class="sxs-lookup"><span data-stu-id="c0af3-107">Set up your MongoDB instance</span></span>

<span data-ttu-id="c0af3-108">Aby umożliwić programowi .NET Apache Spark komunikowanie się z wystąpieniem usługi MongoDB, upewnij się, że został on poprawnie skonfigurowany, wykonując następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="c0af3-108">In order to get .NET for Apache Spark to talk to your MongoDB instance you need to make sure it is set up correctly by doing the following:</span></span>

1. <span data-ttu-id="c0af3-109">Utwórz nazwę użytkownika i hasło dla aplikacji, aby nawiązać połączenie, i nadaj użytkownikowi wymagane uprawnienia/role przy użyciu następującego polecenia za pośrednictwem powłoki Mongo:</span><span class="sxs-lookup"><span data-stu-id="c0af3-109">Create a username and password for your application to connect through, and give the user the necessary permissions/roles using the following command through mongo shell:</span></span>

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

2. <span data-ttu-id="c0af3-110">Upewnij się, że adres IP komputera, na którym działa aplikacja .NET dla Apache Spark, jest listy dozwolonych, aby serwer MongoDB mógł nawiązać połączenie z usługą.</span><span class="sxs-lookup"><span data-stu-id="c0af3-110">Make sure the IP address of the machine your .NET for Apache Spark application is running on is whitelisted for the MongoDB server to be able to connect to.</span></span> <span data-ttu-id="c0af3-111">Możesz zapoznać się z [tym przewodnikiem](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/) , aby dowiedzieć się, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="c0af3-111">You can refer to [this guide](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/) to learn how to do that.</span></span>

## <a name="configure-your-net-for-apache-spark-application"></a><span data-ttu-id="c0af3-112">Skonfiguruj platformę .NET dla aplikacji Apache Spark</span><span class="sxs-lookup"><span data-stu-id="c0af3-112">Configure your .NET for Apache Spark application</span></span>

1. <span data-ttu-id="c0af3-113">Aby skonfigurować aplikację do komunikacji z wystąpieniem MongoDB i odczytać z kolekcji, należy ustawić następujące zmienne.</span><span class="sxs-lookup"><span data-stu-id="c0af3-113">Have the following variables set to configure your application to talk to the MongoDB instance and read from a collection.</span></span>
    1. <span data-ttu-id="c0af3-114">**authURI**: "parametry połączenia upoważniające aplikację do łączenia się z wymaganym wystąpieniem MongoDB".</span><span class="sxs-lookup"><span data-stu-id="c0af3-114">**authURI**: "Connection string authorizing your application to connect to the required MongoDB instance".</span></span> <span data-ttu-id="c0af3-115">Jest to następujący format:</span><span class="sxs-lookup"><span data-stu-id="c0af3-115">The format for that is as follows:</span></span>

        ```
        "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>"
        ```

    2. <span data-ttu-id="c0af3-116">**Nazwa użytkownika**: Nazwa użytkownika konta utworzonego w kroku 1 poprzedniej sekcji</span><span class="sxs-lookup"><span data-stu-id="c0af3-116">**username**: Username of the account you created in Step 1 of the previous section</span></span>
    3. <span data-ttu-id="c0af3-117">**hasło**: hasło utworzonego konta użytkownika</span><span class="sxs-lookup"><span data-stu-id="c0af3-117">**password**: Password of the user account created</span></span>
    4. <span data-ttu-id="c0af3-118">**cluster_address**: Nazwa hosta/adres klastra MongoDB</span><span class="sxs-lookup"><span data-stu-id="c0af3-118">**cluster_address**: hostname/address of your MongoDB cluster</span></span>
    5. <span data-ttu-id="c0af3-119">**baza danych**: baza danych MongoDB, z którą chcesz nawiązać połączenie</span><span class="sxs-lookup"><span data-stu-id="c0af3-119">**database**: The MongoDB database you want to connect to</span></span>
    6. <span data-ttu-id="c0af3-120">**Kolekcja**: Kolekcja MongoDB, którą chcesz odczytać.</span><span class="sxs-lookup"><span data-stu-id="c0af3-120">**collection**: The MongoDB collection you want to read.</span></span> <span data-ttu-id="c0af3-121">(W tym przykładzie użyto standardowego [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) przykładowego pliku dostarczonego z każdą instalacją Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="c0af3-121">(For this example we use the standard [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) example file provided with every Apache Spark installation.)</span></span>

2. <span data-ttu-id="c0af3-122">Użyj `com.mongodb.spark.sql.DefaultSource` formatu `spark.Read()` , jak pokazano poniżej w prostym fragmencie kodu:</span><span class="sxs-lookup"><span data-stu-id="c0af3-122">Use the `com.mongodb.spark.sql.DefaultSource` format is `spark.Read()` as shown below in a simple code snippet:</span></span>

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

## <a name="run-your-application"></a><span data-ttu-id="c0af3-123">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="c0af3-123">Run your application</span></span>

<span data-ttu-id="c0af3-124">Aby można było uruchomić aplikację .NET for Apache Spark, należy zdefiniować `mongo-spark-connector` moduł jako część definicji kompilacji w projekcie platformy Spark, używając `libraryDependency` w tym `build.sbt` celu projektów SBT.</span><span class="sxs-lookup"><span data-stu-id="c0af3-124">In order to run your .NET for Apache Spark application, you should define the `mongo-spark-connector` module as part of the build definition in your Spark project, using `libraryDependency` in `build.sbt` for sbt projects.</span></span> <span data-ttu-id="c0af3-125">W przypadku środowisk Spark, takich jak `spark-submit` (lub `spark-shell` ) należy użyć `--packages` opcji wiersza polecenia, takiej jak:</span><span class="sxs-lookup"><span data-stu-id="c0af3-125">For Spark environments such as `spark-submit` (or `spark-shell`) you should use the `--packages` command-line option like so:</span></span>

```bash
spark-submit --master local --packages org.mongodb.spark:mongo-spark-connector_2.12:3.0.0 --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-<version>.jar yourApp.exe
```

> [!NOTE]
> <span data-ttu-id="c0af3-126">Upewnij się, że dołączasz wersję pakietu zgodnie z uruchomioną wersją platformy Spark.</span><span class="sxs-lookup"><span data-stu-id="c0af3-126">Make sure to include the package version in accordance with the version of Spark being run.</span></span>

<span data-ttu-id="c0af3-127">Wynik jest wyświetlany jako ramka danych ( `df` ), jak pokazano poniżej:</span><span class="sxs-lookup"><span data-stu-id="c0af3-127">The result as displayed is the DataFrame (`df`) as shown below:</span></span>

```text
+--------------------+----+-------+
|                 _id| age|   name|
+--------------------+----+-------+
|[5f7c28438029a134...|null|Michael|
|[5f7c287f8029a134...|  30|   Andy|
|[5f7c289a8029a134...|  19| Justin|
+--------------------+----+-------+
```
