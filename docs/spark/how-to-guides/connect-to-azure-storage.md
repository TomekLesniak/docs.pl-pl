---
title: Nawiązywanie połączenia z magazynem zdalnym z komputera lokalnego
description: Połącz się z kontami usługi Azure Storage przy użyciu platformy .NET dla Apache Spark z komputera lokalnego.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: dc0c3b44279756596f3d456616821e690710ae04
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224017"
---
# <a name="connect-to-azure-data-lake-storage-gen-2-or-wasb-account"></a><span data-ttu-id="fd0a5-103">Nawiązywanie połączenia z kontem Azure Data Lake Storage generacji 2 lub WASB</span><span class="sxs-lookup"><span data-stu-id="fd0a5-103">Connect to Azure Data Lake Storage Gen 2 or WASB account</span></span>

<span data-ttu-id="fd0a5-104">W tym artykule dowiesz się, jak nawiązać połączenie z kontem Azure Data Lake Storage (ADLS) generacji 2 lub Windows Azure Storage Blob (WASB) przy użyciu wystąpienia programu [.NET dla Apache Spark](https://github.com/dotnet/spark) uruchomionego lokalnie na komputerze z systemem Windows.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-104">In this article, you learn how to connect to an Azure Data Lake Storage (ADLS) Gen 2 or Windows Azure Storage Blob (WASB) account through an instance of [.NET for Apache Spark](https://github.com/dotnet/spark) running locally on your Windows machine.</span></span>

## <a name="set-up-the-environment"></a><span data-ttu-id="fd0a5-105">Konfigurowanie środowiska</span><span class="sxs-lookup"><span data-stu-id="fd0a5-105">Set up the environment</span></span>

1. <span data-ttu-id="fd0a5-106">Pobierz dystrybucję Apache Spark utworzoną bez usługi Hadoop z [oficjalnej witryny sieci Web](https://archive.apache.org/dist/spark/) (Wybierz wersję [obsługiwaną przez platformę .NET dla Apache Spark](https://github.com/dotnet/spark#supported-apache-spark)) i Wyodrębnij ją do katalogu.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-106">Download the Apache Spark distribution built without Hadoop from [official website](https://archive.apache.org/dist/spark/) (choose a version [supported by .NET for Apache Spark](https://github.com/dotnet/spark#supported-apache-spark)), and extract it to a directory.</span></span> <span data-ttu-id="fd0a5-107">Ustaw zmienną środowiskową `SPARK_HOME` na ten katalog.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-107">Set the environment variable `SPARK_HOME` to this directory.</span></span>
2. <span data-ttu-id="fd0a5-108">Pobierz plik binarny Apache Hadoop z tego [miejsca](http://hadoop.apache.org/releases.html) i wyodrębnij go do folderu, a następnie ustaw `HADOOP_HOME` dla zmiennej środowiskowej ten folder.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-108">Download the Apache Hadoop binary from [here](http://hadoop.apache.org/releases.html) and extract to a folder, and set your `HADOOP_HOME` environment variable to this folder.</span></span>
3. <span data-ttu-id="fd0a5-109">Pobierz `winutils.exe` pliki i `hadoop.dll` z [tej lokalizacji](https://github.com/cdarlint/winutils) (w zależności od wersji usługi Hadoop zainstalowanej w poprzednim kroku) i umieść je w folderze bin usługi Hadoop.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-109">Download the `winutils.exe` and `hadoop.dll` files from [this location](https://github.com/cdarlint/winutils) (depending on the version of Hadoop installed in the previous step) and put them in the bin folder of your Hadoop.</span></span> <span data-ttu-id="fd0a5-110">Te pliki binarne są potrzebne w systemie Windows w celu poprawnego skonfigurowania wszystkich ustawień (szczegółowe informacje znajdują się w [temacie Apache wiki tutaj](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)).</span><span class="sxs-lookup"><span data-stu-id="fd0a5-110">These binaries are needed on Windows in order to get everything setup correctly (this is explained in detail in the [Apache wiki here](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)).</span></span>
4. <span data-ttu-id="fd0a5-111">Skonfiguruj instalację usługi Hadoop, wprowadzając następujące zmiany do `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd` pliku:</span><span class="sxs-lookup"><span data-stu-id="fd0a5-111">Configure your Hadoop installation by making the following changes to your `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd` file:</span></span>
    1. <span data-ttu-id="fd0a5-112">Ustaw `JAVA_HOME` Właściwość przy użyciu ścieżki DOS (ponieważ usługa Hadoop nie przypomina spacji w systemie `JAVA_HOME` ).</span><span class="sxs-lookup"><span data-stu-id="fd0a5-112">Set the `JAVA_HOME` property using the DOS path (since Hadoop doesn't like spaces in `JAVA_HOME`).</span></span> <span data-ttu-id="fd0a5-113">Powinno to wyglądać następująco: `C:\Progra~1\Java\jdk1.8.0_241` (wskazując na dowolną wersję środowiska Java zainstalowaną na komputerze lokalnym).</span><span class="sxs-lookup"><span data-stu-id="fd0a5-113">This should look something like this: `C:\Progra~1\Java\jdk1.8.0_241` (Pointing to whatever version of Java you have installed on your local machine).</span></span>
    2. <span data-ttu-id="fd0a5-114">Dołącz `%HADOOP_HOME%\share\hadoop\tools\lib\*` do `HADOOP_CLASSPATH` .</span><span class="sxs-lookup"><span data-stu-id="fd0a5-114">Append `%HADOOP_HOME%\share\hadoop\tools\lib\*` to `HADOOP_CLASSPATH`.</span></span>
    <span data-ttu-id="fd0a5-115">Ostatni `hadoop-env.cmd` plik powinien wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="fd0a5-115">Your final `hadoop-env.cmd` file should look something like this:</span></span>

    ![Końcowy plik Hadoop-ENV. cmd](./media/connect-external-sources/hadoop-env.png)

## <a name="configure-your-storage-account-in-hadoop"></a><span data-ttu-id="fd0a5-117">Konfigurowanie konta magazynu w usłudze Hadoop</span><span class="sxs-lookup"><span data-stu-id="fd0a5-117">Configure your storage account in Hadoop</span></span>

1. <span data-ttu-id="fd0a5-118">Otwórz konto magazynu ADLS generacji 2 lub WASB, z którym chcesz nawiązać połączenie za pośrednictwem [Azure Portal](https://portal.azure.com) i Otwórz panel **klucze dostępu** w bloku **Ustawienia** , a następnie skopiuj wartość **klucz** z w obszarze Klucz1.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-118">Open the ADLS Gen 2 or WASB storage account you want to connect to through the [Azure portal](https://portal.azure.com) and open the **Access keys** panel under the **Settings** blade and copy the value of **Key** from under key1.</span></span>
2. <span data-ttu-id="fd0a5-119">Teraz w celu skonfigurowania usługi Hadoop w celu uzyskania dostępu do konta ADLS Gen2 należy edytować `core-site.xml` plik (znajdujący się w `%HADOOP_HOME%\etc\hadoop\` pliku) zawierający konfigurację całego klastra.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-119">Now in order to configure Hadoop to access your ADLS Gen2 account you would have to edit your `core-site.xml` (located in `%HADOOP_HOME%\etc\hadoop\` ) file which contains cluster-wide configuration.</span></span> <span data-ttu-id="fd0a5-120">Dodaj następujące właściwości wewnątrz `<configuration>` tagów w tym pliku:</span><span class="sxs-lookup"><span data-stu-id="fd0a5-120">Add the following properties inside the `<configuration>` tags in this file:</span></span>

    ```xml
    <configuration>
      <property>
        <name>fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.dfs.core.windows.net</name>
        <value>SharedKey</value>
        <description></description>
      </property>
      <property>
        <name>fs.azure.account.key.YOUR_ACCOUNT_NAME.dfs.core.windows.net</name>
        <value>YOUR ACCESS KEY (copied from Step 1)</value>
        <description>The secret password. Never share these.</description>
      </property>
    </configuration>
    ```

    <span data-ttu-id="fd0a5-121">Jeśli próbujesz nawiązać połączenie z kontem WASB, Zastąp ciąg nazwą `dfs` `blob` właściwości.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-121">If you are trying to connect to a WASB account, replace `dfs` with `blob` in the property names.</span></span> <span data-ttu-id="fd0a5-122">Na przykład `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-122">For example, `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.</span></span>
3. <span data-ttu-id="fd0a5-123">Możesz przetestować łączność z kontem magazynu z poziomu usługi Hadoop, uruchamiając następujące polecenie w `%HADOOP_HOME%` katalogu:</span><span class="sxs-lookup"><span data-stu-id="fd0a5-123">You can test the connectivity to your Storage Account from Hadoop by running the following command from your `%HADOOP_HOME%` directory:</span></span>

    ```bash
    bin\hdfs dfs -ls <URI to your account>
    ```

<span data-ttu-id="fd0a5-124">Powinno to spowodować wyświetlenie listy wszystkich plików/folderów w ścieżce udostępnionej przez identyfikator URI.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-124">This should display a list of all files/folders in the path provided by your URI.</span></span>

> [!NOTE]
> <span data-ttu-id="fd0a5-125">Format do uzyskania identyfikatora URI dla konta magazynu jest następujący:</span><span class="sxs-lookup"><span data-stu-id="fd0a5-125">The format to derive the URI to your Storage account is as follows:</span></span>
>
> ```
> For ADLS: abfs[s]://<file_system>@<account_name>.dfs.core.windows.net/<path>/<file_name>
> For WASB: wasb[s]://<file_system>@<account_name>.blob.core.windows.net/<path>/<file_name>
> ```

## <a name="connect-to-your-storage-account"></a><span data-ttu-id="fd0a5-126">Nawiązywanie połączenia z kontem magazynu</span><span class="sxs-lookup"><span data-stu-id="fd0a5-126">Connect to your storage account</span></span>

1. <span data-ttu-id="fd0a5-127">Jeśli powyższe polecenie będzie działało, możesz teraz przejść do korzystania z tego konta magazynu za pomocą platformy Spark.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-127">If the above command worked, you can now move on to accessing this storage account through Spark.</span></span> <span data-ttu-id="fd0a5-128">Najpierw uruchom polecenie `hadoop classpath` z wiersza polecenia `%HADOOP_HOME%` i skopiuj dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-128">First run the command `hadoop classpath` from the commandline inside `%HADOOP_HOME%` and copy the output.</span></span>
2. <span data-ttu-id="fd0a5-129">Ustaw dane wyjściowe polecenia Run w kroku 1 do wartości zmiennej środowiskowej `SPARK_DIST_CLASSPATH` .</span><span class="sxs-lookup"><span data-stu-id="fd0a5-129">Set the output of the command run in Step 1 to the value of environment variable `SPARK_DIST_CLASSPATH`.</span></span>
3. <span data-ttu-id="fd0a5-130">Teraz powinno być możliwe uzyskanie dostępu do konta magazynu ADLS lub WASB za pośrednictwem platformy Spark .NET przy użyciu identyfikatora URI ABFS, jak pokazano w poniższym przykładzie poniżej.</span><span class="sxs-lookup"><span data-stu-id="fd0a5-130">Now you should be able to access your ADLS or WASB storage account through Spark .NET using the abfs URI as shown in the simple example below.</span></span> <span data-ttu-id="fd0a5-131">(W tym przykładzie użyto standardowego [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) przykładowego pliku dostarczonego z każdą instalacją Apache Spark):</span><span class="sxs-lookup"><span data-stu-id="fd0a5-131">(For this example we use the standard [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) example file provided with every Apache Spark installation.):</span></span>

    ```csharp
    SparkSession spark = SparkSession
       .Builder()
       .AppName("Connect to Azure Storage locally")
       .GetOrCreate();
    DataFrame df = spark.Read().Json("wasbs://file_system@account_name.blob.core.windows.net/path/people.json");
    //DataFrame df = spark.Read().Json("abfss://file_system@account_name.dfs.core.windows.net/path/file.json");
    df.Show();
    ```

    <span data-ttu-id="fd0a5-132">Wynik jest wyświetlany jako ramka danych ( `df` ), jak pokazano poniżej:</span><span class="sxs-lookup"><span data-stu-id="fd0a5-132">The result as displayed is the DataFrame (`df`) as shown below:</span></span>

    ```text
    +----+-------+
    | age|   name|
    +----+-------+
    |null|Michael|
    |  30|   Andy|
    |  19| Justin|
    +----+-------+
    ```
