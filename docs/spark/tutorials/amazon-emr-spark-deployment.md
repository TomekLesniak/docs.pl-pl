---
title: Wdrażanie aplikacji .NET dla Apache Spark w usłudze Amazon EMR Spark
description: Dowiedz się, jak wdrożyć aplikację .NET for Apache Spark w usłudze Amazon EMR Spark.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: dd1cfdf12266b55d9dbc0210479b89ba68c59a38
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688075"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="30ab4-103">Wdrażanie aplikacji .NET dla Apache Spark w usłudze Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="30ab4-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="30ab4-104">W tym samouczku przedstawiono sposób wdrażania aplikacji .NET for Apache Spark w usłudze Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="30ab4-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="30ab4-105">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) to zarządzana platforma klastra, która upraszcza uruchamianie platform danych Big Data w systemie AWS.</span><span class="sxs-lookup"><span data-stu-id="30ab4-105">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

<span data-ttu-id="30ab4-106">Z tego samouczka dowiesz się, jak wykonywać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="30ab4-106">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="30ab4-107">Przygotuj pakiet Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="30ab4-107">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="30ab4-108">Publikowanie aplikacji platformy .NET Spark</span><span class="sxs-lookup"><span data-stu-id="30ab4-108">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="30ab4-109">Wdrażanie aplikacji w usłudze Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="30ab4-109">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="30ab4-110">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="30ab4-110">Run your app</span></span>

> [!Note]
> <span data-ttu-id="30ab4-111">AWS EMR Spark jest oparty na systemie Linux.</span><span class="sxs-lookup"><span data-stu-id="30ab4-111">AWS EMR Spark is Linux-based.</span></span> <span data-ttu-id="30ab4-112">W związku z tym, Jeśli interesuje Cię wdrażanie aplikacji w programie AWS EMR Spark, upewnij się, że aplikacja jest zgodna .NET Standard i że używasz kompilatora .NET Core do kompilowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="30ab4-112">Therefore, if you are interested in deploying your app to AWS EMR Spark, make sure your app is .NET Standard compatible and that you use .NET Core compiler to compile your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="30ab4-113">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="30ab4-113">Prerequisites</span></span>

<span data-ttu-id="30ab4-114">Przed rozpoczęciem wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="30ab4-114">Before you start, do the following:</span></span>

* <span data-ttu-id="30ab4-115">Pobierz [interfejs wiersza polecenia AWS](https://aws.amazon.com/cli/).</span><span class="sxs-lookup"><span data-stu-id="30ab4-115">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="30ab4-116">Pobierz [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) na komputer lokalny.</span><span class="sxs-lookup"><span data-stu-id="30ab4-116">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="30ab4-117">Jest to skrypt pomocnika używany później do kopiowania programu .NET pod kątem Apache Spark plików zależnych do węzłów procesu roboczego klastra platformy Spark.</span><span class="sxs-lookup"><span data-stu-id="30ab4-117">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="30ab4-118">Przygotowanie zależności procesu roboczego</span><span class="sxs-lookup"><span data-stu-id="30ab4-118">Prepare worker dependencies</span></span>

<span data-ttu-id="30ab4-119">**Microsoft. Spark. Worker** to składnik zaplecza, który znajduje się w poszczególnych węzłach procesu roboczego klastra Spark.</span><span class="sxs-lookup"><span data-stu-id="30ab4-119">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="30ab4-120">Jeśli chcesz wykonać funkcję UDF w języku C# (funkcja zdefiniowana przez użytkownika), platforma Spark musi zrozumieć, jak uruchomić środowisko CLR środowiska .NET, aby wykonać operację UDF.</span><span class="sxs-lookup"><span data-stu-id="30ab4-120">When you want to execute a C# UDF (User-Defined Function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="30ab4-121">Element **Microsoft. Spark. Worker** udostępnia kolekcję klas na platformie Spark, które umożliwiają włączenie tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="30ab4-121">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="30ab4-122">Wybierz wersję [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp, która ma zostać wdrożona w klastrze.</span><span class="sxs-lookup"><span data-stu-id="30ab4-122">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="30ab4-123">Jeśli na przykład chcesz `.NET for Apache Spark v1.0.0` użyć `netcoreapp3.1` , Pobierz [pakiet Microsoft. Spark. Worker. netcoreapp 3.1. linux-x64-1.0.0. tar. gz](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="30ab4-123">For example, if you want `.NET for Apache Spark v1.0.0` using `netcoreapp3.1`, you'd download [Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).</span></span>

2. <span data-ttu-id="30ab4-124">Przekazuj `Microsoft.Spark.Worker.<release>.tar.gz` i [Install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) do rozproszonego systemu plików (np. S3), do którego ma dostęp klaster.</span><span class="sxs-lookup"><span data-stu-id="30ab4-124">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="30ab4-125">Przygotowywanie aplikacji .NET dla Apache Spark</span><span class="sxs-lookup"><span data-stu-id="30ab4-125">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="30ab4-126">Postępuj zgodnie [z samouczkiem wprowadzenie,](get-started.md) aby skompilować aplikację.</span><span class="sxs-lookup"><span data-stu-id="30ab4-126">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="30ab4-127">Opublikuj swoją aplikację platformy Spark .NET jako samodzielny.</span><span class="sxs-lookup"><span data-stu-id="30ab4-127">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="30ab4-128">Uruchom następujące polecenie w systemie Linux.</span><span class="sxs-lookup"><span data-stu-id="30ab4-128">Run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp3.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="30ab4-129">Twórz `<your app>.zip` pliki do opublikowania.</span><span class="sxs-lookup"><span data-stu-id="30ab4-129">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="30ab4-130">Uruchom następujące polecenie w systemie Linux przy użyciu polecenia `zip` .</span><span class="sxs-lookup"><span data-stu-id="30ab4-130">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="30ab4-131">Przekaż następujące elementy do rozproszonego systemu plików (np. S3), do którego klaster ma dostęp:</span><span class="sxs-lookup"><span data-stu-id="30ab4-131">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="30ab4-132">`microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar`: Ten plik JAR jest dołączony jako część pakietu NuGet [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) i znajduje się w katalogu danych wyjściowych kompilacji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="30ab4-132">`microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="30ab4-133">Pliki (takie jak pliki zależności lub typowe dane dostępne dla każdego pracownika) lub zestawy (takie jak biblioteki DLL, które zawierają zdefiniowane przez użytkownika funkcje lub biblioteki, od których zależy aplikacja), zostaną umieszczone w katalogu roboczym każdego wykonawcy.</span><span class="sxs-lookup"><span data-stu-id="30ab4-133">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="30ab4-134">Wdrażanie w usłudze Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="30ab4-134">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="30ab4-135">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) to zarządzana platforma klastra, która upraszcza uruchamianie platform danych Big Data w systemie AWS.</span><span class="sxs-lookup"><span data-stu-id="30ab4-135">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE]
> <span data-ttu-id="30ab4-136">System Amazon EMR Spark jest oparty na systemie Linux.</span><span class="sxs-lookup"><span data-stu-id="30ab4-136">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="30ab4-137">W związku z tym, Jeśli interesuje Cię wdrażanie aplikacji w usłudze Amazon EMR Spark, upewnij się, że aplikacja jest zgodna .NET Standard i że używasz [kompilatora .NET Core](https://dotnet.microsoft.com/download) do kompilowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="30ab4-137">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="30ab4-138">Wdróż aplikację Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="30ab4-138">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="30ab4-139">Ten krok jest wymagany tylko podczas tworzenia klastra.</span><span class="sxs-lookup"><span data-stu-id="30ab4-139">This step is only required at cluster creation.</span></span>

<span data-ttu-id="30ab4-140">Uruchamiany `install-worker.sh` podczas tworzenia klastra za pomocą [akcji Bootstrap](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span><span class="sxs-lookup"><span data-stu-id="30ab4-140">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="30ab4-141">Uruchom następujące polecenie w systemie Linux przy użyciu interfejsu wiersza polecenia AWS.</span><span class="sxs-lookup"><span data-stu-id="30ab4-141">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr create-cluster \
--name "Test cluster" \
--release-label emr-5.23.0 \
--use-default-roles \
--ec2-attributes KeyName=myKey \
--applications Name=Spark \
--instance-count 3 \
--instance-type m1.medium \
--bootstrap-actions Path=s3://mybucket/<some dir>/install-worker.sh,Name="Install Microsoft.Spark.Worker",Args=["aws","s3://mybucket/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz","/usr/local/bin"]
```

## <a name="run-your-app"></a><span data-ttu-id="30ab4-142">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="30ab4-142">Run your app</span></span>

<span data-ttu-id="30ab4-143">Istnieją dwa sposoby uruchamiania aplikacji w usłudze Amazon EMR Spark: Spark-Submit i Amazon EMR.</span><span class="sxs-lookup"><span data-stu-id="30ab4-143">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="30ab4-144">Korzystanie z platformy Spark — przesyłanie</span><span class="sxs-lookup"><span data-stu-id="30ab4-144">Use spark-submit</span></span>

<span data-ttu-id="30ab4-145">Za pomocą polecenia [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) można przesłać Apache Spark zadań programu .NET do usługi Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="30ab4-145">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="30ab4-146">`ssh` w jednym z węzłów w klastrze.</span><span class="sxs-lookup"><span data-stu-id="30ab4-146">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="30ab4-147">Uruchom polecenie `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="30ab4-147">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="30ab4-148">Korzystanie z kroków EMR Amazon</span><span class="sxs-lookup"><span data-stu-id="30ab4-148">Use Amazon EMR Steps</span></span>

<span data-ttu-id="30ab4-149">[Procedury Amazon EMR](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) mogą służyć do przesyłania zadań do platformy Spark zainstalowanej w klastrze EMR.</span><span class="sxs-lookup"><span data-stu-id="30ab4-149">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="30ab4-150">Uruchom następujące polecenie w systemie Linux przy użyciu interfejsu wiersza polecenia AWS.</span><span class="sxs-lookup"><span data-stu-id="30ab4-150">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="30ab4-151">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="30ab4-151">Next steps</span></span>

<span data-ttu-id="30ab4-152">W tym samouczku wdrożono aplikację .NET for Apache Spark w usłudze Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="30ab4-152">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="30ab4-153">W przypadku platformy .NET do Apache Spark przykładowe projekty przejdź do witryny GitHub.</span><span class="sxs-lookup"><span data-stu-id="30ab4-153">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="30ab4-154">.NET for Apache Spark — przykłady</span><span class="sxs-lookup"><span data-stu-id="30ab4-154">.NET for Apache Spark samples</span></span>](https://github.com/dotnet/spark/tree/master/examples)
