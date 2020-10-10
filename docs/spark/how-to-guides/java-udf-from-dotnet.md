---
title: Wywołaj środowisko Java UDF z platformy .NET dla aplikacji Apache Spark
description: Dowiedz się, jak wywołać UDF języka Java z poziomu aplikacji .NET for Apache Spark.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: e309a1e8cda2a559f300a07155c005677db85945
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877919"
---
# <a name="call-a-java-udf-from-your-net-for-apache-spark-application"></a>Wywoływanie formatu UDF języka Java z aplikacji .NET dla Apache Spark

W tym artykule dowiesz się, jak wywołać funkcję Java User-Defined (UDF) z poziomu aplikacji [.net for Apache Spark](https://github.com/dotnet/spark) .

1. Jak zdefiniować UDF języka Java i skompilować je do komputera jar — ten krok nie jest konieczny, jeśli masz już zdefiniowany plik UDF w pliku JAR. W takim przypadku wystarczy, że jest to pełna nazwa funkcji UDF, łącznie z pakietem.
2. Zarejestruj i Wywołaj kod UDF języka Java w aplikacji .NET dla Apache Spark.

## <a name="define-and-compile-your-java-udfs"></a>Definiowanie i kompilowanie środowiska Java UDF

1. Utwórz projekt Maven lub SBT i Dodaj następujące zależności do pliku konfiguracji projektu:
    1. `org.apache.spark.spark-core_2.11.<version>`
    2. `org.apache.spark.spark-sql_2.11.<version>`
2. Zdefiniuj system plików UDF w języku Java, implementując [odpowiedni interfejs](https://github.com/apache/spark/blob/master/sql/core/src/main/java/org/apache/spark/sql/api/java/UDF1.java) (zgodnie z podpisem UDF) i importując odpowiedni pakiet, jak pokazano poniżej w prostym przykładzie

    ```java
    package com.ScalaUdf.app; // Name of package where UDF is defined
    import org.apache.spark.sql.api.java.UDF1; // UDF interface to implement

    public class JavaUdf implements UDF1<Integer, Integer> { // Name of the Java UDF
        private static final int serialVersionUID = 1;
        @Override
        public Integer call(Integer num) throws Exception { // Define logic of UDF
            return (num + 5);
        }
    }
    ```

3. Kompiluj i Pakuj projekt, aby utworzyć i plik wykonywalny jar `UdfApp-0.0.1.jar` .

## <a name="register-and-call-java-udfs-in-net-for-apache-spark"></a>Zarejestruj i Wywołaj środowisko Java UDF na platformie .NET dla Apache Spark

1. Użyj [`RegisterJava`](https://github.com/dotnet/spark/blob/8dcdcdc7c60d5f42cba5a90f1346d854ab5bf7bb/src/csharp/Microsoft.Spark/Sql/UDFRegistration.cs#L424) interfejsu API, aby zarejestrować system plików UDF w języku Java przy użyciu platformy Spark SQL.
2. Zarejestruj się, `DataFrame` na którym chcesz wywołać system plików UDF jako tabelę SQL przy użyciu [`CreateOrReplaceTempView`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L982) funkcji.
3. Użyj polecenia `SparkSession.Sql` , aby wywołać funkcję UDF w widoku tabeli przy użyciu platformy Spark SQL.
Podstawowy przykład ilustrujący powyższe kroki:

    ```csharp
    class Program
    {
        static void Main()
        {
            SparkSession spark = SparkSession
                .Builder()
                .AppName("Scala/Java UDFs from .NET for Apache Spark")
                .GetOrCreate();
            spark.Udf().RegisterJava<int>("udfAdd5", "com.ScalaUdf.app.JavaUdf"); // Register your Java UDF as 'udfAdd5'
            DataFrame df = spark.CreateDataFrame(new int[] { 2, 5 });
            df.CreateOrReplaceTempView("numbersData"); // Create an SQL table from the DataFrame `df`
            DataFrame dfUdf = spark.Sql("SELECT udfAdd5(_1) As Result FROM numbersData"); // Call the registered UDF on the table
            dfUdf.Show();
            spark.Stop();
        }
    }
    ```

4. Prześlij tę aplikację za pomocą `spark-submit` przekazania wcześniej skompilowanego pliku UDF w języku Java przy użyciu `--jars` opcji:

    ```bash
    spark-submit --master local --jars UdfApp-0.0.1.jar --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-3.0.x-0.12.1.jar InterRuntimeUDFs.exe
    ```

    Wynikowa `dfUdf` ramka danych ma numer 5 dodany do każdego wiersza w kolumnie wejściowej, zgodnie z definicją w `JavaUdf` :

    ```text
    +-------+
    | Result|
    +-------+
    |      7|
    |     10|
    +-------+
    ```

## <a name="call-net-udf-from-scala-or-python-in-apache-spark"></a>Wywołaj funkcję UDF platformy .NET z Scala lub Python w Apache Spark

Możesz również zarejestrować i wywołać UDF języka C# z aplikacji Apache Spark, która została zapisywana w Scala lub Python przy użyciu [Narzędzia sparkdotnetudf Open Source](https://github.com/imback82/sparkdotnetudf).
