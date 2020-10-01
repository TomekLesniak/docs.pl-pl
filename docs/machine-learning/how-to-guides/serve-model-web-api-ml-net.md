---
title: Wdrażanie modelu w ASP.NET Core Web API
description: Obsługiwanie modelu uczenia maszynowego w usłudze ML.NET tonacji Analysis za pośrednictwem Internetu przy użyciu interfejsu Web API ASP.NET Core
ms.date: 11/07/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: f588d4681ee277ad15b50d5553473b1c9e84d578
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608767"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="a4f6f-103">Wdrażanie modelu w ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="a4f6f-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="a4f6f-104">Dowiedz się, jak obsłużyć wstępnie szkolony model uczenia maszynowego ML.NET w sieci Web przy użyciu ASP.NET Core internetowego interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="a4f6f-105">Obsługa modelu przez internetowy interfejs API umożliwia prognozowanie za pośrednictwem standardowych metod HTTP.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a4f6f-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="a4f6f-106">Prerequisites</span></span>

- <span data-ttu-id="a4f6f-107">[Program Visual studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) lub nowszy albo program visual Studio 2017 w wersji 15,6 lub nowszej z zainstalowanym obciążeniem "Programowanie dla wielu platform" platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-107">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="a4f6f-108">Narzędzia.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-108">PowerShell.</span></span>
- <span data-ttu-id="a4f6f-109">Model wstępnie szkolony.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-109">Pre-trained model.</span></span> <span data-ttu-id="a4f6f-110">Użyj [samouczka analiza tonacji ml.NET](../tutorials/sentiment-analysis.md) , aby skompilować własny model lub pobrać ten [wstępnie szkolony model uczenia maszynowego analizy tonacji](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="a4f6f-110">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="a4f6f-111">Tworzenie projektu interfejsu API sieci Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a4f6f-111">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="a4f6f-112">Otwórz program Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-112">Open Visual Studio 2017.</span></span> <span data-ttu-id="a4f6f-113">Wybierz pozycję **plik > nowy > projekt** na pasku menu.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-113">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="a4f6f-114">W oknie dialogowym Nowy projekt wybierz węzeł **Visual C#** , a następnie węzeł **sieci Web** .</span><span class="sxs-lookup"><span data-stu-id="a4f6f-114">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="a4f6f-115">Następnie wybierz szablon projektu **aplikacji sieci Web ASP.NET Core** .</span><span class="sxs-lookup"><span data-stu-id="a4f6f-115">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="a4f6f-116">W polu tekstowym **Nazwa** wpisz "SentimentAnalysisWebAPI", a następnie wybierz przycisk **OK** .</span><span class="sxs-lookup"><span data-stu-id="a4f6f-116">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="a4f6f-117">W oknie, w którym są wyświetlane różne typy projektów ASP.NET Core, wybierz pozycję **interfejs API** i wybierz przycisk **OK** .</span><span class="sxs-lookup"><span data-stu-id="a4f6f-117">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="a4f6f-118">Utwórz katalog o nazwie *MLModels* w projekcie, aby zapisać wstępnie utworzone pliki modelu uczenia maszynowego:</span><span class="sxs-lookup"><span data-stu-id="a4f6f-118">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="a4f6f-119">W Eksplorator rozwiązań kliknij prawym przyciskiem myszy projekt i wybierz polecenie Dodaj > nowy folder.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-119">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="a4f6f-120">Wpisz "MLModels" i naciśnij klawisz ENTER.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-120">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="a4f6f-121">Zainstaluj **pakiet NuGet Microsoft.ml**:</span><span class="sxs-lookup"><span data-stu-id="a4f6f-121">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="a4f6f-122">W Eksplorator rozwiązań kliknij prawym przyciskiem myszy projekt i wybierz polecenie **Zarządzaj pakietami NuGet**.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-122">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a4f6f-123">Wybierz pozycję "nuget.org" jako źródło pakietu, wybierz kartę Przeglądaj, Wyszukaj pozycję **Microsoft.ml**, wybierz ten pakiet z listy, a następnie wybierz przycisk Instaluj.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-123">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="a4f6f-124">Wybierz przycisk **OK** w oknie dialogowym **Podgląd zmian** , a następnie **Wybierz przycisk** Akceptuję w oknie dialogowym akceptacji licencji, jeśli zgadzasz się z postanowieniami licencyjnymi dotyczącymi wymienionych pakietów.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-124">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="a4f6f-125">Zainstaluj **pakiet Nuget Microsoft.Extensions.ml**:</span><span class="sxs-lookup"><span data-stu-id="a4f6f-125">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="a4f6f-126">W Eksplorator rozwiązań kliknij prawym przyciskiem myszy projekt i wybierz polecenie **Zarządzaj pakietami NuGet**.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-126">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a4f6f-127">Wybierz pozycję "nuget.org" jako źródło pakietu, wybierz kartę Przeglądaj, Wyszukaj pozycję **Microsoft.Extensions.ml**, wybierz ten pakiet z listy, a następnie wybierz przycisk Instaluj.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-127">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="a4f6f-128">Wybierz przycisk **OK** w oknie dialogowym **Podgląd zmian** , a następnie **Wybierz przycisk** Akceptuję w oknie dialogowym akceptacji licencji, jeśli zgadzasz się z postanowieniami licencyjnymi dotyczącymi wymienionych pakietów.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-128">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="a4f6f-129">Dodaj model do projektu interfejsu API sieci Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a4f6f-129">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="a4f6f-130">Skopiuj wstępnie utworzony model do katalogu *MLModels*</span><span class="sxs-lookup"><span data-stu-id="a4f6f-130">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="a4f6f-131">W Eksplorator rozwiązań kliknij prawym przyciskiem myszy plik zip modelu i wybierz polecenie Właściwości.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-131">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="a4f6f-132">W obszarze Zaawansowane Zmień wartość opcji Kopiuj do katalogu wyjściowego na Kopiuj, jeśli nowszy.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-132">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="a4f6f-133">Tworzenie modeli danych</span><span class="sxs-lookup"><span data-stu-id="a4f6f-133">Create data models</span></span>

<span data-ttu-id="a4f6f-134">Należy utworzyć klasy dla danych wejściowych i prognoz.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-134">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="a4f6f-135">Dodaj nową klasę do projektu:</span><span class="sxs-lookup"><span data-stu-id="a4f6f-135">Add a new class to your project:</span></span>

1. <span data-ttu-id="a4f6f-136">Utwórz katalog o nazwie *Datamodels* w projekcie, aby zapisać modele danych:</span><span class="sxs-lookup"><span data-stu-id="a4f6f-136">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="a4f6f-137">W Eksplorator rozwiązań kliknij prawym przyciskiem myszy projekt i wybierz polecenie Dodaj > nowy folder.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-137">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="a4f6f-138">Wpisz "datamodels" i naciśnij klawisz **Enter**.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-138">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="a4f6f-139">W Eksplorator rozwiązań kliknij prawym przyciskiem myszy katalog *Datamodels* , a następnie wybierz pozycję Dodaj > nowy element.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-139">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="a4f6f-140">W oknie dialogowym **Dodaj nowy element** wybierz pozycję **Klasa** i zmień wartość pola **Nazwa** na *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-140">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="a4f6f-141">Następnie wybierz przycisk **Dodaj** .</span><span class="sxs-lookup"><span data-stu-id="a4f6f-141">Then, select the **Add** button.</span></span> <span data-ttu-id="a4f6f-142">Plik *SentimentData.cs* zostanie otwarty w edytorze kodu.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-142">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="a4f6f-143">Dodaj następującą instrukcję using na początku *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="a4f6f-143">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="a4f6f-144">Usuń istniejącą definicję klasy i Dodaj następujący kod do pliku **SentimentData.cs** :</span><span class="sxs-lookup"><span data-stu-id="a4f6f-144">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

    ```csharp
    public class SentimentData
    {
        [LoadColumn(0)]
        public string SentimentText;

        [LoadColumn(1)]
        [ColumnName("Label")]
        public bool Sentiment;
    }
    ```

4. <span data-ttu-id="a4f6f-145">W Eksplorator rozwiązań kliknij prawym przyciskiem myszy katalog *Datamodels* , a następnie wybierz pozycję **Dodaj > nowy element**.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-145">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="a4f6f-146">W oknie dialogowym **Dodaj nowy element** wybierz pozycję **Klasa** i zmień wartość pola **Nazwa** na *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-146">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="a4f6f-147">Następnie wybierz przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-147">Then, select the Add button.</span></span> <span data-ttu-id="a4f6f-148">Plik *SentimentPrediction.cs* zostanie otwarty w edytorze kodu.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-148">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="a4f6f-149">Dodaj następującą instrukcję using na początku *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="a4f6f-149">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="a4f6f-150">Usuń istniejącą definicję klasy i Dodaj następujący kod do pliku *SentimentPrediction.cs* :</span><span class="sxs-lookup"><span data-stu-id="a4f6f-150">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="a4f6f-151">`SentimentPrediction` dziedziczy z `SentimentData` .</span><span class="sxs-lookup"><span data-stu-id="a4f6f-151">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="a4f6f-152">Dzięki temu można łatwiej zobaczyć oryginalne dane we `SentimentText` właściwości wraz z danymi wyjściowymi generowanymi przez model.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-152">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span>

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="a4f6f-153">Zarejestruj PredictionEnginePool do użycia w aplikacji</span><span class="sxs-lookup"><span data-stu-id="a4f6f-153">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="a4f6f-154">Aby wykonać pojedyncze prognozowanie, należy utworzyć [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) .</span><span class="sxs-lookup"><span data-stu-id="a4f6f-154">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="a4f6f-155">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) nie jest bezpieczny wątkowo.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-155">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="a4f6f-156">Ponadto należy utworzyć wystąpienie go wszędzie tam, gdzie jest to potrzebne w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-156">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="a4f6f-157">Gdy aplikacja zostanie powiększona, ten proces może być niezarządzany.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-157">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="a4f6f-158">Aby zwiększyć wydajność i bezpieczeństwo wątków, należy użyć kombinacji iniekcji zależności i `PredictionEnginePool` usługi, która tworzy [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) obiekty do użycia w całej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-158">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

<span data-ttu-id="a4f6f-159">Poniższy link zawiera więcej informacji, jeśli chcesz dowiedzieć się więcej o [iniekcji zależności w ASP.NET Core](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="a4f6f-159">The following link provides more information if you want to learn more about [dependency injection in ASP.NET Core](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="a4f6f-160">Otwórz klasę *Startup.cs* i Dodaj następującą instrukcję using na początku pliku:</span><span class="sxs-lookup"><span data-stu-id="a4f6f-160">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="a4f6f-161">Dodaj następujący kod do metody *ConfigureServices* :</span><span class="sxs-lookup"><span data-stu-id="a4f6f-161">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
        .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
    ```

<span data-ttu-id="a4f6f-162">Na wysokim poziomie ten kod inicjuje automatycznie obiekty i usługi do późniejszego użycia, gdy żądanie jest wymagane przez aplikację, a nie trzeba jej wykonać ręcznie.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-162">At a high level, this code initializes the objects and services automatically for later use when requested by the application instead of having to manually do it.</span></span>

<span data-ttu-id="a4f6f-163">Modele uczenia maszynowego nie są statyczne.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-163">Machine learning models are not static.</span></span> <span data-ttu-id="a4f6f-164">Po udostępnieniu nowych danych szkoleniowych model zostanie ponownie przeszkolony i wdrożony ponownie.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-164">As new training data becomes available, the model is retrained and redeployed.</span></span> <span data-ttu-id="a4f6f-165">Jednym ze sposobów uzyskania najnowszej wersji modelu do aplikacji jest ponowne wdrożenie całej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-165">One way to get the latest version of the model into your application is to redeploy the entire application.</span></span> <span data-ttu-id="a4f6f-166">Powoduje to jednak wprowadzenie przestojów aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-166">However, this introduces application downtime.</span></span> <span data-ttu-id="a4f6f-167">`PredictionEnginePool`Usługa udostępnia mechanizm umożliwiający ponowne załadowanie zaktualizowanego modelu bez przełączania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-167">The `PredictionEnginePool` service provides a mechanism to reload an updated model without taking your application down.</span></span>

<span data-ttu-id="a4f6f-168">Ustaw `watchForChanges` parametr na `true` , a następnie uruchomi polecenie, `PredictionEnginePool` [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) które nasłuchuje w systemie plików powiadomienia o zmianie, i zgłasza zdarzenia w przypadku zmiany pliku.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-168">Set the `watchForChanges` parameter to `true`, and the `PredictionEnginePool` starts a [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) that listens to the file system change notifications and raises events when there is a change to the file.</span></span> <span data-ttu-id="a4f6f-169">Zostanie wyświetlony komunikat z prośbą o `PredictionEnginePool` automatyczne załadowanie modelu.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-169">This prompts the `PredictionEnginePool` to automatically reload the model.</span></span>

<span data-ttu-id="a4f6f-170">Model jest identyfikowany przez `modelName` parametr, aby można było ponownie załadować więcej niż jeden model dla aplikacji po zmianie.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-170">The model is identified by the `modelName` parameter so that more than one model per application can be reloaded upon change.</span></span>

> [!TIP]
> <span data-ttu-id="a4f6f-171">Alternatywnie możesz użyć `FromUri` metody podczas pracy z modelami przechowywanymi zdalnie.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-171">Alternatively, you can use the `FromUri` method when working with models stored remotely.</span></span> <span data-ttu-id="a4f6f-172">Zamiast oglądać zdarzenia ze zmienionymi plikami, `FromUri` sonduje lokalizację zdalną pod kątem zmian.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-172">Rather than watching for file changed events, `FromUri` polls the remote location for changes.</span></span> <span data-ttu-id="a4f6f-173">Interwał sondowania jest wartością domyślną 5 minut.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-173">The polling interval defaults to 5 minutes.</span></span> <span data-ttu-id="a4f6f-174">Interwał sondowania można zwiększyć lub zmniejszyć w zależności od wymagań aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-174">You can increase or decrease the polling interval based on your application's requirements.</span></span> <span data-ttu-id="a4f6f-175">W poniższym przykładzie kodu `PredictionEnginePool` sonduje model przechowywany w określonym identyfikatorze URI co minutę.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-175">In the code sample below, the `PredictionEnginePool` polls the model stored at the specified URI every minute.</span></span>
>
>```csharp
>services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="create-predict-controller"></a><span data-ttu-id="a4f6f-176">Utwórz kontroler predykcyjny</span><span class="sxs-lookup"><span data-stu-id="a4f6f-176">Create Predict controller</span></span>

<span data-ttu-id="a4f6f-177">Aby przetwarzać przychodzące żądania HTTP, Utwórz kontroler.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-177">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="a4f6f-178">W Eksplorator rozwiązań kliknij prawym przyciskiem myszy katalog *controllers* , a następnie wybierz pozycję **Dodaj kontroler >**.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-178">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="a4f6f-179">W oknie dialogowym **Dodaj nowy element** wybierz pozycję **kontroler interfejsu API puste** i wybierz pozycję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-179">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="a4f6f-180">W oknie monitu Zmień **nazwę kontrolera** na *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-180">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="a4f6f-181">Następnie wybierz przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-181">Then, select the Add button.</span></span> <span data-ttu-id="a4f6f-182">Plik *PredictController.cs* zostanie otwarty w edytorze kodu.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-182">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="a4f6f-183">Dodaj następującą instrukcję using na początku *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="a4f6f-183">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="a4f6f-184">Usuń istniejącą definicję klasy i Dodaj następujący kod do pliku *PredictController.cs* :</span><span class="sxs-lookup"><span data-stu-id="a4f6f-184">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

    ```csharp
    public class PredictController : ControllerBase
    {
        private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

        public PredictController(PredictionEnginePool<SentimentData,SentimentPrediction> predictionEnginePool)
        {
            _predictionEnginePool = predictionEnginePool;
        }

        [HttpPost]
        public ActionResult<string> Post([FromBody] SentimentData input)
        {
            if(!ModelState.IsValid)
            {
                return BadRequest();
            }

            SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

<span data-ttu-id="a4f6f-185">Ten kod przypisuje `PredictionEnginePool` przez przekazanie go do konstruktora kontrolera, który uzyskuje się za pośrednictwem iniekcji zależności.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-185">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="a4f6f-186">Następnie `Predict` `Post` Metoda kontrolera używa `PredictionEnginePool` do wykonywania prognoz przy użyciu `SentimentAnalysisModel` zarejestrowanej w `Startup` klasie i zwraca wyniki z powrotem do użytkownika, jeśli to się powiedzie.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-186">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions using the `SentimentAnalysisModel` registered in the `Startup` class and returns the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="a4f6f-187">Testowanie lokalnego interfejsu API sieci Web</span><span class="sxs-lookup"><span data-stu-id="a4f6f-187">Test web API locally</span></span>

<span data-ttu-id="a4f6f-188">Po skonfigurowaniu wszystkiego czas na przetestowanie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-188">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="a4f6f-189">Uruchom aplikację.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-189">Run the application.</span></span>
1. <span data-ttu-id="a4f6f-190">Otwórz program PowerShell i wprowadź następujący kod, gdzie PORT jest portem, na którym nasłuchuje aplikacja.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-190">Open PowerShell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="a4f6f-191">Jeśli to się powiedzie, dane wyjściowe powinny wyglądać podobnie do poniższego tekstu:</span><span class="sxs-lookup"><span data-stu-id="a4f6f-191">If successful, the output should look similar to the text below:</span></span>

    ```powershell
    Negative
    ```

<span data-ttu-id="a4f6f-192">Gratulacje!</span><span class="sxs-lookup"><span data-stu-id="a4f6f-192">Congratulations!</span></span> <span data-ttu-id="a4f6f-193">Udało Ci się pomyślnie obsłużyć model, aby przekonywać prognoz przez Internet przy użyciu ASP.NET Core internetowego interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="a4f6f-193">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a4f6f-194">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="a4f6f-194">Next Steps</span></span>

- [<span data-ttu-id="a4f6f-195">Wdróż na platformie Azure</span><span class="sxs-lookup"><span data-stu-id="a4f6f-195">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs#deploy-the-app-to-azure)
