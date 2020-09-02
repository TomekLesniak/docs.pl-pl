---
title: Wprowadzenie do platformy .NET dla Apache Spark
description: Dowiedz się, jak uruchomić aplikację .NET dla Apache Spark przy użyciu platformy .NET Core w systemach Windows, macOS i Ubuntu.
ms.date: 06/25/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: d7297b11a2b5b21420fcb2f0f9ae823cb29b88d1
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359002"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="bc705-103">Samouczek: Rozpoczynanie pracy z platformą .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bc705-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="bc705-104">W tym samouczku przedstawiono sposób uruchamiania aplikacji platformy .NET dla Apache Spark przy użyciu platformy .NET Core w systemach Windows, macOS i Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="bc705-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, macOS, and Ubuntu.</span></span>

<span data-ttu-id="bc705-105">Ten samouczek zawiera informacje na temat wykonywania następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="bc705-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="bc705-106">Przygotuj środowisko dla platformy .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bc705-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="bc705-107">Napisz swoją pierwszą aplikację .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bc705-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="bc705-108">Kompiluj i uruchamiaj prostą aplikację platformy .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bc705-108">Build and run your simple .NET for Apache Spark application</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prepare-your-environment"></a><span data-ttu-id="bc705-109">Przygotowywanie środowiska</span><span class="sxs-lookup"><span data-stu-id="bc705-109">Prepare your environment</span></span>

<span data-ttu-id="bc705-110">Przed rozpoczęciem pisania aplikacji należy skonfigurować niektóre zależności wymagane wstępnie.</span><span class="sxs-lookup"><span data-stu-id="bc705-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="bc705-111">Jeśli można uruchomić `dotnet` ,, `java` `mvn` , `spark-shell` z poziomu środowiska wiersza polecenia, środowisko jest już przygotowane i można przejść do następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="bc705-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="bc705-112">Jeśli nie można uruchomić żadnego lub wszystkich poleceń, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="bc705-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="bc705-113">1. Zainstaluj platformę .NET</span><span class="sxs-lookup"><span data-stu-id="bc705-113">1. Install .NET</span></span>

<span data-ttu-id="bc705-114">Aby rozpocząć tworzenie aplikacji platformy .NET, należy pobrać i zainstalować zestaw .NET SDK (Software Development Kit).</span><span class="sxs-lookup"><span data-stu-id="bc705-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="bc705-115">Pobierz i zainstaluj [zestaw .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="bc705-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="bc705-116">Zainstalowanie zestawu SDK dodaje `dotnet` łańcucha narzędzi do ścieżki.</span><span class="sxs-lookup"><span data-stu-id="bc705-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="bc705-117">Po zainstalowaniu zestaw .NET Core SDK Otwórz nowy wiersz polecenia lub terminal i uruchom polecenie `dotnet` .</span><span class="sxs-lookup"><span data-stu-id="bc705-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="bc705-118">Jeśli polecenie jest uruchamiane i drukuje informacje o sposobach korzystania z programu dotnet, można przejść do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="bc705-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="bc705-119">Jeśli `'dotnet' is not recognized as an internal or external command` wystąpi błąd, upewnij się, że otwarto **Nowy** wiersz polecenia lub terminal przed uruchomieniem polecenia.</span><span class="sxs-lookup"><span data-stu-id="bc705-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="bc705-120">2. Zainstaluj środowisko Java</span><span class="sxs-lookup"><span data-stu-id="bc705-120">2. Install Java</span></span>

<span data-ttu-id="bc705-121">Zainstaluj [środowisko Java 8,1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) dla systemu Windows i MacOS lub [OpenJDK 8](https://openjdk.java.net/install/) dla Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="bc705-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and macOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="bc705-122">Wybierz odpowiednią wersję systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="bc705-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="bc705-123">Na przykład wybierz **jdk-8u201-windows-x64.exe** dla komputera z systemem Windows x64 (jak pokazano poniżej) lub **JDK-8u231-macosx-x64. dmg** dla macOS.</span><span class="sxs-lookup"><span data-stu-id="bc705-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for macOS.</span></span> <span data-ttu-id="bc705-124">Następnie użyj polecenia, `java` Aby zweryfikować instalację.</span><span class="sxs-lookup"><span data-stu-id="bc705-124">Then, use the command `java` to verify the installation.</span></span>

![Pobieranie w języku Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="bc705-126">3. Zainstaluj oprogramowanie do kompresji</span><span class="sxs-lookup"><span data-stu-id="bc705-126">3. Install compression software</span></span>

<span data-ttu-id="bc705-127">Apache Spark jest pobierany jako skompresowany plik TGZ.</span><span class="sxs-lookup"><span data-stu-id="bc705-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="bc705-128">Użyj programu wyodrębniania, takiego jak [7-zip](https://www.7-zip.org/) lub [WinZip](https://www.winzip.com/), aby wyodrębnić plik.</span><span class="sxs-lookup"><span data-stu-id="bc705-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="bc705-129">4. Zainstaluj Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bc705-129">4. Install Apache Spark</span></span>

<span data-ttu-id="bc705-130">[Pobierz i zainstaluj Apache Spark](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="bc705-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="bc705-131">Należy wybrać jedną z wersji 2,3. \* lub 2.4.0, 2.4.1, 2.4.3 lub 2.4.4 (.NET dla Apache Spark nie jest zgodna z innymi wersjami Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="bc705-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="bc705-132">W poniższych krokach przyjęto założenie, że [pobrano i zainstalowano Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span><span class="sxs-lookup"><span data-stu-id="bc705-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="bc705-133">Jeśli chcesz użyć innej wersji, Zastąp wartość **2.4.1** odpowiednim numerem wersji.</span><span class="sxs-lookup"><span data-stu-id="bc705-133">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="bc705-134">Następnie wyodrębnij plik **. tar** i pliki Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="bc705-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="bc705-135">Aby wyodrębnić zagnieżdżony plik **tar** :</span><span class="sxs-lookup"><span data-stu-id="bc705-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="bc705-136">Znajdź pobrany plik **Spark-2.4.1-bin-Hadoop 2.7. tgz** .</span><span class="sxs-lookup"><span data-stu-id="bc705-136">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="bc705-137">Kliknij prawym przyciskiem myszy plik i wybierz **7-zip-> Wyodrębnij tutaj**.</span><span class="sxs-lookup"><span data-stu-id="bc705-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="bc705-138">**Spark-2.4.1-bin-Hadoop 2.7. tar** jest tworzony obok pobranego pliku **. tgz** .</span><span class="sxs-lookup"><span data-stu-id="bc705-138">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="bc705-139">Aby wyodrębnić pliki Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="bc705-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="bc705-140">Kliknij prawym przyciskiem myszy **Spark-2.4.1-bin-Hadoop 2.7. tar** i wybierz **7-zip-> Wyodrębnianie plików...**</span><span class="sxs-lookup"><span data-stu-id="bc705-140">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="bc705-141">Wprowadź **C:\Bin** w polu **Wyodrębnij do** .</span><span class="sxs-lookup"><span data-stu-id="bc705-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="bc705-142">Usuń zaznaczenie pola wyboru pod polem **Wyodrębnij do** .</span><span class="sxs-lookup"><span data-stu-id="bc705-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="bc705-143">Wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc705-143">Select **OK**.</span></span>
* <span data-ttu-id="bc705-144">Pliki Apache Spark są wyodrębniane do C:\bin\spark-2.4.1-bin-hadoop2.7</span><span class="sxs-lookup"><span data-stu-id="bc705-144">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7</span></span>\

![Zainstaluj platformę Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="bc705-146">Uruchom następujące polecenia, aby ustawić zmienne środowiskowe używane do lokalizowania Apache Spark w **systemie Windows**:</span><span class="sxs-lookup"><span data-stu-id="bc705-146">Run the following commands to set the environment variables used to locate Apache Spark on **Windows**:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="bc705-147">Uruchom następujące polecenia, aby ustawić zmienne środowiskowe używane do lokalizowania Apache Spark w **macOS** i **Ubuntu**:</span><span class="sxs-lookup"><span data-stu-id="bc705-147">Run the following commands to set the environment variables used to locate Apache Spark on **macOS** and **Ubuntu**:</span></span>

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

<span data-ttu-id="bc705-148">Po zainstalowaniu wszystkiego i ustawieniu zmiennych środowiskowych Otwórz **Nowy** wiersz polecenia lub terminal i uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="bc705-148">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="bc705-149">Jeśli polecenie jest uruchamiane i drukuje informacje o wersji, można przejść do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="bc705-149">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="bc705-150">Jeśli `'spark-submit' is not recognized as an internal or external command` wystąpi błąd, upewnij się, że otwarto **Nowy** wiersz polecenia.</span><span class="sxs-lookup"><span data-stu-id="bc705-150">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="bc705-151">5. Zainstaluj program .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bc705-151">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="bc705-152">Pobierz wydanie [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) z platformy .net dla Apache Spark GitHub.</span><span class="sxs-lookup"><span data-stu-id="bc705-152">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="bc705-153">Na przykład jeśli korzystasz z komputera z systemem Windows i planujesz używać platformy .NET Core, [Pobierz wydanie systemu Windows x64 netcoreapp 3.1](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).</span><span class="sxs-lookup"><span data-stu-id="bc705-153">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).</span></span>

<span data-ttu-id="bc705-154">Aby wyodrębnić pakiet Microsoft. Spark. Worker:</span><span class="sxs-lookup"><span data-stu-id="bc705-154">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="bc705-155">Znajdź pobrany plik **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** .</span><span class="sxs-lookup"><span data-stu-id="bc705-155">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="bc705-156">Kliknij prawym przyciskiem myszy i wybierz **7-zip-> Wyodrębnianie plików.**...</span><span class="sxs-lookup"><span data-stu-id="bc705-156">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="bc705-157">Wprowadź **C:\Bin** w polu **Wyodrębnij do** .</span><span class="sxs-lookup"><span data-stu-id="bc705-157">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="bc705-158">Usuń zaznaczenie pola wyboru pod polem **Wyodrębnij do** .</span><span class="sxs-lookup"><span data-stu-id="bc705-158">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="bc705-159">Wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc705-159">Select **OK**.</span></span>

![Zainstaluj platformę .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="bc705-161">6. Zainstaluj WinUtils (tylko system Windows)</span><span class="sxs-lookup"><span data-stu-id="bc705-161">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="bc705-162">Platforma .NET dla Apache Spark wymaga zainstalowania WinUtils razem z Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="bc705-162">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="bc705-163">[Pobierz winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="bc705-163">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="bc705-164">Następnie skopiuj WinUtils do **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span><span class="sxs-lookup"><span data-stu-id="bc705-164">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="bc705-165">Jeśli używasz innej wersji usługi Hadoop, która ma adnotację na końcu nazwy folderu instalacji platformy Spark, [Wybierz wersję WinUtils](https://github.com/steveloughran/winutils) zgodną z wersją usługi Hadoop.</span><span class="sxs-lookup"><span data-stu-id="bc705-165">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="bc705-166">7. Ustaw DOTNET_WORKER_DIR i sprawdź zależności</span><span class="sxs-lookup"><span data-stu-id="bc705-166">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="bc705-167">Uruchom jedno z następujących poleceń, aby ustawić `DOTNET_WORKER_DIR` zmienną środowiskową, która jest używana przez aplikacje platformy .NET do lokalizowania programu .NET dla Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="bc705-167">Run one of the following commands to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark.</span></span>

<span data-ttu-id="bc705-168">W **systemie Windows**Utwórz [nową zmienną środowiskową](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR` i ustaw ją na katalog, w którym został pobrany i wyodrębniony element Microsoft. Spark. Worker (na przykład `C:\bin\Microsoft.Spark.Worker\` ).</span><span class="sxs-lookup"><span data-stu-id="bc705-168">On **Windows**, create a [new environment variable](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, `C:\bin\Microsoft.Spark.Worker\`).</span></span>

<span data-ttu-id="bc705-169">W programie **macOS**Utwórz nową zmienną środowiskową przy użyciu programu `export DOTNET_WORKER_DIR <your_path>` i ustaw ją na katalog, w którym został pobrany i wyodrębniony element Microsoft. Spark. Worker (na przykład *~/bin/Microsoft.Spark.Worker/*).</span><span class="sxs-lookup"><span data-stu-id="bc705-169">On **macOS**, create a new environment variable using `export DOTNET_WORKER_DIR <your_path>` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker/*).</span></span>

<span data-ttu-id="bc705-170">W programie **Ubuntu**Utwórz [nową zmienną środowiskową](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR` i ustaw ją na katalog, w którym został pobrany i wyodrębniony element Microsoft. Spark. Worker (na przykład *~/bin/Microsoft.Spark.Worker*).</span><span class="sxs-lookup"><span data-stu-id="bc705-170">On **Ubuntu**, create a [new environment variable](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker*).</span></span>

<span data-ttu-id="bc705-171">Na koniec sprawdź, czy `dotnet` `java` `mvn` `spark-shell` przed przejściem do następnej sekcji można uruchomić polecenie,,, z poziomu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="bc705-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="bc705-172">Napisz aplikację platformy .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bc705-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="bc705-173">1. Tworzenie aplikacji konsolowej</span><span class="sxs-lookup"><span data-stu-id="bc705-173">1. Create a console app</span></span>

<span data-ttu-id="bc705-174">W wierszu polecenia lub terminalu uruchom następujące polecenia, aby utworzyć nową aplikację konsolową:</span><span class="sxs-lookup"><span data-stu-id="bc705-174">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="bc705-175">`dotnet`Polecenie tworzy `new` aplikację typu `console` .</span><span class="sxs-lookup"><span data-stu-id="bc705-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="bc705-176">`-o`Parametr tworzy katalog o nazwie *mySparkApp* , w którym jest przechowywana aplikacja i wypełnia je wymaganymi plikami.</span><span class="sxs-lookup"><span data-stu-id="bc705-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="bc705-177">`cd mySparkApp`Polecenie zmienia katalog na właśnie utworzony katalog aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bc705-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="bc705-178">2. Zainstaluj pakiet NuGet</span><span class="sxs-lookup"><span data-stu-id="bc705-178">2. Install NuGet package</span></span>

<span data-ttu-id="bc705-179">Aby używać platformy .NET do Apache Spark w aplikacji, zainstaluj pakiet Microsoft. Spark.</span><span class="sxs-lookup"><span data-stu-id="bc705-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="bc705-180">W wierszu polecenia lub terminalu uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="bc705-180">In your command prompt or terminal, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.8.0`

### <a name="3-code-your-app"></a><span data-ttu-id="bc705-181">3. kod aplikacji</span><span class="sxs-lookup"><span data-stu-id="bc705-181">3. Code your app</span></span>

<span data-ttu-id="bc705-182">Otwórz *program.cs* w Visual Studio Code lub dowolnym edytorze tekstów i Zastąp cały kod następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="bc705-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            SparkSession spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            DataFrame words = dataFrame
                .Select(Functions.Split(Functions.Col("value"), " ").Alias("words"))
                .Select(Functions.Explode(Functions.Col("words"))
                .Alias("word"))
                .GroupBy("word")
                .Count()
                .OrderBy(Functions.Col("count").Desc());

            // Show results.
            words.Show();

            // Stop Spark session.
            spark.Stop();
        }
    }
}
```

### <a name="4-create-and-add-a-data-file"></a><span data-ttu-id="bc705-183">4. Utwórz i Dodaj plik danych</span><span class="sxs-lookup"><span data-stu-id="bc705-183">4. Create and add a data file</span></span>

<span data-ttu-id="bc705-184">Otwórz wiersz polecenia lub terminal i przejdź do folderu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bc705-184">Open your command prompt or terminal and navigate into your app folder.</span></span>

```bash
cd <your-app-output-directory>
```

<span data-ttu-id="bc705-185">Aplikacja przetwarza plik zawierający wiersze tekstu.</span><span class="sxs-lookup"><span data-stu-id="bc705-185">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="bc705-186">Utwórz plik *input.txt* w katalogu *mySparkApp* , zawierający następujący tekst:</span><span class="sxs-lookup"><span data-stu-id="bc705-186">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="bc705-187">Uruchamianie aplikacji platformy .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bc705-187">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="bc705-188">Uruchom następujące polecenie, aby skompilować aplikację:</span><span class="sxs-lookup"><span data-stu-id="bc705-188">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="bc705-189">Uruchom następujące polecenie, aby przesłać aplikację do uruchamiania na Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="bc705-189">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```console
   spark-submit \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --master local \
   microsoft-spark-2.4.x-<version>.jar \
   dotnet HelloSpark.dll
   ```

   > [!NOTE]
   > <span data-ttu-id="bc705-190">W tym poleceniu przyjęto założenie, że pobrano Apache Spark i dodano go do zmiennej środowiskowej PATH, aby można było użyć programu `spark-submit` .</span><span class="sxs-lookup"><span data-stu-id="bc705-190">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="bc705-191">W przeciwnym razie należy użyć pełnej ścieżki (na przykład *C:\bin\apache-spark\bin\spark-Submit* lub *~/Spark/bin/Spark-Submit*).</span><span class="sxs-lookup"><span data-stu-id="bc705-191">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

3. <span data-ttu-id="bc705-192">Gdy aplikacja zostanie uruchomiona, dane zliczania wyrazów *input.txt* pliku są zapisywane w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="bc705-192">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="bc705-193">Gratulacje!</span><span class="sxs-lookup"><span data-stu-id="bc705-193">Congratulations!</span></span> <span data-ttu-id="bc705-194">Pomyślnie utworzono i uruchomiono aplikację .NET dla Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="bc705-194">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc705-195">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="bc705-195">Next steps</span></span>

<span data-ttu-id="bc705-196">W niniejszym samouczku zawarto informacje na temat wykonywania następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="bc705-196">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="bc705-197">Przygotuj środowisko systemu Windows dla platformy .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bc705-197">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="bc705-198">Napisz swoją pierwszą aplikację .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bc705-198">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="bc705-199">Kompiluj i uruchamiaj prostą aplikację platformy .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bc705-199">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="bc705-200">Aby wyświetlić film wideo z objaśnieniem powyższych kroków, Zaewidencjonuj [serie wideo dla programu .net for Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span><span class="sxs-lookup"><span data-stu-id="bc705-200">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="bc705-201">Zapoznaj się ze stroną zasobów, aby dowiedzieć się więcej.</span><span class="sxs-lookup"><span data-stu-id="bc705-201">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="bc705-202">Platforma .NET dla Apache Spark zasobów</span><span class="sxs-lookup"><span data-stu-id="bc705-202">.NET for Apache Spark Resources</span></span>](../resources/index.md)
