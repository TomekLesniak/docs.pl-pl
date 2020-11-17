---
title: Wprowadzenie do platformy .NET dla Apache Spark
description: Dowiedz się, jak uruchomić aplikację .NET dla Apache Spark przy użyciu platformy .NET Core w systemach Windows, macOS i Ubuntu.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 16ccc8f40f290c4bc10f03d1f4d1b296b17f6b11
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687828"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="67d89-103">Samouczek: Rozpoczynanie pracy z platformą .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="67d89-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="67d89-104">W tym samouczku przedstawiono sposób uruchamiania aplikacji platformy .NET dla Apache Spark przy użyciu platformy .NET Core w systemach Windows, macOS i Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="67d89-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, macOS, and Ubuntu.</span></span>

<span data-ttu-id="67d89-105">Z tego samouczka dowiesz się, jak wykonywać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="67d89-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="67d89-106">Przygotuj środowisko dla platformy .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="67d89-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="67d89-107">Napisz swoją pierwszą aplikację .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="67d89-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="67d89-108">Kompilowanie i uruchamianie aplikacji platformy .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="67d89-108">Build and run your .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="67d89-109">Przygotowywanie środowiska</span><span class="sxs-lookup"><span data-stu-id="67d89-109">Prepare your environment</span></span>

<span data-ttu-id="67d89-110">Przed rozpoczęciem pisania aplikacji należy skonfigurować niektóre zależności wymagane wstępnie.</span><span class="sxs-lookup"><span data-stu-id="67d89-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="67d89-111">Jeśli można uruchomić `dotnet` polecenie, `java` w `spark-shell` środowisku wiersza polecenia, środowisko jest już przygotowane i można przejść do następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="67d89-111">If you can run `dotnet`, `java`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="67d89-112">Jeśli nie można uruchomić żadnego lub wszystkich poleceń, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="67d89-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="67d89-113">1. Zainstaluj platformę .NET</span><span class="sxs-lookup"><span data-stu-id="67d89-113">1. Install .NET</span></span>

<span data-ttu-id="67d89-114">Aby rozpocząć tworzenie aplikacji platformy .NET, należy pobrać i zainstalować zestaw .NET SDK (Software Development Kit).</span><span class="sxs-lookup"><span data-stu-id="67d89-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="67d89-115">Pobierz i zainstaluj [zestaw .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="67d89-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="67d89-116">Zainstalowanie zestawu SDK dodaje `dotnet` łańcucha narzędzi do ścieżki.</span><span class="sxs-lookup"><span data-stu-id="67d89-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="67d89-117">Po zainstalowaniu zestaw .NET Core SDK Otwórz nowy wiersz polecenia lub terminal i uruchom polecenie `dotnet` .</span><span class="sxs-lookup"><span data-stu-id="67d89-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="67d89-118">Jeśli polecenie jest uruchamiane i drukuje informacje o sposobach korzystania z programu dotnet, można przejść do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="67d89-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="67d89-119">Jeśli `'dotnet' is not recognized as an internal or external command` wystąpi błąd, upewnij się, że otwarto **Nowy** wiersz polecenia lub terminal przed uruchomieniem polecenia.</span><span class="sxs-lookup"><span data-stu-id="67d89-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="67d89-120">2. Zainstaluj środowisko Java</span><span class="sxs-lookup"><span data-stu-id="67d89-120">2. Install Java</span></span>

<span data-ttu-id="67d89-121">Zainstaluj [środowisko Java 8,1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) dla systemu Windows i MacOS lub [OpenJDK 8](https://openjdk.java.net/install/) dla Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="67d89-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and macOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="67d89-122">Wybierz odpowiednią wersję systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="67d89-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="67d89-123">Na przykład wybierz **jdk-8u201-windows-x64.exe** dla komputera z systemem Windows x64 (jak pokazano poniżej) lub **JDK-8u231-macosx-x64. dmg** dla macOS.</span><span class="sxs-lookup"><span data-stu-id="67d89-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for macOS.</span></span> <span data-ttu-id="67d89-124">Następnie użyj polecenia, `java` Aby zweryfikować instalację.</span><span class="sxs-lookup"><span data-stu-id="67d89-124">Then, use the command `java` to verify the installation.</span></span>

![Pobieranie w języku Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="67d89-126">3. Zainstaluj oprogramowanie do kompresji</span><span class="sxs-lookup"><span data-stu-id="67d89-126">3. Install compression software</span></span>

<span data-ttu-id="67d89-127">Apache Spark jest pobierany jako skompresowany plik TGZ.</span><span class="sxs-lookup"><span data-stu-id="67d89-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="67d89-128">Użyj programu wyodrębniania, takiego jak [7-zip](https://www.7-zip.org/) lub [WinZip](https://www.winzip.com/), aby wyodrębnić plik.</span><span class="sxs-lookup"><span data-stu-id="67d89-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="67d89-129">4. Zainstaluj Apache Spark</span><span class="sxs-lookup"><span data-stu-id="67d89-129">4. Install Apache Spark</span></span>

<span data-ttu-id="67d89-130">[Pobierz i zainstaluj Apache Spark](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="67d89-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="67d89-131">Należy wybrać jedną z wersji 2,3. \* lub 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 lub 3.0.1 (.NET dla Apache Spark nie jest zgodna z innymi wersjami Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="67d89-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0, or 3.0.1 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="67d89-132">Polecenia używane w poniższych krokach założono, że zostały [pobrane i zainstalowane Apache Spark 3.0.1](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="67d89-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 3.0.1](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="67d89-133">Jeśli chcesz użyć innej wersji, Zamień **3.0.1** na odpowiedni numer wersji.</span><span class="sxs-lookup"><span data-stu-id="67d89-133">If you wish to use a different version, replace **3.0.1** with the appropriate version number.</span></span> <span data-ttu-id="67d89-134">Następnie wyodrębnij plik **. tar** i pliki Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="67d89-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="67d89-135">Aby wyodrębnić zagnieżdżony plik **tar** :</span><span class="sxs-lookup"><span data-stu-id="67d89-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="67d89-136">Znajdź pobrany plik **Spark-3.0.1-bin-Hadoop 2.7. tgz** .</span><span class="sxs-lookup"><span data-stu-id="67d89-136">Locate the **spark-3.0.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="67d89-137">Kliknij prawym przyciskiem myszy plik i wybierz **7-zip-> Wyodrębnij tutaj**.</span><span class="sxs-lookup"><span data-stu-id="67d89-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="67d89-138">**Spark-3.0.1-bin-Hadoop 2.7. tar** jest tworzony obok pobranego pliku **. tgz** .</span><span class="sxs-lookup"><span data-stu-id="67d89-138">**spark-3.0.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="67d89-139">Aby wyodrębnić pliki Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="67d89-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="67d89-140">Kliknij prawym przyciskiem myszy pozycję **Spark-3.0.1-bin-Hadoop 2.7. tar** i wybierz pozycję **7-zip-> Wyodrębnianie plików...**</span><span class="sxs-lookup"><span data-stu-id="67d89-140">Right-click on **spark-3.0.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="67d89-141">Wprowadź **C:\Bin** w polu **Wyodrębnij do** .</span><span class="sxs-lookup"><span data-stu-id="67d89-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="67d89-142">Usuń zaznaczenie pola wyboru pod polem **Wyodrębnij do** .</span><span class="sxs-lookup"><span data-stu-id="67d89-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="67d89-143">Wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="67d89-143">Select **OK**.</span></span>
* <span data-ttu-id="67d89-144">Pliki Apache Spark są wyodrębniane do C:\bin\spark-3.0.1-bin-hadoop2.7</span><span class="sxs-lookup"><span data-stu-id="67d89-144">The Apache Spark files are extracted to C:\bin\spark-3.0.1-bin-hadoop2.7</span></span>\

![Zainstaluj platformę Spark](./media/spark-extract-with-7-zip.png)

<span data-ttu-id="67d89-146">Uruchom następujące polecenia, aby ustawić zmienne środowiskowe używane do lokalizowania Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="67d89-146">Run the following commands to set the environment variables used to locate Apache Spark.</span></span> <span data-ttu-id="67d89-147">W systemie Windows pamiętaj, aby uruchomić wiersz polecenia w trybie administratora.</span><span class="sxs-lookup"><span data-stu-id="67d89-147">On Windows, make sure to run the command prompt in administrator mode.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="67d89-148">Windows</span><span class="sxs-lookup"><span data-stu-id="67d89-148">Windows</span></span>](#tab/windows)

```console
setx /M HADOOP_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M SPARK_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M PATH "%PATH%;%HADOOP_HOME%;%SPARK_HOME%\bin"
```

#### <a name="maclinux"></a>[<span data-ttu-id="67d89-149">System Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="67d89-149">Mac/Linux</span></span>](#tab/linux)

```bash
export SPARK_HOME=~/bin/spark-3.0.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

---

<span data-ttu-id="67d89-150">Po zainstalowaniu wszystkiego i ustawieniu zmiennych środowiskowych Otwórz **Nowy** wiersz polecenia lub terminal i uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="67d89-150">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

```text
spark-submit --version
```

<span data-ttu-id="67d89-151">Jeśli polecenie jest uruchamiane i drukuje informacje o wersji, można przejść do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="67d89-151">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="67d89-152">Jeśli `'spark-submit' is not recognized as an internal or external command` wystąpi błąd, upewnij się, że otwarto **Nowy** wiersz polecenia.</span><span class="sxs-lookup"><span data-stu-id="67d89-152">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="67d89-153">5. Zainstaluj program .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="67d89-153">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="67d89-154">Pobierz wydanie [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) z platformy .net dla Apache Spark GitHub.</span><span class="sxs-lookup"><span data-stu-id="67d89-154">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="67d89-155">Na przykład jeśli korzystasz z komputera z systemem Windows i planujesz używać platformy .NET Core, [Pobierz wydanie systemu Windows x64 netcoreapp 3.1](https://github.com/dotnet/spark/releases).</span><span class="sxs-lookup"><span data-stu-id="67d89-155">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases).</span></span>

<span data-ttu-id="67d89-156">Aby wyodrębnić pakiet Microsoft. Spark. Worker:</span><span class="sxs-lookup"><span data-stu-id="67d89-156">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="67d89-157">Znajdź pobrany plik **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-1.0.0.zip** .</span><span class="sxs-lookup"><span data-stu-id="67d89-157">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-1.0.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="67d89-158">Kliknij prawym przyciskiem myszy i wybierz **7-zip-> Wyodrębnianie plików.**...</span><span class="sxs-lookup"><span data-stu-id="67d89-158">Right-click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="67d89-159">Wprowadź **C:\Bin** w polu **Wyodrębnij do** .</span><span class="sxs-lookup"><span data-stu-id="67d89-159">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="67d89-160">Usuń zaznaczenie pola wyboru pod polem **Wyodrębnij do** .</span><span class="sxs-lookup"><span data-stu-id="67d89-160">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="67d89-161">Wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="67d89-161">Select **OK**.</span></span>

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="67d89-162">6. Zainstaluj WinUtils (tylko system Windows)</span><span class="sxs-lookup"><span data-stu-id="67d89-162">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="67d89-163">Platforma .NET dla Apache Spark wymaga zainstalowania WinUtils razem z Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="67d89-163">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="67d89-164">[Pobierz winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="67d89-164">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="67d89-165">Następnie skopiuj WinUtils do **C:\bin\spark-3.0.1-bin-hadoop2.7\bin**.</span><span class="sxs-lookup"><span data-stu-id="67d89-165">Then, copy WinUtils into **C:\bin\spark-3.0.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="67d89-166">Jeśli używasz innej wersji usługi Hadoop, która ma adnotację na końcu nazwy folderu instalacji platformy Spark, [Wybierz wersję WinUtils](https://github.com/steveloughran/winutils) zgodną z wersją usługi Hadoop.</span><span class="sxs-lookup"><span data-stu-id="67d89-166">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="67d89-167">7. Ustaw DOTNET_WORKER_DIR i sprawdź zależności</span><span class="sxs-lookup"><span data-stu-id="67d89-167">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="67d89-168">Uruchom jedno z następujących poleceń, aby ustawić `DOTNET_WORKER_DIR` zmienną środowiskową, która jest używana przez aplikacje platformy .NET do lokalizowania danych binarnych programu .NET dla Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="67d89-168">Run one of the following commands to set the `DOTNET_WORKER_DIR` environment variable, which is used by .NET apps to locate .NET for Apache Spark worker binaries.</span></span> <span data-ttu-id="67d89-169">Upewnij się, że zastąpisz do katalogu, do którego `<PATH-DOTNET_WORKER_DIR>` został pobrany i wyodrębniony `Microsoft.Spark.Worker` .</span><span class="sxs-lookup"><span data-stu-id="67d89-169">Make sure to replace `<PATH-DOTNET_WORKER_DIR>` with the directory where you downloaded and extracted the `Microsoft.Spark.Worker`.</span></span> <span data-ttu-id="67d89-170">W systemie Windows pamiętaj, aby uruchomić wiersz polecenia w trybie administratora.</span><span class="sxs-lookup"><span data-stu-id="67d89-170">On Windows, make sure to run the command prompt in administrator mode.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="67d89-171">Windows</span><span class="sxs-lookup"><span data-stu-id="67d89-171">Windows</span></span>](#tab/windows)

```console
setx /M DOTNET_WORKER_DIR <PATH-DOTNET-WORKER-DIR>
```

#### <a name="maclinux"></a>[<span data-ttu-id="67d89-172">System Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="67d89-172">Mac/Linux</span></span>](#tab/linux)

```bash
export DOTNET_WORKER_DIR=<PATH-DOTNET-WORKER-DIR>
```

---

<span data-ttu-id="67d89-173">Na koniec sprawdź, czy można uruchomić `dotnet` polecenie, `java` `spark-shell` z poziomu wiersza polecenia przed przejściem do następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="67d89-173">Finally, double-check that you can run `dotnet`, `java`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="67d89-174">Napisz aplikację platformy .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="67d89-174">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="67d89-175">1. Tworzenie aplikacji konsolowej</span><span class="sxs-lookup"><span data-stu-id="67d89-175">1. Create a console app</span></span>

<span data-ttu-id="67d89-176">W wierszu polecenia lub terminalu uruchom następujące polecenia, aby utworzyć nową aplikację konsolową:</span><span class="sxs-lookup"><span data-stu-id="67d89-176">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o MySparkApp
cd MySparkApp
```

<span data-ttu-id="67d89-177">`dotnet`Polecenie tworzy `new` aplikację typu `console` .</span><span class="sxs-lookup"><span data-stu-id="67d89-177">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="67d89-178">`-o`Parametr tworzy katalog o nazwie *MySparkApp* , w którym jest przechowywana aplikacja i wypełnia je wymaganymi plikami.</span><span class="sxs-lookup"><span data-stu-id="67d89-178">The `-o` parameter creates a directory named *MySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="67d89-179">`cd MySparkApp`Polecenie zmienia katalog na utworzony katalog aplikacji.</span><span class="sxs-lookup"><span data-stu-id="67d89-179">The `cd MySparkApp` command changes the directory to the app directory you created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="67d89-180">2. Zainstaluj pakiet NuGet</span><span class="sxs-lookup"><span data-stu-id="67d89-180">2. Install NuGet package</span></span>

<span data-ttu-id="67d89-181">Aby używać platformy .NET do Apache Spark w aplikacji, zainstaluj pakiet Microsoft. Spark.</span><span class="sxs-lookup"><span data-stu-id="67d89-181">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="67d89-182">W wierszu polecenia lub terminalu uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="67d89-182">In your command prompt or terminal, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Spark
```

> [!NOTE]
> <span data-ttu-id="67d89-183">Ten samouczek używa najnowszej wersji `Microsoft.Spark` pakietu NuGet, o ile nie określono inaczej.</span><span class="sxs-lookup"><span data-stu-id="67d89-183">This tutorial uses the latest version of the `Microsoft.Spark` NuGet package unless otherwise specified.</span></span>

### <a name="3-write-your-app"></a><span data-ttu-id="67d89-184">3. Napisz aplikację</span><span class="sxs-lookup"><span data-stu-id="67d89-184">3. Write your app</span></span>

<span data-ttu-id="67d89-185">Otwórz *program.cs* w Visual Studio Code lub dowolnym edytorze tekstów i Zastąp cały kod następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="67d89-185">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;
using static Microsoft.Spark.Sql.Functions;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create Spark session
            SparkSession spark =
                SparkSession
                    .Builder()
                    .AppName("word_count_sample")
                    .GetOrCreate();

            // Create initial DataFrame
            string filePath = args[0];
            DataFrame dataFrame = spark.Read().Text(filePath);

            //Count words
            DataFrame words =
                dataFrame
                    .Select(Split(Col("value")," ").Alias("words"))
                    .Select(Explode(Col("words")).Alias("word"))
                    .GroupBy("word")
                    .Count()
                    .OrderBy(Col("count").Desc());

            // Display results
            words.Show();

            // Stop Spark session
            spark.Stop();
        }
    }
}
```

<span data-ttu-id="67d89-186">[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) to punkt wejścia aplikacji Apache Spark, który zarządza kontekstem i informacjami aplikacji.</span><span class="sxs-lookup"><span data-stu-id="67d89-186">[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) is the entrypoint of Apache Spark applications, which manages the context and information of your application.</span></span> <span data-ttu-id="67d89-187">Przy użyciu metody [tekstowej](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) dane tekstowe z pliku określonego przez `filePath` jest odczytywane w [ramce Dataframe](xref:Microsoft.Spark.Sql.DataFrame).</span><span class="sxs-lookup"><span data-stu-id="67d89-187">Using the [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) method, the text data from the file specified by the `filePath` is read into a [DataFrame](xref:Microsoft.Spark.Sql.DataFrame).</span></span> <span data-ttu-id="67d89-188">Element Dataframe to sposób organizowania danych w zestaw nazwanych kolumn.</span><span class="sxs-lookup"><span data-stu-id="67d89-188">A DataFrame is a way of organizing data into a set of named columns.</span></span> <span data-ttu-id="67d89-189">Następnie seria transformacji jest stosowana do dzielenia zdań w pliku, grupowania każdego z nich i policzania ich w kolejności malejącej.</span><span class="sxs-lookup"><span data-stu-id="67d89-189">Then, a series of transformations is applied to split the sentences in the file, group each of the words, count them and order them in descending order.</span></span> <span data-ttu-id="67d89-190">Wynik tych operacji jest przechowywany w innej ramce Dataframe.</span><span class="sxs-lookup"><span data-stu-id="67d89-190">The result of these operations is stored in another DataFrame.</span></span> <span data-ttu-id="67d89-191">Należy zauważyć, że w tym momencie nie wykonano żadnych operacji, ponieważ platforma .NET dla Apache Spark opóźnieniem oblicza dane.</span><span class="sxs-lookup"><span data-stu-id="67d89-191">Note that at this point, no operations have taken place because .NET for Apache Spark lazily evaluates the data.</span></span> <span data-ttu-id="67d89-192">Nie do momentu wywołania metody [show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) , aby wyświetlić zawartość `words` przekształconego ramki danych do konsoli, że operacje zdefiniowane w wierszach powyżej zostały wykonane.</span><span class="sxs-lookup"><span data-stu-id="67d89-192">It's not until the [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) method is called to display the contents of the `words` transformed DataFrame to the console that the operations defined in the lines above execute.</span></span> <span data-ttu-id="67d89-193">Gdy sesja platformy Spark nie jest już potrzebna, użyj metody [stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) , aby zatrzymać sesję.</span><span class="sxs-lookup"><span data-stu-id="67d89-193">Once you no longer need the Spark session, use the [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) method to stop your session.</span></span>

### <a name="4-create-data-file"></a><span data-ttu-id="67d89-194">4. Utwórz plik danych</span><span class="sxs-lookup"><span data-stu-id="67d89-194">4. Create data file</span></span>

<span data-ttu-id="67d89-195">Aplikacja przetwarza plik zawierający wiersze tekstu.</span><span class="sxs-lookup"><span data-stu-id="67d89-195">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="67d89-196">Utwórz plik o nazwie *input.txt* pliku w katalogu *MySparkApp* , zawierający następujący tekst:</span><span class="sxs-lookup"><span data-stu-id="67d89-196">Create a file called *input.txt* file in your *MySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

<span data-ttu-id="67d89-197">Zapisz zmiany i zamknij plik.</span><span class="sxs-lookup"><span data-stu-id="67d89-197">Save the changes and close the file.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="67d89-198">Uruchamianie aplikacji platformy .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="67d89-198">Run your .NET for Apache Spark app</span></span>

<span data-ttu-id="67d89-199">Uruchom następujące polecenie, aby skompilować aplikację:</span><span class="sxs-lookup"><span data-stu-id="67d89-199">Run the following command to build your application:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="67d89-200">Przejdź do katalogu wyjściowego kompilacji i użyj polecenia, `spark-submit` Aby przesłać aplikację do uruchamiania na Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="67d89-200">Navigate to your build output directory and use the `spark-submit` command to submit your application to run on Apache Spark.</span></span> <span data-ttu-id="67d89-201">Pamiętaj, aby zamienić na  `<version>` wersję programu .NET Worker i `<path-of-input.txt>` ścieżkę pliku *input.txt* .</span><span class="sxs-lookup"><span data-stu-id="67d89-201">Make sure to replace  `<version>` with the version of your .NET worker and `<path-of-input.txt>` with the path of your *input.txt* file is stored.</span></span>

### <a name="windows"></a>[<span data-ttu-id="67d89-202">Windows</span><span class="sxs-lookup"><span data-stu-id="67d89-202">Windows</span></span>](#tab/windows)

```console
spark-submit ^
--class org.apache.spark.deploy.dotnet.DotnetRunner ^
--master local ^
microsoft-spark-3-0_2.12-<version>.jar ^
dotnet MySparkApp.dll <path-of-input.txt>
```

### <a name="maclinux"></a>[<span data-ttu-id="67d89-203">System Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="67d89-203">Mac/Linux</span></span>](#tab/linux)

```bash
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master local \
microsoft-spark-3-0_2.12-<version>.jar \
dotnet MySparkApp.dll <path-of-input.txt>
```

---

> [!NOTE]
> <span data-ttu-id="67d89-204">W tym poleceniu przyjęto założenie, że pobrano Apache Spark i dodano go do zmiennej środowiskowej PATH, aby można było użyć programu `spark-submit` .</span><span class="sxs-lookup"><span data-stu-id="67d89-204">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="67d89-205">W przeciwnym razie należy użyć pełnej ścieżki (na przykład *C:\bin\apache-spark\bin\spark-Submit* lub *~/Spark/bin/Spark-Submit*).</span><span class="sxs-lookup"><span data-stu-id="67d89-205">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

<span data-ttu-id="67d89-206">Gdy aplikacja zostanie uruchomiona, dane zliczania wyrazów *input.txt* pliku są zapisywane w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="67d89-206">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

```console
+------+-----+
|  word|count|
+------+-----+
|  .NET|    3|
|Apache|    2|
|   app|    2|
|  This|    2|
| Spark|    2|
| World|    1|
|counts|    1|
|   for|    1|
| words|    1|
|  with|    1|
| Hello|    1|
|  uses|    1|
+------+-----+
```

<span data-ttu-id="67d89-207">Gratulacje!</span><span class="sxs-lookup"><span data-stu-id="67d89-207">Congratulations!</span></span> <span data-ttu-id="67d89-208">Pomyślnie utworzono i uruchomiono aplikację .NET dla Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="67d89-208">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="67d89-209">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="67d89-209">Next steps</span></span>

<span data-ttu-id="67d89-210">W niniejszym samouczku zawarto informacje na temat wykonywania następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="67d89-210">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="67d89-211">Przygotuj środowisko dla platformy .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="67d89-211">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="67d89-212">Napisz swoją pierwszą aplikację .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="67d89-212">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="67d89-213">Kompilowanie i uruchamianie aplikacji platformy .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="67d89-213">Build and run your .NET for Apache Spark application</span></span>

<span data-ttu-id="67d89-214">Aby wyświetlić film wideo z objaśnieniem powyższych kroków, zapoznaj się z [serią filmów dla programu .net for Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span><span class="sxs-lookup"><span data-stu-id="67d89-214">To see a video explaining the steps above, check out the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="67d89-215">Zapoznaj się ze stroną zasobów, aby dowiedzieć się więcej.</span><span class="sxs-lookup"><span data-stu-id="67d89-215">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="67d89-216">Platforma .NET dla Apache Spark zasobów</span><span class="sxs-lookup"><span data-stu-id="67d89-216">.NET for Apache Spark Resources</span></span>](../resources/index.md)
