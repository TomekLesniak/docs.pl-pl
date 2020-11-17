---
title: Tworzenie aplikacji platformy .NET dla Apache Spark w systemie Windows
description: Dowiedz się, jak utworzyć platformę .NET dla aplikacji Apache Spark w systemie Windows.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: how-to
ms.openlocfilehash: 8f197c0050d149ed03e328e72868ad4ba2f728c1
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688114"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a><span data-ttu-id="8c607-103">Dowiedz się, jak skompilować aplikację platformy .NET dla Apache Spark w systemie Windows</span><span class="sxs-lookup"><span data-stu-id="8c607-103">Learn how to build your .NET for Apache Spark application on Windows</span></span>

<span data-ttu-id="8c607-104">W tym artykule przedstawiono sposób kompilowania aplikacji platformy .NET dla Apache Spark w systemie Windows.</span><span class="sxs-lookup"><span data-stu-id="8c607-104">This article teaches you how to build your .NET for Apache Spark applications on Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c607-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="8c607-105">Prerequisites</span></span>

<span data-ttu-id="8c607-106">Jeśli masz już wszystkie poniższe wymagania wstępne, przejdź do kroków [kompilacji](#build) .</span><span class="sxs-lookup"><span data-stu-id="8c607-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

  1. <span data-ttu-id="8c607-107">Pobierz i zainstaluj **[zestaw .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1)** — Instalacja zestawu SDK spowoduje dodanie `dotnet` łańcucha narzędzi do ścieżki.</span><span class="sxs-lookup"><span data-stu-id="8c607-107">Download and install the **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1)** - installing the SDK will add the `dotnet` toolchain to your path.</span></span> <span data-ttu-id="8c607-108">Obsługiwane są programy .NET Core 2,1, 2,2 i 3,1.</span><span class="sxs-lookup"><span data-stu-id="8c607-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>
  2. <span data-ttu-id="8c607-109">Zainstaluj **[program Visual Studio 2019](https://www.visualstudio.com/downloads/)** (wersja 16,3 lub nowsza).</span><span class="sxs-lookup"><span data-stu-id="8c607-109">Install **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (Version 16.3 or later).</span></span> <span data-ttu-id="8c607-110">Wersja społeczności jest całkowicie bezpłatna.</span><span class="sxs-lookup"><span data-stu-id="8c607-110">The Community version is completely free.</span></span> <span data-ttu-id="8c607-111">Podczas konfigurowania instalacji należy uwzględnić następujące składniki:</span><span class="sxs-lookup"><span data-stu-id="8c607-111">When configuring your installation, include these components at minimum:</span></span>
     * <span data-ttu-id="8c607-112">Programowanie aplikacji klasycznych dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="8c607-112">.NET desktop development</span></span>
       * <span data-ttu-id="8c607-113">Wszystkie wymagane składniki</span><span class="sxs-lookup"><span data-stu-id="8c607-113">All Required Components</span></span>
         * <span data-ttu-id="8c607-114">Narzędzia programistyczne .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="8c607-114">.NET Framework 4.6.1 Development Tools</span></span>
     * <span data-ttu-id="8c607-115">Programowanie dla wielu platform w środowisku .NET Core</span><span class="sxs-lookup"><span data-stu-id="8c607-115">.NET Core cross-platform development</span></span>
       * <span data-ttu-id="8c607-116">Wszystkie wymagane składniki</span><span class="sxs-lookup"><span data-stu-id="8c607-116">All Required Components</span></span>
  3. <span data-ttu-id="8c607-117">Zainstaluj **[środowisko Java 1,8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span><span class="sxs-lookup"><span data-stu-id="8c607-117">Install **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span></span>
     - <span data-ttu-id="8c607-118">Wybierz odpowiednią wersję systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="8c607-118">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="8c607-119">Na przykład *jdk-8u201-windows-x64.exe* dla komputera z systemem Windows x64.</span><span class="sxs-lookup"><span data-stu-id="8c607-119">For example, *jdk-8u201-windows-x64.exe* for Windows x64 machine.</span></span>
     - <span data-ttu-id="8c607-120">Zainstaluj program przy użyciu Instalatora i sprawdź, czy można uruchomić go `java` z poziomu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="8c607-120">Install using the installer and verify you are able to run `java` from your command line.</span></span>
  4. <span data-ttu-id="8c607-121">Zainstaluj program **[Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi)**.</span><span class="sxs-lookup"><span data-stu-id="8c607-121">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>
     - <span data-ttu-id="8c607-122">Pobierz [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).</span><span class="sxs-lookup"><span data-stu-id="8c607-122">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).</span></span>
     - <span data-ttu-id="8c607-123">Wyodrębnij do katalogu lokalnego.</span><span class="sxs-lookup"><span data-stu-id="8c607-123">Extract to a local directory.</span></span> <span data-ttu-id="8c607-124">Na przykład \* C:\bin\apache-Maven-3.6.0 \* .</span><span class="sxs-lookup"><span data-stu-id="8c607-124">For example, \*C:\bin\apache-maven-3.6.0\*.</span></span>
     - <span data-ttu-id="8c607-125">Dodaj Maven Apache do [zmiennej środowiskowej PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="8c607-125">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="8c607-126">Na przykład *C:\bin\apache-Maven-3.6.0\bin*.</span><span class="sxs-lookup"><span data-stu-id="8c607-126">For example, *C:\bin\apache-maven-3.6.0\bin*.</span></span>
     - <span data-ttu-id="8c607-127">Sprawdź, czy możesz uruchamiać `mvn` z poziomu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="8c607-127">Verify you are able to run `mvn` from your command-line.</span></span>
  5. <span data-ttu-id="8c607-128">Zainstaluj **[Apache Spark 2.3 +](https://spark.apache.org/downloads.html)**.</span><span class="sxs-lookup"><span data-stu-id="8c607-128">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
     - <span data-ttu-id="8c607-129">Pobierz [Apache Spark 2.3 +](https://spark.apache.org/downloads.html) i wyodrębnij go do folderu lokalnego (na przykład *C:\bin\spark-3.0.1-bin-hadoop2.7 \* ) przy użyciu [7-zip](https://www.7-zip.org/). (Obsługiwane wersje platformy Spark to 2,3.*, 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 i 3.0.1)</span><span class="sxs-lookup"><span data-stu-id="8c607-129">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (for example, *C:\bin\spark-3.0.1-bin-hadoop2.7\*) using [7-zip](https://www.7-zip.org/). (The supported spark versions are 2.3.*, 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 and 3.0.1)</span></span>
     - <span data-ttu-id="8c607-130">Dodaj [nową zmienną środowiskową](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` .</span><span class="sxs-lookup"><span data-stu-id="8c607-130">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`.</span></span> <span data-ttu-id="8c607-131">Na przykład \* C:\bin\spark-3.0.1-bin-hadoop2.7 \* .</span><span class="sxs-lookup"><span data-stu-id="8c607-131">For example, \*C:\bin\spark-3.0.1-bin-hadoop2.7\*.</span></span>

       ```powershell
       set SPARK_HOME=C:\bin\spark-3.0.1-bin-hadoop2.7\
       ```

     - <span data-ttu-id="8c607-132">Dodaj Apache Spark do [zmiennej środowiskowej PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="8c607-132">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="8c607-133">Na przykład *C:\bin\spark-3.0.1-bin-hadoop2.7\bin*.</span><span class="sxs-lookup"><span data-stu-id="8c607-133">For example, *C:\bin\spark-3.0.1-bin-hadoop2.7\bin*.</span></span>

       ```powershell
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```

     - <span data-ttu-id="8c607-134">Sprawdź, czy możesz uruchamiać `spark-shell` z poziomu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="8c607-134">Verify you are able to run `spark-shell` from your command-line.</span></span>
        <span data-ttu-id="8c607-135">Przykładowe dane wyjściowe konsoli:</span><span class="sxs-lookup"><span data-stu-id="8c607-135">Sample console output:</span></span>

        ```output
        Welcome to
              ____              __
             / __/__  ___ _____/ /__
            _\ \/ _ \/ _ `/ __/  '_/
           /___/ .__/\_,_/_/ /_/\_\   version 3.0.1
              /_/

        Using Scala version 2.12.10 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201)
        Type in expressions to have them evaluated.
        Type :help for more information.

        scala> sc
        res0: org.apache.spark.SparkContext = org.apache.spark.SparkContext@6eaa6b0c
        ```

        </details>

  6. <span data-ttu-id="8c607-136">Zainstaluj **[WinUtils](https://github.com/steveloughran/winutils)**.</span><span class="sxs-lookup"><span data-stu-id="8c607-136">Install **[WinUtils](https://github.com/steveloughran/winutils)**.</span></span>
     - <span data-ttu-id="8c607-137">Pobierz `winutils.exe` plik binarny z [repozytorium WinUtils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="8c607-137">Download `winutils.exe` binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="8c607-138">Należy wybrać wersję usługi Hadoop, z którą została skompilowana dystrybucja platformy Spark.</span><span class="sxs-lookup"><span data-stu-id="8c607-138">You should select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="8c607-139">W przypadku usługi exammple Użyj usługi Hadoop-2.7.1 dla platformy Spark 3.0.1.</span><span class="sxs-lookup"><span data-stu-id="8c607-139">For exammple, use hadoop-2.7.1 for Spark 3.0.1.</span></span>
     - <span data-ttu-id="8c607-140">Zapisz `winutils.exe` plik binarny w wybranym katalogu.</span><span class="sxs-lookup"><span data-stu-id="8c607-140">Save `winutils.exe` binary to a directory of your choice.</span></span> <span data-ttu-id="8c607-141">Na przykład *C:\hadoop\bin*.</span><span class="sxs-lookup"><span data-stu-id="8c607-141">For example, *C:\hadoop\bin*.</span></span>
     - <span data-ttu-id="8c607-142">Ustaw `HADOOP_HOME` , aby odzwierciedlał katalog z winutils.exe (bez bin).</span><span class="sxs-lookup"><span data-stu-id="8c607-142">Set `HADOOP_HOME` to reflect the directory with winutils.exe (without bin).</span></span> <span data-ttu-id="8c607-143">Na przykład za pomocą wiersza polecenia:</span><span class="sxs-lookup"><span data-stu-id="8c607-143">For instance, using command-line:</span></span>

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - <span data-ttu-id="8c607-144">Ustaw zmienną środowiskową PATH, która ma zostać dołączona `%HADOOP_HOME%\bin` .</span><span class="sxs-lookup"><span data-stu-id="8c607-144">Set PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span> <span data-ttu-id="8c607-145">Na przykład za pomocą wiersza polecenia:</span><span class="sxs-lookup"><span data-stu-id="8c607-145">For instance, using command line:</span></span>

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

<span data-ttu-id="8c607-146">Przed przejściem do następnej sekcji upewnij się, że masz możliwość uruchomienia `dotnet` , `java` , `mvn` ,, `spark-shell` z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="8c607-146">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span> <span data-ttu-id="8c607-147">Czy istnieje lepszy sposób?</span><span class="sxs-lookup"><span data-stu-id="8c607-147">Feel there is a better way?</span></span> <span data-ttu-id="8c607-148">[Otwórz problem](https://github.com/dotnet/spark/issues) i śmiało, aby współtworzyć.</span><span class="sxs-lookup"><span data-stu-id="8c607-148">[Open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

> [!NOTE]
> <span data-ttu-id="8c607-149">Jeśli wszystkie zmienne środowiskowe zostały zaktualizowane, może być wymagane nowe wystąpienie wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="8c607-149">A new instance of the command line may be required if any environment variables were updated.</span></span>

## <a name="build"></a><span data-ttu-id="8c607-150">Kompilacja</span><span class="sxs-lookup"><span data-stu-id="8c607-150">Build</span></span>

<span data-ttu-id="8c607-151">W pozostałej części tego przewodnika konieczne będzie sklonowanie repozytorium .NET for Apache Spark na komputerze.</span><span class="sxs-lookup"><span data-stu-id="8c607-151">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine.</span></span> <span data-ttu-id="8c607-152">Można wybrać dowolną lokalizację dla sklonowanego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="8c607-152">You can choose any location for the cloned repository.</span></span> <span data-ttu-id="8c607-153">Na przykład \* C:\github\dotnet-Spark \* .</span><span class="sxs-lookup"><span data-stu-id="8c607-153">For example, \*C:\github\dotnet-spark\*.</span></span>

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a><span data-ttu-id="8c607-154">Kompiluj platformę .NET dla Apache Spark warstwy rozszerzeń Scala</span><span class="sxs-lookup"><span data-stu-id="8c607-154">Build .NET for Apache Spark Scala extensions layer</span></span>

<span data-ttu-id="8c607-155">Gdy przesyłasz aplikację .NET, platforma .NET dla Apache Spark ma niezbędną logikę zapisaną w Scala, która informuje Apache Spark, jak obsługiwać żądania (na przykład żądanie utworzenia nowej sesji platformy Spark, żądanie przeniesienia danych z platformy .NET do strony JVM itp.).</span><span class="sxs-lookup"><span data-stu-id="8c607-155">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (for example, request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="8c607-156">Tę logikę można znaleźć w [kodzie źródłowym programu .net for Spark Scala](https://github.com/dotnet/spark/tree/master/src/scala).</span><span class="sxs-lookup"><span data-stu-id="8c607-156">This logic can be found in the [.NET for Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span></span>

<span data-ttu-id="8c607-157">Bez względu na to, czy używasz .NET Framework, czy platformy .NET Core, musisz skompilować platformę .NET dla Apache Spark Scala warstwy rozszerzeń:</span><span class="sxs-lookup"><span data-stu-id="8c607-157">Regardless of whether you are using .NET Framework or .NET Core, you will need to build the .NET for Apache Spark Scala extension layer:</span></span>

```powershell
cd src\scala
mvn clean package
```

<span data-ttu-id="8c607-158">Powinna zostać wyświetlona JARs utworzona dla obsługiwanych wersji platformy Spark:</span><span class="sxs-lookup"><span data-stu-id="8c607-158">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2-3\target\microsoft-spark-2-3_2.11-<spark-dotnet-version>.jar`
* `microsoft-spark-2-4\target\microsoft-spark-2-4_2.11-<spark-dotnet-version>.jar`
* `microsoft-spark-3-0\target\microsoft-spark-3-0_2.12-<spark-dotnet-version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a><span data-ttu-id="8c607-159">Tworzenie przykładowych aplikacji platformy .NET dla platformy Spark</span><span class="sxs-lookup"><span data-stu-id="8c607-159">Build the .NET for Spark sample applications</span></span>

<span data-ttu-id="8c607-160">W tej sekcji opisano sposób tworzenia [przykładowych aplikacji](https://github.com/dotnet/spark/tree/master/examples) dla platformy .net dla Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="8c607-160">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/master/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="8c607-161">Te kroki ułatwią zrozumienie ogólnego procesu tworzenia aplikacji platformy .NET dla platformy Spark.</span><span class="sxs-lookup"><span data-stu-id="8c607-161">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

#### <a name="using-visual-studio-for-net-framework"></a><span data-ttu-id="8c607-162">Korzystanie z programu Visual Studio dla .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8c607-162">Using Visual Studio for .NET Framework</span></span>

  1. <span data-ttu-id="8c607-163">Otwórz `src\csharp\Microsoft.Spark.sln` w programie Visual Studio i skompiluj `Microsoft.Spark.CSharp.Examples` projekt w `examples` folderze (spowoduje to również skompilowanie projektu powiązań .NET).</span><span class="sxs-lookup"><span data-stu-id="8c607-163">Open `src\csharp\Microsoft.Spark.sln` in Visual Studio and build the `Microsoft.Spark.CSharp.Examples` project under the `examples` folder (this will in turn build the .NET bindings project as well).</span></span> <span data-ttu-id="8c607-164">Jeśli chcesz, możesz napisać własny kod w `Microsoft.Spark.Examples` projekcie ("input_file.json" w tym przykładzie jako plik JSON z danymi, dla których chcesz utworzyć ramkę danych):</span><span class="sxs-lookup"><span data-stu-id="8c607-164">If you want, you can write your own code in the `Microsoft.Spark.Examples` project (the 'input_file.json' in this example is a json file with the data you want to create the dataframe with):</span></span>
  
      ```csharp
        // Instantiate a session
        var spark = SparkSession
            .Builder()
            .AppName("Hello Spark!")
            .GetOrCreate();

        // Create initial DataFrame
        DataFrame df = spark.Read().Json(input_file.json);

        // Print schema
        df.PrintSchema();

        // Apply a filter and show results
        df.Filter(df["age"] > 21).Show();
      ```

     <span data-ttu-id="8c607-165">Po pomyślnym zakończeniu kompilacji zostaną wyświetlone odpowiednie pliki binarne utworzone w katalogu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="8c607-165">Once the build is successful, you will see the appropriate binaries produced in the output directory.</span></span>
     <span data-ttu-id="8c607-166">Przykładowe dane wyjściowe konsoli:</span><span class="sxs-lookup"><span data-stu-id="8c607-166">Sample console output:</span></span>

      ```powershell
            Directory: C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461


        Mode                LastWriteTime         Length Name
        ----                -------------         ------ ----
        -a----         3/6/2019  12:18 AM         125440 Apache.Arrow.dll
        -a----        3/16/2019  12:00 AM          13824 Microsoft.Spark.CSharp.Examples.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.CSharp.Examples.exe.config
        -a----        3/16/2019  12:00 AM           2720 Microsoft.Spark.CSharp.Examples.pdb
        -a----        3/16/2019  12:00 AM         143360 Microsoft.Spark.dll
        -a----        3/16/2019  12:00 AM          63388 Microsoft.Spark.pdb
        -a----        3/16/2019  12:00 AM          34304 Microsoft.Spark.Worker.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.Worker.exe.config
        -a----        3/16/2019  12:00 AM          11900 Microsoft.Spark.Worker.pdb
        -a----        3/16/2019  12:00 AM          23552 Microsoft.Spark.Worker.xml
        -a----        3/16/2019  12:00 AM         332363 Microsoft.Spark.xml
        ------------------------------------------- More framework files -------------------------------------
      ```

#### <a name="using-net-core-cli-for-net-core"></a><span data-ttu-id="8c607-167">Używanie interfejs wiersza polecenia platformy .NET Core dla platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="8c607-167">Using .NET Core CLI for .NET Core</span></span>

> [!NOTE]
> <span data-ttu-id="8c607-168">Obecnie pracujemy nad automatyzowaniem kompilacji platformy .NET Core dla platformy Spark .NET.</span><span class="sxs-lookup"><span data-stu-id="8c607-168">We are currently working on automating .NET Core builds for Spark .NET.</span></span> <span data-ttu-id="8c607-169">Do tego czasu będziemy wdzięczni za cierpliwość wykonywania niektórych czynności ręcznie.</span><span class="sxs-lookup"><span data-stu-id="8c607-169">Until then, we appreciate your patience in performing some of the steps manually.</span></span>

  1. <span data-ttu-id="8c607-170">Kompiluj proces roboczy:</span><span class="sxs-lookup"><span data-stu-id="8c607-170">Build the worker:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp3.1 -r win-x64
      ```

      <span data-ttu-id="8c607-171">Przykładowe dane wyjściowe konsoli:</span><span class="sxs-lookup"><span data-stu-id="8c607-171">Sample console output:</span></span>

      ```powershell
      PS C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker> dotnet publish -f netcoreapp3.1 -r win-x64
      Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 299.95 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 306.62 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\Microsoft.Spark.Worker.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.1\Microsoft.Spark.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\x64\Debug\netcoreapp3.1\win-x64\Microsoft.Spark.Worker.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\x64\Debug\netcoreapp3.1\win-x64\publish\
      ```

  2. <span data-ttu-id="8c607-172">Kompiluj przykłady:</span><span class="sxs-lookup"><span data-stu-id="8c607-172">Build the samples:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp3.1 -r win-x64
      ```

      <span data-ttu-id="8c607-173">Przykładowe dane wyjściowe konsoli:</span><span class="sxs-lookup"><span data-stu-id="8c607-173">Sample console output:</span></span>

      ```powershell
      PS C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples> dotnet publish -f netcoreapp3.1 -r win-x64
      Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 44.22 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 336.94 ms for C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\Microsoft.Spark.CSharp.Examples.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.1\Microsoft.Spark.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\x64\Debug\netcoreapp3.1\win-x64\Microsoft.Spark.CSharp.Examples.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\x64\Debug\netcoreapp3.1\win-x64\publish\
      ```

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="8c607-174">Uruchamianie przykładowych aplikacji platformy .NET dla platformy Spark</span><span class="sxs-lookup"><span data-stu-id="8c607-174">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="8c607-175">Po skompilowaniu przykładów, ich uruchomienie będzie możliwe `spark-submit` bez względu na to, czy jesteś ukierunkowany na .NET Framework czy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8c607-175">Once you build the samples, running them will be through `spark-submit` regardless of whether you are targeting .NET Framework or .NET Core.</span></span> <span data-ttu-id="8c607-176">Upewnij się, że wykonano sekcję [wymagania wstępne](#prerequisites) i zainstalowano Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="8c607-176">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

  1. <span data-ttu-id="8c607-177">Ustaw `DOTNET_WORKER_DIR` `PATH` zmienną środowiskową lub w celu uwzględnienia ścieżki, w której `Microsoft.Spark.Worker` Wygenerowano plik binarny (na przykład *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\x64\Debug\netcoreapp3.1\win-x64\publish* for .NET Core):</span><span class="sxs-lookup"><span data-stu-id="8c607-177">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\x64\Debug\netcoreapp3.1\win-x64\publish* for .NET Core):</span></span>

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\x64\Debug\netcoreapp3.1\win-x64\publish
      ```
  
  2. <span data-ttu-id="8c607-178">Otwórz program PowerShell i przejdź do katalogu, w którym Wygenerowano plik binarny aplikacji (na przykład *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\x64\Debug\netcoreapp3.1\win-x64\publish* for .NET Core):</span><span class="sxs-lookup"><span data-stu-id="8c607-178">Open PowerShell and go to the directory where your app binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\x64\Debug\netcoreapp3.1\win-x64\publish* for .NET Core):</span></span>

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\x64\Debug\netcoreapp3.1\win-x64\publish
      ```

  3. <span data-ttu-id="8c607-179">Uruchamianie aplikacji jest zgodne ze strukturą podstawową:</span><span class="sxs-lookup"><span data-stu-id="8c607-179">Running your app follows the basic structure:</span></span>

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     <span data-ttu-id="8c607-180">Oto kilka przykładów, które można uruchomić:</span><span class="sxs-lookup"><span data-stu-id="8c607-180">Here are some examples you can run:</span></span>

     - <span data-ttu-id="8c607-181">**[Microsoft.Spark.Examples.Sql.Batch. Prosty](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="8c607-181">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - <span data-ttu-id="8c607-182">**[Microsoft. Spark. przykłady. SQL. Streaming. StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="8c607-182">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - <span data-ttu-id="8c607-183">**[Microsoft. Spark. przykłady. SQL. Streaming. StructuredKafkaWordCount (Maven dostępny)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="8c607-183">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - <span data-ttu-id="8c607-184">**[Microsoft. Spark. przykłady. SQL. Streaming. StructuredKafkaWordCount (podano Jars)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="8c607-184">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```
