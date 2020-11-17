---
title: Wdrażanie aplikacji platformy .NET dla Apache Spark w usłudze Azure HDInsight
description: Dowiedz się, jak wdrożyć aplikację platformy .NET dla Apache Spark w usłudze HDInsight.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: f7a3b0c0d972d5cb6dbc6eea818fe794c5060eae
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687913"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="93021-103">Samouczek: wdrażanie aplikacji .NET dla Apache Spark w usłudze Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="93021-103">Tutorial: Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="93021-104">W tym samouczku przedstawiono sposób wdrażania aplikacji platformy .NET dla Apache Spark w chmurze za pomocą klastra usługi Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="93021-104">This tutorial teaches you how to deploy your .NET for Apache Spark app to the cloud through an Azure HDInsight cluster.</span></span> <span data-ttu-id="93021-105">Usługa HDInsight ułatwia tworzenie i Konfigurowanie klastra Spark na platformie Azure, ponieważ klastry Spark w usłudze HDInsight są zgodne z usługą Azure Storage i Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="93021-105">HDInsight makes it easier to create and configure a Spark cluster in Azure since Spark clusters in HDInsight are compatible with Azure Storage and Azure Data Lake Storage.</span></span>

<span data-ttu-id="93021-106">Z tego samouczka dowiesz się, jak wykonywać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="93021-106">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="93021-107">Uzyskaj dostęp do kont magazynu przy użyciu Eksplorator usługi Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="93021-107">Access your storage accounts using Azure Storage Explorer.</span></span>
> * <span data-ttu-id="93021-108">Utwórz klaster usługi Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="93021-108">Create an Azure HDInsight cluster.</span></span>
> * <span data-ttu-id="93021-109">Opublikuj aplikację .NET dla Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="93021-109">Publish your .NET for Apache Spark app.</span></span>
> * <span data-ttu-id="93021-110">Utwórz i uruchom akcję skryptu usługi HDInsight.</span><span class="sxs-lookup"><span data-stu-id="93021-110">Create and run an HDInsight script action.</span></span>
> * <span data-ttu-id="93021-111">Uruchom aplikację .NET dla Apache Spark w klastrze usługi HDInsight.</span><span class="sxs-lookup"><span data-stu-id="93021-111">Run a .NET for Apache Spark app on an HDInsight cluster.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="93021-112">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="93021-112">Prerequisites</span></span>

<span data-ttu-id="93021-113">Przed rozpoczęciem wykonaj następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="93021-113">Before you start, do the following tasks:</span></span>

* <span data-ttu-id="93021-114">Jeśli nie masz subskrypcji platformy Azure, utwórz [bezpłatne konto](https://azure.microsoft.com/free/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="93021-114">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/dotnet/).</span></span>
* <span data-ttu-id="93021-115">Zaloguj się w witrynie [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="93021-115">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
* <span data-ttu-id="93021-116">Zainstaluj Eksplorator usługi Azure Storage na komputerze z [systemem Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409)lub [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409) .</span><span class="sxs-lookup"><span data-stu-id="93021-116">Install Azure Storage Explorer on your [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409), or [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409) computer.</span></span>
* <span data-ttu-id="93021-117">Ukończ [platformę .NET dla Apache Spark — Rozpocznij pracę w 10-minutowym](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) samouczku.</span><span class="sxs-lookup"><span data-stu-id="93021-117">Complete the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial.</span></span>

## <a name="access-your-storage-accounts"></a><span data-ttu-id="93021-118">Dostęp do kont magazynu</span><span class="sxs-lookup"><span data-stu-id="93021-118">Access your storage accounts</span></span>

1. <span data-ttu-id="93021-119">Otwórz Eksplorator usługi Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="93021-119">Open Azure Storage Explorer.</span></span>

2. <span data-ttu-id="93021-120">W menu po lewej stronie wybierz pozycję **Dodaj konto** , a następnie zaloguj się do konta platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="93021-120">Select **Add Account** on the left menu, and sign in to your Azure account.</span></span>

    ![Zaloguj się do konta platformy Azure z poziomu Eksplorator usługi Storage](./media/hdinsight-deployment/signin-azure-storage-explorer.png)

   <span data-ttu-id="93021-122">Po zalogowaniu się powinny zostać wyświetlone wszystkie konta magazynu i wszystkie zasoby, które zostały przekazane do kont magazynu.</span><span class="sxs-lookup"><span data-stu-id="93021-122">After you sign in, you should see all storage accounts you have and any resources you have uploaded to your storage accounts.</span></span>

## <a name="create-an-hdinsight-cluster"></a><span data-ttu-id="93021-123">Tworzenie klastra HDInsight</span><span class="sxs-lookup"><span data-stu-id="93021-123">Create an HDInsight cluster</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93021-124">Opłaty za klastry usługi HDInsight są naliczane proporcjonalnie do liczby minut, nawet jeśli nie są używane.</span><span class="sxs-lookup"><span data-stu-id="93021-124">Billing for HDInsight clusters is prorated per minute, even if you're not using them.</span></span> <span data-ttu-id="93021-125">Pamiętaj o usunięciu klastra po zakończeniu korzystania z niego.</span><span class="sxs-lookup"><span data-stu-id="93021-125">Be sure to delete your cluster after you have finished using it.</span></span> <span data-ttu-id="93021-126">Aby uzyskać więcej informacji, zobacz sekcję [czyszczenie zasobów](#clean-up-resources) w tym samouczku.</span><span class="sxs-lookup"><span data-stu-id="93021-126">For more information, see the [Clean up resources](#clean-up-resources) section of this tutorial.</span></span>

1. <span data-ttu-id="93021-127">Odwiedź [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="93021-127">Visit the [Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="93021-128">Wybierz pozycję **+ Utwórz zasób**.</span><span class="sxs-lookup"><span data-stu-id="93021-128">Select **+ Create a resource**.</span></span> <span data-ttu-id="93021-129">Następnie wybierz pozycję **HDInsight** z kategorii **Analytics** .</span><span class="sxs-lookup"><span data-stu-id="93021-129">Then, select **HDInsight** from the **Analytics** category.</span></span>

    ![Utwórz zasób usługi HDInsight na podstawie Azure Portal](./media/hdinsight-deployment/create-hdinsight-resource.png)

3. <span data-ttu-id="93021-131">W obszarze **Podstawy** podaj następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="93021-131">Under **Basics**, provide the following values:</span></span>

    |<span data-ttu-id="93021-132">Właściwość</span><span class="sxs-lookup"><span data-stu-id="93021-132">Property</span></span>  |<span data-ttu-id="93021-133">Opis</span><span class="sxs-lookup"><span data-stu-id="93021-133">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="93021-134">Subskrypcja</span><span class="sxs-lookup"><span data-stu-id="93021-134">Subscription</span></span>  | <span data-ttu-id="93021-135">Z listy rozwijanej wybierz jedną z aktywnych subskrypcji platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="93021-135">From the drop-down, choose one of your active Azure subscriptions.</span></span> |
    |<span data-ttu-id="93021-136">Grupa zasobów</span><span class="sxs-lookup"><span data-stu-id="93021-136">Resource group</span></span> | <span data-ttu-id="93021-137">Określ, czy chcesz utworzyć nową grupę zasobów, czy użyć istniejącej grupy.</span><span class="sxs-lookup"><span data-stu-id="93021-137">Specify whether you want to create a new resource group or use an existing one.</span></span> <span data-ttu-id="93021-138">Grupa zasobów to kontener zawierający powiązane zasoby dla rozwiązania platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="93021-138">A resource group is a container that holds related resources for an Azure solution.</span></span> |
    |<span data-ttu-id="93021-139">Nazwa klastra</span><span class="sxs-lookup"><span data-stu-id="93021-139">Cluster name</span></span> | <span data-ttu-id="93021-140">Podaj nazwę klastra Spark w usłudze HDInsight.</span><span class="sxs-lookup"><span data-stu-id="93021-140">Give a name to your HDInsight Spark cluster.</span></span>|
    |<span data-ttu-id="93021-141">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="93021-141">Location</span></span>   | <span data-ttu-id="93021-142">Wybierz lokalizację dla grupy zasobów.</span><span class="sxs-lookup"><span data-stu-id="93021-142">Select a location for the resource group.</span></span> <span data-ttu-id="93021-143">Szablon używa tej lokalizacji do tworzenia klastra oraz na potrzeby domyślnego magazynu klastra.</span><span class="sxs-lookup"><span data-stu-id="93021-143">The template uses this location for creating the cluster as well as for the default cluster storage.</span></span> |
    |<span data-ttu-id="93021-144">Typ klastra</span><span class="sxs-lookup"><span data-stu-id="93021-144">Cluster type</span></span>| <span data-ttu-id="93021-145">Wybierz pozycję **Spark** jako typ klastra.</span><span class="sxs-lookup"><span data-stu-id="93021-145">Select **Spark** as the cluster type.</span></span>|
    |<span data-ttu-id="93021-146">Wersja klastra</span><span class="sxs-lookup"><span data-stu-id="93021-146">Cluster version</span></span>|<span data-ttu-id="93021-147">Po wybraniu typu klastra w tym polu zostanie automatycznie wypełniona domyślna wersja.</span><span class="sxs-lookup"><span data-stu-id="93021-147">This field will autopopulate with the default version once the cluster type has been selected.</span></span> <span data-ttu-id="93021-148">Wybierz 2,3 lub 2,4 wersję platformy Spark.</span><span class="sxs-lookup"><span data-stu-id="93021-148">Select a 2.3 or 2.4 version of Spark.</span></span>|
    |<span data-ttu-id="93021-149">Nazwa użytkownika logowania klastra</span><span class="sxs-lookup"><span data-stu-id="93021-149">Cluster login username</span></span>| <span data-ttu-id="93021-150">Wprowadź nazwę użytkownika logowania klastra.</span><span class="sxs-lookup"><span data-stu-id="93021-150">Enter the cluster login username.</span></span>  <span data-ttu-id="93021-151">Nazwa domyślna to *admin*.</span><span class="sxs-lookup"><span data-stu-id="93021-151">The default name is *admin*.</span></span> |
    |<span data-ttu-id="93021-152">Hasło logowania klastra</span><span class="sxs-lookup"><span data-stu-id="93021-152">Cluster login password</span></span>| <span data-ttu-id="93021-153">Wprowadź hasło logowania.</span><span class="sxs-lookup"><span data-stu-id="93021-153">Enter any login password.</span></span> |
    |<span data-ttu-id="93021-154">Nazwa użytkownika protokołu SSH (Secure Shell)</span><span class="sxs-lookup"><span data-stu-id="93021-154">Secure Shell (SSH) username</span></span>| <span data-ttu-id="93021-155">Wprowadź nazwę użytkownika protokołu SSH.</span><span class="sxs-lookup"><span data-stu-id="93021-155">Enter the SSH username.</span></span> <span data-ttu-id="93021-156">Domyślnie to konto współdzieli hasło z kontem *Nazwa użytkownika logowania klastra*.</span><span class="sxs-lookup"><span data-stu-id="93021-156">By default, this account shares the same password as the *Cluster Login username* account.</span></span> |

4. <span data-ttu-id="93021-157">Wybierz pozycję **Dalej: magazyn >>** , aby kontynuować na stronie **Magazyn** .</span><span class="sxs-lookup"><span data-stu-id="93021-157">Select **Next: Storage >>** to continue to the **Storage** page.</span></span> <span data-ttu-id="93021-158">W obszarze **Magazyn** podaj następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="93021-158">Under **Storage**, provide the following values:</span></span>

    |<span data-ttu-id="93021-159">Właściwość</span><span class="sxs-lookup"><span data-stu-id="93021-159">Property</span></span>  |<span data-ttu-id="93021-160">Opis</span><span class="sxs-lookup"><span data-stu-id="93021-160">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="93021-161">Podstawowy typ magazynu</span><span class="sxs-lookup"><span data-stu-id="93021-161">Primary storage type</span></span>|<span data-ttu-id="93021-162">Użyj wartości domyślnej **usługi Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="93021-162">Use the default value **Azure Storage**.</span></span>|
    |<span data-ttu-id="93021-163">Metoda wybierania</span><span class="sxs-lookup"><span data-stu-id="93021-163">Selection method</span></span>|<span data-ttu-id="93021-164">Użyj wartości domyślnej **Wybierz z listy**.</span><span class="sxs-lookup"><span data-stu-id="93021-164">Use the default value **Select from list**.</span></span>|
    |<span data-ttu-id="93021-165">Konto magazynu podstawowego</span><span class="sxs-lookup"><span data-stu-id="93021-165">Primary storage account</span></span>|<span data-ttu-id="93021-166">Wybierz swoją subskrypcję i jedno z aktywnych kont magazynu w ramach tej subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="93021-166">Choose your subscription and one of your active storage accounts within that subscription.</span></span>|
    |<span data-ttu-id="93021-167">Kontener</span><span class="sxs-lookup"><span data-stu-id="93021-167">Container</span></span>|<span data-ttu-id="93021-168">Ten kontener to konkretny kontener obiektów BLOB na koncie magazynu, w którym klaster szuka plików do uruchomienia aplikacji w chmurze.</span><span class="sxs-lookup"><span data-stu-id="93021-168">This container is the specific blob container in your storage account where your cluster looks for files to run your app in the cloud.</span></span> <span data-ttu-id="93021-169">Możesz nadać mu dowolną nazwę.</span><span class="sxs-lookup"><span data-stu-id="93021-169">You can give it any available name.</span></span>|

5. <span data-ttu-id="93021-170">W obszarze **Recenzja + tworzenie** wybierz pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="93021-170">Under **Review + create**, select **Create**.</span></span> <span data-ttu-id="93021-171">Utworzenie klastra trwa około 20 minut.</span><span class="sxs-lookup"><span data-stu-id="93021-171">It takes about 20 minutes to create the cluster.</span></span> <span data-ttu-id="93021-172">Przed przejściem do następnego kroku należy utworzyć klaster.</span><span class="sxs-lookup"><span data-stu-id="93021-172">The cluster must be created before you can continue to the next step.</span></span>

## <a name="publish-your-app"></a><span data-ttu-id="93021-173">Publikowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="93021-173">Publish your app</span></span>

<span data-ttu-id="93021-174">Następnie opublikujesz *mySparkApp* utworzone w programie [.NET dla Apache Spark — Rozpocznij w 10-minutowym](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) samouczku, co umożliwia klastrowi Spark dostęp do wszystkich plików potrzebnych do uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="93021-174">Next, you publish the *mySparkApp* created in the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial, which gives your Spark cluster access to all the files it needs to run your app.</span></span>

1. <span data-ttu-id="93021-175">Uruchom następujące polecenia, aby opublikować *mySparkApp*:</span><span class="sxs-lookup"><span data-stu-id="93021-175">Run the following commands to publish the *mySparkApp*:</span></span>

   <span data-ttu-id="93021-176">**W systemie Windows:**</span><span class="sxs-lookup"><span data-stu-id="93021-176">**On Windows:**</span></span>

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.1 -r win-x64
   ```

   <span data-ttu-id="93021-177">**W systemie Linux:**</span><span class="sxs-lookup"><span data-stu-id="93021-177">**On Linux:**</span></span>

   ```bash
   cd mySparkApp
   foo@bar:~/path/to/app$ dotnet publish -c Release -f netcoreapp3.1 -r ubuntu.16.04-x64
   ```

2. <span data-ttu-id="93021-178">Wykonaj następujące zadania w celu przesłania plików opublikowanych aplikacji, aby można je było łatwo przekazać do klastra usługi HDInsight.</span><span class="sxs-lookup"><span data-stu-id="93021-178">Do the following tasks to zip your published app files so that you can easily upload them to your HDInsight cluster.</span></span> <span data-ttu-id="93021-179">Zanotuj zawartość folderu publikowania, *publish.zip* na przykład, który został utworzony w wyniku kroku 1.</span><span class="sxs-lookup"><span data-stu-id="93021-179">Zip the contents of the publish folder, *publish.zip* for example, that was created as a result of Step 1.</span></span> <span data-ttu-id="93021-180">Wszystkie zestawy powinny znajdować się w pierwszej warstwie pliku ZIP i nie powinna być pośrednia warstwa folderów.</span><span class="sxs-lookup"><span data-stu-id="93021-180">All the assemblies should be in the first layer of the ZIP file and there should be no intermediate folder layer.</span></span> <span data-ttu-id="93021-181">Oznacza to, że podczas rozpakowania *publish.zip* wszystkie zestawy są wyodrębniane do bieżącego katalogu roboczego.</span><span class="sxs-lookup"><span data-stu-id="93021-181">This means when you unzip *publish.zip*, all assemblies are extracted into your current working directory.</span></span>

   <span data-ttu-id="93021-182">**W systemie Windows:**</span><span class="sxs-lookup"><span data-stu-id="93021-182">**On Windows:**</span></span>

   <span data-ttu-id="93021-183">Użyj programu wyodrębniania, takiego jak 7-zip lub WinZip, aby wyodrębnić plik do katalogu bin ze wszystkimi opublikowanymi plikami binarnymi.</span><span class="sxs-lookup"><span data-stu-id="93021-183">Use an extraction program, like 7-Zip or WinZip, to extract the file into the bin directory with all the published binaries.</span></span>

   <span data-ttu-id="93021-184">**W systemie Linux Uruchom następujące polecenie:**</span><span class="sxs-lookup"><span data-stu-id="93021-184">**On Linux, run the following command:**</span></span>

   ```bash
   zip -r publish.zip
   ```

## <a name="upload-files-to-azure"></a><span data-ttu-id="93021-185">Przekazywanie plików na platformę Azure</span><span class="sxs-lookup"><span data-stu-id="93021-185">Upload files to Azure</span></span>

<span data-ttu-id="93021-186">Następnie użyj Eksplorator usługi Azure Storage do przekazania następujących pięciu plików do kontenera obiektów BLOB wybranego dla magazynu klastra:</span><span class="sxs-lookup"><span data-stu-id="93021-186">Next, you use the Azure Storage Explorer to upload the following five files to the blob container you chose for your cluster's storage:</span></span>

* <span data-ttu-id="93021-187">Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="93021-187">Microsoft.Spark.Worker</span></span>
* <span data-ttu-id="93021-188">install-worker.sh</span><span class="sxs-lookup"><span data-stu-id="93021-188">install-worker.sh</span></span>
* <span data-ttu-id="93021-189">publish.zip</span><span class="sxs-lookup"><span data-stu-id="93021-189">publish.zip</span></span>
* <span data-ttu-id="93021-190">Microsoft-Spark-2-4_ 2.11 — 1.0.0. jar</span><span class="sxs-lookup"><span data-stu-id="93021-190">microsoft-spark-2-4_2.11-1.0.0.jar</span></span>
* <span data-ttu-id="93021-191">input.txt</span><span class="sxs-lookup"><span data-stu-id="93021-191">input.txt</span></span>

1. <span data-ttu-id="93021-192">Otwórz Eksplorator usługi Azure Storage i przejdź do swojego konta magazynu z menu po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="93021-192">Open Azure Storage Explorer and navigate to your storage account from the left menu.</span></span> <span data-ttu-id="93021-193">Przejdź do szczegółów kontenera obiektów BLOB klastra w kontenerach **obiektów BLOB** na koncie magazynu.</span><span class="sxs-lookup"><span data-stu-id="93021-193">Drill down to the blob container for your cluster under **Blob Containers** in your storage account.</span></span>

2. <span data-ttu-id="93021-194">Aplikacja *Microsoft. Spark. Worker* ułatwia Apache Spark wykonywanie aplikacji, na przykład dowolnych funkcji zdefiniowanych przez użytkownika (UDF).</span><span class="sxs-lookup"><span data-stu-id="93021-194">*Microsoft.Spark.Worker* helps Apache Spark execute your app, such as any user-defined functions (UDFs) you may have written.</span></span> <span data-ttu-id="93021-195">Pobierz [pakiet Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="93021-195">Download [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).</span></span> <span data-ttu-id="93021-196">Następnie wybierz pozycję **Przekaż** w Eksplorator usługi Azure Storage, aby przekazać proces roboczy.</span><span class="sxs-lookup"><span data-stu-id="93021-196">Then, select **Upload** in Azure Storage Explorer to upload the worker.</span></span>

   ![Przekaż pliki do Eksplorator usługi Azure Storage](./media/hdinsight-deployment/upload-files-to-storage.png)

3. <span data-ttu-id="93021-198">*Install-Worker.sh* to skrypt, który umożliwia skopiowanie programu .net dla Apache Spark plików zależnych do węzłów klastra.</span><span class="sxs-lookup"><span data-stu-id="93021-198">The *install-worker.sh* is a script that lets you copy .NET for Apache Spark dependent files into the nodes of your cluster.</span></span>

   <span data-ttu-id="93021-199">Utwórz nowy plik o nazwie **Install-Worker.sh** na komputerze lokalnym i wklej [zawartość Install-Worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) znajdującą się w witrynie GitHub.</span><span class="sxs-lookup"><span data-stu-id="93021-199">Create a new file named **install-worker.sh** in your local computer, and paste the [install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.</span></span> <span data-ttu-id="93021-200">Następnie Przekaż *Install-Worker.sh* do kontenera obiektów BLOB.</span><span class="sxs-lookup"><span data-stu-id="93021-200">Then, upload *install-worker.sh* to your blob container.</span></span>

4. <span data-ttu-id="93021-201">Klaster wymaga pliku *publish.zip* , który zawiera pliki opublikowane przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="93021-201">Your cluster needs the *publish.zip* file that contains your app's published files.</span></span> <span data-ttu-id="93021-202">Przejdź do opublikowanego folderu, **mySparkApp/bin/Release/netcoreapp 3.1/Ubuntu. 16.04-x64** i Znajdź **publish.zip**.</span><span class="sxs-lookup"><span data-stu-id="93021-202">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.1/ubuntu.16.04-x64**, and locate **publish.zip**.</span></span> <span data-ttu-id="93021-203">Następnie Przekaż *publish.zip* do kontenera obiektów BLOB.</span><span class="sxs-lookup"><span data-stu-id="93021-203">Then upload *publish.zip* to your blob container.</span></span>

5. <span data-ttu-id="93021-204">Klaster wymaga kodu aplikacji spakowanego jako jar, dołączonego jako część [pakietu NuGet Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) i współznajdującego się w katalogu danych wyjściowych kompilacji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="93021-204">Your cluster needs the application code that is packaged as a jar, included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) nuget and colocated in your app's build output directory.</span></span> <span data-ttu-id="93021-205">Przejdź do opublikowanego folderu, **mySparkApp/bin/Release/netcoreapp 3.1/Ubuntu. 16.04-x64** i Znajdź **Microsoft-Spark-2-4_ 2.11-1.0.0. jar**.</span><span class="sxs-lookup"><span data-stu-id="93021-205">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.1/ubuntu.16.04-x64**, and locate **microsoft-spark-2-4_2.11-1.0.0.jar**.</span></span> <span data-ttu-id="93021-206">Następnie Przekaż plik jar do kontenera obiektów BLOB.</span><span class="sxs-lookup"><span data-stu-id="93021-206">Then, upload the jar file to your blob container.</span></span>

   <span data-ttu-id="93021-207">Może istnieć wiele plików jar (dla wersji 2.3. x, 2.4. x i 3.0. x z platformy Spark).</span><span class="sxs-lookup"><span data-stu-id="93021-207">There may be multiple .jar files (for versions 2.3.x, 2.4.x and 3.0.x of Spark).</span></span> <span data-ttu-id="93021-208">Musisz wybrać plik JAR, który jest zgodny z wersją platformy Spark wybraną podczas tworzenia klastra.</span><span class="sxs-lookup"><span data-stu-id="93021-208">You need to choose the .jar file that matches the version of Spark you chose during cluster creation.</span></span> <span data-ttu-id="93021-209">Na przykład wybierz pozycję *Microsoft-Spark-2-4_ 2.11-1.0.0. jar* , jeśli podczas tworzenia klastra wybrano platformę Spark 2,4.</span><span class="sxs-lookup"><span data-stu-id="93021-209">For example, choose *microsoft-spark-2-4_2.11-1.0.0.jar* if you chose Spark 2.4 during cluster creation.</span></span>

6. <span data-ttu-id="93021-210">Klaster wymaga danych wejściowych do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="93021-210">Your cluster needs the input to your app.</span></span> <span data-ttu-id="93021-211">Przejdź do katalogu **mySparkApp** i Znajdź **input.txt**.</span><span class="sxs-lookup"><span data-stu-id="93021-211">Navigate to your **mySparkApp** directory and locate **input.txt**.</span></span> <span data-ttu-id="93021-212">Przekaż plik wejściowy do katalogu **User/sshuser** w kontenerze obiektów BLOB.</span><span class="sxs-lookup"><span data-stu-id="93021-212">Upload your input file to the **user/sshuser** directory in your blob container.</span></span> <span data-ttu-id="93021-213">Nastąpi połączenie z klastrem za pośrednictwem protokołu SSH, a ten folder wskazuje, że Twój klaster szuka jego danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="93021-213">You will be connecting to your cluster through ssh, and this folder is where your cluster looks for its input.</span></span> <span data-ttu-id="93021-214">Plik *input.txt* to jedyny plik przekazany do określonego katalogu.</span><span class="sxs-lookup"><span data-stu-id="93021-214">The *input.txt* file is the only file uploaded to a specific directory.</span></span>

## <a name="run-the-hdinsight-script-action"></a><span data-ttu-id="93021-215">Uruchamianie akcji skryptu HDInsight</span><span class="sxs-lookup"><span data-stu-id="93021-215">Run the HDInsight script action</span></span>

<span data-ttu-id="93021-216">Po uruchomieniu klastra i przekazaniu plików na platformę Azure należy uruchomić skrypt **Install-Worker.sh** w klastrze.</span><span class="sxs-lookup"><span data-stu-id="93021-216">Once your cluster is running and you've uploaded your files to Azure, you run the **install-worker.sh** script on the cluster.</span></span>

1. <span data-ttu-id="93021-217">Przejdź do klastra usługi HDInsight Spark w Azure Portal, a następnie wybierz pozycję **Akcje skryptu**.</span><span class="sxs-lookup"><span data-stu-id="93021-217">Navigate to your HDInsight Spark cluster in Azure portal, and then select **Script actions**.</span></span>

2. <span data-ttu-id="93021-218">Wybierz pozycję **+ Prześlij nową** i podaj następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="93021-218">Select **+ Submit new** and provide the following values:</span></span>

   |<span data-ttu-id="93021-219">Właściwość</span><span class="sxs-lookup"><span data-stu-id="93021-219">Property</span></span>  |<span data-ttu-id="93021-220">Opis</span><span class="sxs-lookup"><span data-stu-id="93021-220">Description</span></span>  |
   |---------|---------|
   | <span data-ttu-id="93021-221">Typ skryptu</span><span class="sxs-lookup"><span data-stu-id="93021-221">Script type</span></span> |<span data-ttu-id="93021-222">Niestandardowy</span><span class="sxs-lookup"><span data-stu-id="93021-222">Custom</span></span>|
   | <span data-ttu-id="93021-223">Nazwa</span><span class="sxs-lookup"><span data-stu-id="93021-223">Name</span></span> | <span data-ttu-id="93021-224">Zainstaluj proces roboczy</span><span class="sxs-lookup"><span data-stu-id="93021-224">Install Worker</span></span>|
   | <span data-ttu-id="93021-225">Identyfikator URI skryptu bash</span><span class="sxs-lookup"><span data-stu-id="93021-225">Bash script URI</span></span> |`https://mystorageaccount.blob.core.windows.net/mycontainer/install-worker.sh` </br> <span data-ttu-id="93021-226">Aby potwierdzić ten identyfikator URI, kliknij prawym przyciskiem myszy pozycję install-worker.sh w Eksplorator usługi Azure Storage a następnie wybierz pozycję Właściwości.</span><span class="sxs-lookup"><span data-stu-id="93021-226">To confirm this URI, right-click on install-worker.sh in Azure Storage Explorer and select Properties.</span></span> |
   | <span data-ttu-id="93021-227">Typy węzłów</span><span class="sxs-lookup"><span data-stu-id="93021-227">Node type(s)</span></span>| <span data-ttu-id="93021-228">Odpowiedzialn</span><span class="sxs-lookup"><span data-stu-id="93021-228">Worker</span></span>|
   | <span data-ttu-id="93021-229">Parametry</span><span class="sxs-lookup"><span data-stu-id="93021-229">Parameters</span></span> | <span data-ttu-id="93021-230">Azure</span><span class="sxs-lookup"><span data-stu-id="93021-230">azure</span></span> </br> wasbs://mycontainer@myStorageAccount.blob.core.windows.net/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz </br> <span data-ttu-id="93021-231">/usr/local/bin</span><span class="sxs-lookup"><span data-stu-id="93021-231">/usr/local/bin</span></span>

3. <span data-ttu-id="93021-232">Wybierz pozycję **Utwórz** , aby przesłać swój skrypt.</span><span class="sxs-lookup"><span data-stu-id="93021-232">Select **Create** to submit your script.</span></span>

## <a name="run-your-app"></a><span data-ttu-id="93021-233">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="93021-233">Run your app</span></span>

1. <span data-ttu-id="93021-234">Przejdź do klastra usługi HDInsight Spark w Azure Portal, a następnie wybierz pozycję **SSH + logowanie do klastra**.</span><span class="sxs-lookup"><span data-stu-id="93021-234">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="93021-235">Skopiuj informacje logowania SSH i wklej nazwę logowania do terminalu.</span><span class="sxs-lookup"><span data-stu-id="93021-235">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="93021-236">Zaloguj się do klastra przy użyciu hasła ustawionego podczas tworzenia klastra.</span><span class="sxs-lookup"><span data-stu-id="93021-236">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="93021-237">Powinny pojawić się komunikaty z powitaniem do Ubuntu i Spark.</span><span class="sxs-lookup"><span data-stu-id="93021-237">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="93021-238">Użyj polecenia **Spark-Submit** , aby uruchomić aplikację w klastrze usługi HDInsight.</span><span class="sxs-lookup"><span data-stu-id="93021-238">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="93021-239">Pamiętaj **, aby zastąpić obiekt** **mojekontomagazynu** i go w przykładowym skrypcie z rzeczywistymi nazwami kontenera obiektów blob i konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="93021-239">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2-4_2.11-1.0.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

   <span data-ttu-id="93021-240">Gdy aplikacja zostanie uruchomiona, zobaczysz tę samą tabelę Count wyrazów z uruchomienia lokalnego uruchamiania zarejestrowanego w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="93021-240">When your app runs, you see the same word count table from the getting started local run written to the console.</span></span> <span data-ttu-id="93021-241">Gratulacje, uruchomiono pierwszą aplikację platformy .NET dla Apache Spark w chmurze!</span><span class="sxs-lookup"><span data-stu-id="93021-241">Congratulations, you've run your first .NET for Apache Spark application in the cloud!</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="93021-242">Czyszczenie zasobów</span><span class="sxs-lookup"><span data-stu-id="93021-242">Clean up resources</span></span>

<span data-ttu-id="93021-243">Usługa HDInsight zapisuje dane w usłudze Azure Storage, dzięki czemu można bezpiecznie usunąć klaster, gdy nie jest używany.</span><span class="sxs-lookup"><span data-stu-id="93021-243">HDInsight saves your data in Azure Storage, so you can safely delete a cluster when it is not in use.</span></span> <span data-ttu-id="93021-244">Opłaty za klaster usługi HDInsight są naliczane nawet wtedy, gdy nie jest używany.</span><span class="sxs-lookup"><span data-stu-id="93021-244">You are also charged for an HDInsight cluster, even when it is not in use.</span></span> <span data-ttu-id="93021-245">Ponieważ opłaty za klaster są wielokrotnie większe niż opłaty za magazyn, ze względów ekonomicznych warto usuwać klastry, gdy nie są używane.</span><span class="sxs-lookup"><span data-stu-id="93021-245">Since the charges for the cluster are many times more than the charges for storage, it makes economic sense to delete clusters when they are not in use.</span></span>

<span data-ttu-id="93021-246">Dodatkowo możesz wybrać nazwę grupy zasobów, aby otworzyć stronę grupy zasobów, a następnie wybrać pozycję **Usuń grupę zasobów**.</span><span class="sxs-lookup"><span data-stu-id="93021-246">You can also select the resource group name to open the resource group page, and then select **Delete resource group**.</span></span> <span data-ttu-id="93021-247">Usunięcie grupy zasobów powoduje usunięcie zarówno klastra Spark w usłudze HDInsight, jak i domyślnego konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="93021-247">By deleting the resource group, you delete both the HDInsight Spark cluster, and the default storage account.</span></span>

## <a name="next-steps"></a><span data-ttu-id="93021-248">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="93021-248">Next steps</span></span>

<span data-ttu-id="93021-249">W tym samouczku wdrożono aplikację .NET dla Apache Spark w usłudze Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="93021-249">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="93021-250">Aby dowiedzieć się więcej o usłudze HDInsight, przejdź do dokumentacji usługi Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="93021-250">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="93021-251">[Zdalne przesyłanie zadań w usłudze Azure HDInsight](../how-to-guides/hdinsight-deploy-methods.md) 
>  [Dokumentacja usługi Azure HDInsight](/azure/hdinsight/)</span><span class="sxs-lookup"><span data-stu-id="93021-251">[Submit jobs remotely on Azure HDInsight](../how-to-guides/hdinsight-deploy-methods.md)
[Azure HDInsight Documentation](/azure/hdinsight/)</span></span>
