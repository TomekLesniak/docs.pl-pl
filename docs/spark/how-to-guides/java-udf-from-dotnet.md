---
title: Wywołaj środowisko Java UDF z platformy .NET dla aplikacji Apache Spark
description: Dowiedz się, jak wywołać UDF języka Java z poziomu aplikacji .NET for Apache Spark.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 17f0ff611e68a5dab2032f78ef75912f314d88a5
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688270"
---
# <a name="call-a-java-udf-from-your-net-for-apache-spark-application"></a><span data-ttu-id="d0ef8-103">Wywoływanie formatu UDF języka Java z aplikacji .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="d0ef8-103">Call a Java UDF from your .NET for Apache Spark application</span></span>

<span data-ttu-id="d0ef8-104">W tym artykule dowiesz się, jak wywołać funkcję Java User-Defined (UDF) z poziomu aplikacji [.net for Apache Spark](https://github.com/dotnet/spark) .</span><span class="sxs-lookup"><span data-stu-id="d0ef8-104">In this article, you learn how to call a Java User-Defined Function (UDF) from your [.NET for Apache Spark](https://github.com/dotnet/spark) application.</span></span>

1. <span data-ttu-id="d0ef8-105">Jak zdefiniować UDF języka Java i skompilować je do komputera jar — ten krok nie jest konieczny, jeśli masz już zdefiniowany plik UDF w pliku JAR.</span><span class="sxs-lookup"><span data-stu-id="d0ef8-105">How to define your Java UDFs and compile them into a jar - this step is not needed if you already have a UDF defined in a jar file.</span></span> <span data-ttu-id="d0ef8-106">W takim przypadku wystarczy, że jest to pełna nazwa funkcji UDF, łącznie z pakietem.</span><span class="sxs-lookup"><span data-stu-id="d0ef8-106">In which case, all you need is the full name of the UDF function including the package.</span></span>
2. <span data-ttu-id="d0ef8-107">Zarejestruj i Wywołaj kod UDF języka Java w aplikacji .NET dla Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="d0ef8-107">Register and call your Java UDF in your .NET for Apache Spark application.</span></span>

## <a name="define-and-compile-your-java-udfs"></a><span data-ttu-id="d0ef8-108">Definiowanie i kompilowanie środowiska Java UDF</span><span class="sxs-lookup"><span data-stu-id="d0ef8-108">Define and compile your Java UDFs</span></span>

1. <span data-ttu-id="d0ef8-109">Utwórz projekt Maven lub SBT i Dodaj następujące zależności do pliku konfiguracji projektu:</span><span class="sxs-lookup"><span data-stu-id="d0ef8-109">Create a Maven or SBT project and add the following dependencies into the project configuration file:</span></span>
    1. `org.apache.spark.spark-core_2.11.<version>`
    2. `org.apache.spark.spark-sql_2.11.<version>`
2. <span data-ttu-id="d0ef8-110">Zdefiniuj system plików UDF w języku Java, implementując [odpowiedni interfejs](https://github.com/apache/spark/blob/master/sql/core/src/main/java/org/apache/spark/sql/api/java/UDF1.java) (zgodnie z podpisem UDF) i importując odpowiedni pakiet, jak pokazano poniżej w prostym przykładzie</span><span class="sxs-lookup"><span data-stu-id="d0ef8-110">Define your Java UDF by implementing the [relevant interface](https://github.com/apache/spark/blob/master/sql/core/src/main/java/org/apache/spark/sql/api/java/UDF1.java) (according to your UDF's signature) and importing the relevant package as shown below in a simple example</span></span>

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

3. <span data-ttu-id="d0ef8-111">Kompiluj i Pakuj projekt, aby utworzyć i plik wykonywalny jar `UdfApp-0.0.1.jar` .</span><span class="sxs-lookup"><span data-stu-id="d0ef8-111">Compile and package your project to create and executable jar say `UdfApp-0.0.1.jar`.</span></span>

## <a name="register-and-call-java-udfs-in-net-for-apache-spark"></a><span data-ttu-id="d0ef8-112">Zarejestruj i Wywołaj środowisko Java UDF na platformie .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="d0ef8-112">Register and call Java UDFs in .NET for Apache Spark</span></span>

1. <span data-ttu-id="d0ef8-113">Użyj [`RegisterJava`](https://github.com/dotnet/spark/blob/8dcdcdc7c60d5f42cba5a90f1346d854ab5bf7bb/src/csharp/Microsoft.Spark/Sql/UDFRegistration.cs#L424) interfejsu API, aby zarejestrować system plików UDF w języku Java przy użyciu platformy Spark SQL.</span><span class="sxs-lookup"><span data-stu-id="d0ef8-113">Use the [`RegisterJava`](https://github.com/dotnet/spark/blob/8dcdcdc7c60d5f42cba5a90f1346d854ab5bf7bb/src/csharp/Microsoft.Spark/Sql/UDFRegistration.cs#L424) API to register your Java UDF with Spark SQL.</span></span>
2. <span data-ttu-id="d0ef8-114">Zarejestruj się, `DataFrame` na którym chcesz wywołać system plików UDF jako tabelę SQL przy użyciu [`CreateOrReplaceTempView`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L982) funkcji.</span><span class="sxs-lookup"><span data-stu-id="d0ef8-114">Register the `DataFrame` on which you want to call your UDF as an SQL Table using the [`CreateOrReplaceTempView`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L982) function.</span></span>
3. <span data-ttu-id="d0ef8-115">Użyj polecenia `SparkSession.Sql` , aby wywołać funkcję UDF w widoku tabeli przy użyciu platformy Spark SQL.</span><span class="sxs-lookup"><span data-stu-id="d0ef8-115">Use `SparkSession.Sql` to call the UDF on the table view using Spark SQL.</span></span>
<span data-ttu-id="d0ef8-116">Podstawowy przykład ilustrujący powyższe kroki:</span><span class="sxs-lookup"><span data-stu-id="d0ef8-116">A basic example to illustrate the above steps:</span></span>

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

4. <span data-ttu-id="d0ef8-117">Prześlij tę aplikację za pomocą `spark-submit` przekazania wcześniej skompilowanego pliku UDF w języku Java przy użyciu `--jars` opcji:</span><span class="sxs-lookup"><span data-stu-id="d0ef8-117">Submit this application using `spark-submit` by passing the previously compiled Java UDF jar through the `--jars` option:</span></span>

    ```bash
    spark-submit --master local --jars UdfApp-0.0.1.jar --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-2-4_2.11-1.0.0.jar InterRuntimeUDFs.exe
    ```

    <span data-ttu-id="d0ef8-118">Wynikowa `dfUdf` ramka danych ma numer 5 dodany do każdego wiersza w kolumnie wejściowej, zgodnie z definicją w `JavaUdf` :</span><span class="sxs-lookup"><span data-stu-id="d0ef8-118">The resultant `dfUdf` DataFrame had the number 5 added to each row of the input column as defined by `JavaUdf`:</span></span>

    ```text
    +-------+
    | Result|
    +-------+
    |      7|
    |     10|
    +-------+
    ```

## <a name="call-net-udf-from-scala-or-python-in-apache-spark"></a><span data-ttu-id="d0ef8-119">Wywołaj funkcję UDF platformy .NET z Scala lub Python w Apache Spark</span><span class="sxs-lookup"><span data-stu-id="d0ef8-119">Call .NET UDF from Scala or Python in Apache Spark</span></span>

<span data-ttu-id="d0ef8-120">Możesz również zarejestrować i wywołać UDF języka C# z aplikacji Apache Spark, która została zapisywana w Scala lub Python przy użyciu [Narzędzia sparkdotnetudf Open Source](https://github.com/imback82/sparkdotnetudf).</span><span class="sxs-lookup"><span data-stu-id="d0ef8-120">You can also register and invoke a C# UDF from an Apache Spark application written in Scala or Python using [the sparkdotnetudf open source tool](https://github.com/imback82/sparkdotnetudf).</span></span>
