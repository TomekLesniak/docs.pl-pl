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
# <a name="connect-to-azure-data-lake-storage-gen-2-or-wasb-account"></a>Nawiązywanie połączenia z kontem Azure Data Lake Storage generacji 2 lub WASB

W tym artykule dowiesz się, jak nawiązać połączenie z kontem Azure Data Lake Storage (ADLS) generacji 2 lub Windows Azure Storage Blob (WASB) przy użyciu wystąpienia programu [.NET dla Apache Spark](https://github.com/dotnet/spark) uruchomionego lokalnie na komputerze z systemem Windows.

## <a name="set-up-the-environment"></a>Konfigurowanie środowiska

1. Pobierz dystrybucję Apache Spark utworzoną bez usługi Hadoop z [oficjalnej witryny sieci Web](https://archive.apache.org/dist/spark/) (Wybierz wersję [obsługiwaną przez platformę .NET dla Apache Spark](https://github.com/dotnet/spark#supported-apache-spark)) i Wyodrębnij ją do katalogu. Ustaw zmienną środowiskową `SPARK_HOME` na ten katalog.
2. Pobierz plik binarny Apache Hadoop z tego [miejsca](http://hadoop.apache.org/releases.html) i wyodrębnij go do folderu, a następnie ustaw `HADOOP_HOME` dla zmiennej środowiskowej ten folder.
3. Pobierz `winutils.exe` pliki i `hadoop.dll` z [tej lokalizacji](https://github.com/cdarlint/winutils) (w zależności od wersji usługi Hadoop zainstalowanej w poprzednim kroku) i umieść je w folderze bin usługi Hadoop. Te pliki binarne są potrzebne w systemie Windows w celu poprawnego skonfigurowania wszystkich ustawień (szczegółowe informacje znajdują się w [temacie Apache wiki tutaj](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)).
4. Skonfiguruj instalację usługi Hadoop, wprowadzając następujące zmiany do `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd` pliku:
    1. Ustaw `JAVA_HOME` Właściwość przy użyciu ścieżki DOS (ponieważ usługa Hadoop nie przypomina spacji w systemie `JAVA_HOME` ). Powinno to wyglądać następująco: `C:\Progra~1\Java\jdk1.8.0_241` (wskazując na dowolną wersję środowiska Java zainstalowaną na komputerze lokalnym).
    2. Dołącz `%HADOOP_HOME%\share\hadoop\tools\lib\*` do `HADOOP_CLASSPATH` .
    Ostatni `hadoop-env.cmd` plik powinien wyglądać następująco:

    ![Końcowy plik Hadoop-ENV. cmd](./media/connect-external-sources/hadoop-env.png)

## <a name="configure-your-storage-account-in-hadoop"></a>Konfigurowanie konta magazynu w usłudze Hadoop

1. Otwórz konto magazynu ADLS generacji 2 lub WASB, z którym chcesz nawiązać połączenie za pośrednictwem [Azure Portal](https://portal.azure.com) i Otwórz panel **klucze dostępu** w bloku **Ustawienia** , a następnie skopiuj wartość **klucz** z w obszarze Klucz1.
2. Teraz w celu skonfigurowania usługi Hadoop w celu uzyskania dostępu do konta ADLS Gen2 należy edytować `core-site.xml` plik (znajdujący się w `%HADOOP_HOME%\etc\hadoop\` pliku) zawierający konfigurację całego klastra. Dodaj następujące właściwości wewnątrz `<configuration>` tagów w tym pliku:

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

    Jeśli próbujesz nawiązać połączenie z kontem WASB, Zastąp ciąg nazwą `dfs` `blob` właściwości. Na przykład `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.
3. Możesz przetestować łączność z kontem magazynu z poziomu usługi Hadoop, uruchamiając następujące polecenie w `%HADOOP_HOME%` katalogu:

    ```bash
    bin\hdfs dfs -ls <URI to your account>
    ```

Powinno to spowodować wyświetlenie listy wszystkich plików/folderów w ścieżce udostępnionej przez identyfikator URI.

> [!NOTE]
> Format do uzyskania identyfikatora URI dla konta magazynu jest następujący:
>
> ```
> For ADLS: abfs[s]://<file_system>@<account_name>.dfs.core.windows.net/<path>/<file_name>
> For WASB: wasb[s]://<file_system>@<account_name>.blob.core.windows.net/<path>/<file_name>
> ```

## <a name="connect-to-your-storage-account"></a>Nawiązywanie połączenia z kontem magazynu

1. Jeśli powyższe polecenie będzie działało, możesz teraz przejść do korzystania z tego konta magazynu za pomocą platformy Spark. Najpierw uruchom polecenie `hadoop classpath` z wiersza polecenia `%HADOOP_HOME%` i skopiuj dane wyjściowe.
2. Ustaw dane wyjściowe polecenia Run w kroku 1 do wartości zmiennej środowiskowej `SPARK_DIST_CLASSPATH` .
3. Teraz powinno być możliwe uzyskanie dostępu do konta magazynu ADLS lub WASB za pośrednictwem platformy Spark .NET przy użyciu identyfikatora URI ABFS, jak pokazano w poniższym przykładzie poniżej. (W tym przykładzie użyto standardowego [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) przykładowego pliku dostarczonego z każdą instalacją Apache Spark):

    ```csharp
    SparkSession spark = SparkSession
       .Builder()
       .AppName("Connect to Azure Storage locally")
       .GetOrCreate();
    DataFrame df = spark.Read().Json("wasbs://file_system@account_name.blob.core.windows.net/path/people.json");
    //DataFrame df = spark.Read().Json("abfss://file_system@account_name.dfs.core.windows.net/path/file.json");
    df.Show();
    ```

    Wynik jest wyświetlany jako ramka danych ( `df` ), jak pokazano poniżej:

    ```text
    +----+-------+
    | age|   name|
    +----+-------+
    |null|Michael|
    |  30|   Andy|
    |  19| Justin|
    +----+-------+
    ```
