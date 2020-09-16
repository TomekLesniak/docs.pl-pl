---
title: Jak korzystać z interfejsu API zautomatyzowanej ML.NET ML
description: Interfejs API zautomatyzowanej sieci ML.NET automatyzuje proces tworzenia modelu i generuje model gotowy do wdrożenia. Informacje na temat opcji, których można użyć do konfigurowania automatycznych zadań uczenia maszynowego.
ms.date: 12/18/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b1ef526301e01e1e75e71e0646f4d11e68215d69
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540735"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a><span data-ttu-id="51032-104">Jak korzystać z interfejsu API automatycznego uczenia maszynowego ML.NET</span><span class="sxs-lookup"><span data-stu-id="51032-104">How to use the ML.NET automated machine learning API</span></span>

<span data-ttu-id="51032-105">Automatyczne Uczenie maszynowe (AutoML) automatyzuje proces stosowania uczenia maszynowego do danych.</span><span class="sxs-lookup"><span data-stu-id="51032-105">Automated machine learning (AutoML) automates the process of applying machine learning to data.</span></span> <span data-ttu-id="51032-106">Mając zestaw danych, można uruchomić **eksperyment** AutoML, aby wykonać iterację różnych danych featurizations, algorytmów uczenia maszynowego i parametrów do wybierania najlepszego modelu.</span><span class="sxs-lookup"><span data-stu-id="51032-106">Given a dataset, you can run an AutoML **experiment** to iterate over different data featurizations, machine learning algorithms, and hyperparameters to select the best model.</span></span>

> [!NOTE]
> <span data-ttu-id="51032-107">Ten temat odnosi się do zautomatyzowanego interfejsu API uczenia maszynowego dla usługi ML.NET, który jest obecnie w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="51032-107">This topic refers to the automated machine learning API for ML.NET, which is currently in preview.</span></span> <span data-ttu-id="51032-108">Materiał może ulec zmianie.</span><span class="sxs-lookup"><span data-stu-id="51032-108">Material may be subject to change.</span></span>

## <a name="load-data"></a><span data-ttu-id="51032-109">Ładowanie danych</span><span class="sxs-lookup"><span data-stu-id="51032-109">Load data</span></span>

<span data-ttu-id="51032-110">Automatyczne Uczenie maszynowe obsługuje ładowanie zestawu danych do [IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="51032-110">Automated machine learning supports loading a dataset into an [IDataView](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="51032-111">Dane mogą mieć postać plików z wartościami rozdzielanymi tabulatorami (TSV) i plików z wartościami rozdzielanymi przecinkami (CSV).</span><span class="sxs-lookup"><span data-stu-id="51032-111">Data can be in the form of tab-separated value (TSV) files and comma separated value (CSV) files.</span></span>

<span data-ttu-id="51032-112">Przykład:</span><span class="sxs-lookup"><span data-stu-id="51032-112">Example:</span></span>

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    // ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a><span data-ttu-id="51032-113">Wybierz typ zadania uczenia maszynowego</span><span class="sxs-lookup"><span data-stu-id="51032-113">Select the machine learning task type</span></span>

<span data-ttu-id="51032-114">Przed utworzeniem eksperymentu należy określić rodzaj problemu z uczeniem maszynowym, który ma zostać rozwiązany.</span><span class="sxs-lookup"><span data-stu-id="51032-114">Before creating an experiment, determine the kind of machine learning problem you want to solve.</span></span> <span data-ttu-id="51032-115">Automatyczne Uczenie maszynowe obsługuje następujące zadania w ML:</span><span class="sxs-lookup"><span data-stu-id="51032-115">Automated machine learning supports the following ML tasks:</span></span>

* <span data-ttu-id="51032-116">Klasyfikacja binarna</span><span class="sxs-lookup"><span data-stu-id="51032-116">Binary Classification</span></span>
* <span data-ttu-id="51032-117">Klasyfikacja wieloklasowa</span><span class="sxs-lookup"><span data-stu-id="51032-117">Multiclass Classification</span></span>
* <span data-ttu-id="51032-118">Regresja</span><span class="sxs-lookup"><span data-stu-id="51032-118">Regression</span></span>
* <span data-ttu-id="51032-119">Zalecenie</span><span class="sxs-lookup"><span data-stu-id="51032-119">Recommendation</span></span>

## <a name="create-experiment-settings"></a><span data-ttu-id="51032-120">Utwórz ustawienia eksperymentu</span><span class="sxs-lookup"><span data-stu-id="51032-120">Create experiment settings</span></span>

<span data-ttu-id="51032-121">Utwórz ustawienia eksperymentu dla typu zadania o określonej ML:</span><span class="sxs-lookup"><span data-stu-id="51032-121">Create experiment settings for the determined ML task type:</span></span>

* <span data-ttu-id="51032-122">Klasyfikacja binarna</span><span class="sxs-lookup"><span data-stu-id="51032-122">Binary Classification</span></span>

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* <span data-ttu-id="51032-123">Klasyfikacja wieloklasowa</span><span class="sxs-lookup"><span data-stu-id="51032-123">Multiclass Classification</span></span>

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* <span data-ttu-id="51032-124">Regresja</span><span class="sxs-lookup"><span data-stu-id="51032-124">Regression</span></span>

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

* <span data-ttu-id="51032-125">Zalecenie</span><span class="sxs-lookup"><span data-stu-id="51032-125">Recommendation</span></span>

  ```csharp
  var experimentSettings = new RecommendationExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a><span data-ttu-id="51032-126">Konfigurowanie ustawień eksperymentu</span><span class="sxs-lookup"><span data-stu-id="51032-126">Configure experiment settings</span></span>

<span data-ttu-id="51032-127">Eksperymenty są wysoce konfigurowalne.</span><span class="sxs-lookup"><span data-stu-id="51032-127">Experiments are highly configurable.</span></span> <span data-ttu-id="51032-128">Zobacz dokumentację [interfejsu API AutoML](/dotnet/api/microsoft.ml.automl?view=ml-dotnet-preview) , aby uzyskać pełną listę ustawień konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="51032-128">See the [AutoML API docs](/dotnet/api/microsoft.ml.automl?view=ml-dotnet-preview) for a full list of configuration settings.</span></span>

<span data-ttu-id="51032-129">Oto niektóre przykłady:</span><span class="sxs-lookup"><span data-stu-id="51032-129">Some examples include:</span></span>

1. <span data-ttu-id="51032-130">Określ maksymalny czas działania eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="51032-130">Specify the maximum time that the experiment is allowed to run.</span></span>

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. <span data-ttu-id="51032-131">Użyj tokenu anulowania, aby anulować eksperyment przed zaplanowaniem jego zakończenia.</span><span class="sxs-lookup"><span data-stu-id="51032-131">Use a cancellation token to cancel the experiment before it is scheduled to finish.</span></span>

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. <span data-ttu-id="51032-132">Określ inną metrykę optymalizacji.</span><span class="sxs-lookup"><span data-stu-id="51032-132">Specify a different optimizing metric.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. <span data-ttu-id="51032-133">`CacheDirectory`Ustawienie to wskaźnik do katalogu, w którym wszystkie modele przeszkolone podczas zadania AutoML zostaną zapisane.</span><span class="sxs-lookup"><span data-stu-id="51032-133">The `CacheDirectory` setting is a pointer to a directory where all models trained during the AutoML task will be saved.</span></span> <span data-ttu-id="51032-134">Jeśli `CacheDirectory` jest ustawiona na wartość null, modele będą przechowywane w pamięci zamiast zapisywać na dysku.</span><span class="sxs-lookup"><span data-stu-id="51032-134">If `CacheDirectory` is set to null, models will be kept in memory instead of written to disk.</span></span>

    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. <span data-ttu-id="51032-135">Poinstruuj zautomatyzowany ML, aby nie używać niektórych instruktorów.</span><span class="sxs-lookup"><span data-stu-id="51032-135">Instruct automated ML not to use certain trainers.</span></span>

    <span data-ttu-id="51032-136">Domyślna lista instruktorów do optymalizacji są zbadane według poszczególnych zadań.</span><span class="sxs-lookup"><span data-stu-id="51032-136">A default list of trainers to optimize are explored per task.</span></span> <span data-ttu-id="51032-137">Tę listę można modyfikować dla każdego eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="51032-137">This list can be modified for each experiment.</span></span> <span data-ttu-id="51032-138">Na przykład, instruktorzy, którzy działają wolno w zestawie danych, można usunąć z listy.</span><span class="sxs-lookup"><span data-stu-id="51032-138">For instance, trainers that run slowly on your dataset can be removed from the list.</span></span> <span data-ttu-id="51032-139">Aby zoptymalizować na jednym konkretnym wywołaniu Trainer `experimentSettings.Trainers.Clear()` , Dodaj Trainer, którego chcesz użyć.</span><span class="sxs-lookup"><span data-stu-id="51032-139">To optimize on one specific trainer call `experimentSettings.Trainers.Clear()`, then add the trainer that you want to use.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

<span data-ttu-id="51032-140">Listę obsługiwanych zadań instruktorów na ML można znaleźć w odpowiadającym jej poniższym łączu:</span><span class="sxs-lookup"><span data-stu-id="51032-140">The list of supported trainers per ML task can be found at the corresponding link below:</span></span>

* [<span data-ttu-id="51032-141">Obsługiwane algorytmy klasyfikacji binarnej</span><span class="sxs-lookup"><span data-stu-id="51032-141">Supported Binary Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [<span data-ttu-id="51032-142">Obsługiwane algorytmy klasyfikacji wieloklasowej</span><span class="sxs-lookup"><span data-stu-id="51032-142">Supported Multiclass Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [<span data-ttu-id="51032-143">Obsługiwane algorytmy regresji</span><span class="sxs-lookup"><span data-stu-id="51032-143">Supported Regression Algorithms</span></span>](xref:Microsoft.ML.AutoML.RegressionTrainer)
* [<span data-ttu-id="51032-144">Obsługiwane algorytmy rekomendacji</span><span class="sxs-lookup"><span data-stu-id="51032-144">Supported Recommendation Algorithms</span></span>](xref:Microsoft.ML.AutoML.RecommendationTrainer)

## <a name="optimizing-metric"></a><span data-ttu-id="51032-145">Optymalizowanie metryki</span><span class="sxs-lookup"><span data-stu-id="51032-145">Optimizing metric</span></span>

<span data-ttu-id="51032-146">Metryka optymalizacji, jak pokazano w powyższym przykładzie, określa metrykę do zoptymalizowania podczas uczenia modelu.</span><span class="sxs-lookup"><span data-stu-id="51032-146">The optimizing metric, as shown in the example above, determines the metric to be optimized during model training.</span></span> <span data-ttu-id="51032-147">Metryka optymalizacji, którą można wybrać, zależy od wybranego typu zadania.</span><span class="sxs-lookup"><span data-stu-id="51032-147">The optimizing metric you can select is determined by the task type you choose.</span></span> <span data-ttu-id="51032-148">Poniżej znajduje się lista dostępnych metryk.</span><span class="sxs-lookup"><span data-stu-id="51032-148">Below is a list of available metrics.</span></span>

|[<span data-ttu-id="51032-149">Klasyfikacja binarna</span><span class="sxs-lookup"><span data-stu-id="51032-149">Binary Classification</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [<span data-ttu-id="51032-150">Klasyfikacja wieloklasowa</span><span class="sxs-lookup"><span data-stu-id="51032-150">Multiclass Classification</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[<span data-ttu-id="51032-151">Zalecenie dotyczące & regresji</span><span class="sxs-lookup"><span data-stu-id="51032-151">Regression & Recommendation</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|<span data-ttu-id="51032-152">Odpowiedni</span><span class="sxs-lookup"><span data-stu-id="51032-152">Accuracy</span></span>| <span data-ttu-id="51032-153">LogLoss</span><span class="sxs-lookup"><span data-stu-id="51032-153">LogLoss</span></span> | <span data-ttu-id="51032-154">RSquared</span><span class="sxs-lookup"><span data-stu-id="51032-154">RSquared</span></span>
|<span data-ttu-id="51032-155">AreaUnderPrecisionRecallCurve</span><span class="sxs-lookup"><span data-stu-id="51032-155">AreaUnderPrecisionRecallCurve</span></span> | <span data-ttu-id="51032-156">LogLossReduction</span><span class="sxs-lookup"><span data-stu-id="51032-156">LogLossReduction</span></span> | <span data-ttu-id="51032-157">MeanAbsoluteError</span><span class="sxs-lookup"><span data-stu-id="51032-157">MeanAbsoluteError</span></span>
|<span data-ttu-id="51032-158">AreaUnderRocCurve</span><span class="sxs-lookup"><span data-stu-id="51032-158">AreaUnderRocCurve</span></span> | <span data-ttu-id="51032-159">MacroAccuracy</span><span class="sxs-lookup"><span data-stu-id="51032-159">MacroAccuracy</span></span> | <span data-ttu-id="51032-160">MeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="51032-160">MeanSquaredError</span></span>
|<span data-ttu-id="51032-161">F1Score</span><span class="sxs-lookup"><span data-stu-id="51032-161">F1Score</span></span> | <span data-ttu-id="51032-162">Mikrodokładność</span><span class="sxs-lookup"><span data-stu-id="51032-162">MicroAccuracy</span></span> | <span data-ttu-id="51032-163">RootMeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="51032-163">RootMeanSquaredError</span></span>
|<span data-ttu-id="51032-164">NegativePrecision</span><span class="sxs-lookup"><span data-stu-id="51032-164">NegativePrecision</span></span> | <span data-ttu-id="51032-165">TopKAccuracy</span><span class="sxs-lookup"><span data-stu-id="51032-165">TopKAccuracy</span></span>
|<span data-ttu-id="51032-166">NegativeRecall</span><span class="sxs-lookup"><span data-stu-id="51032-166">NegativeRecall</span></span> |
|<span data-ttu-id="51032-167">PositivePrecision</span><span class="sxs-lookup"><span data-stu-id="51032-167">PositivePrecision</span></span>
|<span data-ttu-id="51032-168">PositiveRecall</span><span class="sxs-lookup"><span data-stu-id="51032-168">PositiveRecall</span></span>

## <a name="data-pre-processing-and-featurization"></a><span data-ttu-id="51032-169">Wstępne przetwarzanie i cechowania danych</span><span class="sxs-lookup"><span data-stu-id="51032-169">Data pre-processing and featurization</span></span>

> [!NOTE]
> <span data-ttu-id="51032-170">W kolumnie funkcji obsługiwane są tylko typy <xref:System.Boolean> , <xref:System.Single> i <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="51032-170">The feature column only supported types of <xref:System.Boolean>, <xref:System.Single>, and <xref:System.String>.</span></span>

<span data-ttu-id="51032-171">Przetwarzanie wstępne danych odbywa się domyślnie, a następujące kroki są wykonywane automatycznie:</span><span class="sxs-lookup"><span data-stu-id="51032-171">Data pre-processing happens by default and the following steps are performed automatically for you:</span></span>

1. <span data-ttu-id="51032-172">Funkcje upuszczania bez użytecznych informacji</span><span class="sxs-lookup"><span data-stu-id="51032-172">Drop features with no useful information</span></span>

    <span data-ttu-id="51032-173">Porzuć funkcje bez użytecznych informacji dotyczących szkoleń i zestawów walidacji.</span><span class="sxs-lookup"><span data-stu-id="51032-173">Drop features with no useful information from training and validation sets.</span></span> <span data-ttu-id="51032-174">Obejmują one funkcje, w których brakuje wszystkich wartości, takich same jak wszystkie wiersze, lub z bardzo dużą kardynalnością (np. skrótami, identyfikatorami lub identyfikatorami GUID).</span><span class="sxs-lookup"><span data-stu-id="51032-174">These include features with all values missing, same value across all rows or with extremely high cardinality (e.g., hashes, IDs or GUIDs).</span></span>

1. <span data-ttu-id="51032-175">Brak wskazania wartości i nie należy ich przypisywaniu</span><span class="sxs-lookup"><span data-stu-id="51032-175">Missing value indication and imputation</span></span>

    <span data-ttu-id="51032-176">Wypełnij brakujące komórki wartości wartością domyślną dla typu danych.</span><span class="sxs-lookup"><span data-stu-id="51032-176">Fill missing value cells with the default value for the datatype.</span></span> <span data-ttu-id="51032-177">Dołącz funkcje wskaźnika z taką samą liczbą gniazd jak w przypadku kolumny wejściowej.</span><span class="sxs-lookup"><span data-stu-id="51032-177">Append indicator features with the same number of slots as the input column.</span></span> <span data-ttu-id="51032-178">Wartość w funkcjach dołączanych wskaźników jest w `1` przypadku braku wartości w kolumnie wejściowej i `0` w przeciwnym razie.</span><span class="sxs-lookup"><span data-stu-id="51032-178">The value in the appended indicator features is `1` if the value in the input column is missing and `0` otherwise.</span></span>

1. <span data-ttu-id="51032-179">Generuj dodatkowe funkcje</span><span class="sxs-lookup"><span data-stu-id="51032-179">Generate additional features</span></span>

    <span data-ttu-id="51032-180">Dla funkcji tekstowych: Funkcje zbioru dla programu Word przy użyciu unigrams i Tri-Character-Grams.</span><span class="sxs-lookup"><span data-stu-id="51032-180">For text features: Bag-of-word features using unigrams and tri-character-grams.</span></span>

    <span data-ttu-id="51032-181">W przypadku funkcji kategorii: jednostronicowe kodowanie dla funkcji niskiej kardynalności i jednostronicowe kodowanie dla wysokich funkcji kategorii.</span><span class="sxs-lookup"><span data-stu-id="51032-181">For categorical features: One-hot encoding for low cardinality features, and one-hot-hash encoding for high cardinality categorical features.</span></span>

1. <span data-ttu-id="51032-182">Przekształcenia i kodowania</span><span class="sxs-lookup"><span data-stu-id="51032-182">Transformations and encodings</span></span>

    <span data-ttu-id="51032-183">Funkcje tekstowe z bardzo kilkoma unikatowymi wartościami przekształconymi na funkcje kategorii.</span><span class="sxs-lookup"><span data-stu-id="51032-183">Text features with very few unique values transformed into categorical features.</span></span> <span data-ttu-id="51032-184">W zależności od kardynalności funkcji kategorii należy wykonać jedno-gorąca lub jednostronicowe kodowanie skrótu.</span><span class="sxs-lookup"><span data-stu-id="51032-184">Depending on cardinality of categorical features, perform one-hot encoding or one-hot hash encoding.</span></span>

## <a name="exit-criteria"></a><span data-ttu-id="51032-185">Kryteria wyjścia</span><span class="sxs-lookup"><span data-stu-id="51032-185">Exit criteria</span></span>

<span data-ttu-id="51032-186">Zdefiniuj kryteria, aby ukończyć zadanie:</span><span class="sxs-lookup"><span data-stu-id="51032-186">Define the criteria to complete your task:</span></span>

1. <span data-ttu-id="51032-187">Zakończ po upływie długiego czasu `MaxExperimentTimeInSeconds` w ustawieniach eksperymentu możesz określić, jak długo w sekundach ma być nadal wykonywane zadanie.</span><span class="sxs-lookup"><span data-stu-id="51032-187">Exit after a length of time - Using `MaxExperimentTimeInSeconds` in your experiment settings you can define how long in seconds that an task should continue to run.</span></span>

1. <span data-ttu-id="51032-188">Wyjście z tokenu anulowania — można użyć tokenu anulowania, który umożliwia anulowanie zadania przed jego zaplanowaniem.</span><span class="sxs-lookup"><span data-stu-id="51032-188">Exit on a cancellation token -  You can use a cancellation token that lets you cancel the task before it is scheduled to finish.</span></span>

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a><span data-ttu-id="51032-189">Tworzenie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="51032-189">Create an experiment</span></span>

<span data-ttu-id="51032-190">Po skonfigurowaniu ustawień eksperymentu możesz przystąpić do tworzenia eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="51032-190">Once you have configured the experiment settings, you are ready to create the experiment.</span></span>

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a><span data-ttu-id="51032-191">Uruchamianie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="51032-191">Run the experiment</span></span>

<span data-ttu-id="51032-192">Uruchamianie eksperymentu wyzwala wstępne przetwarzanie danych, wybór algorytmu uczenia i dostrajanie parametrów.</span><span class="sxs-lookup"><span data-stu-id="51032-192">Running the experiment triggers data pre-processing, learning algorithm selection, and hyperparameter tuning.</span></span> <span data-ttu-id="51032-193">AutoML będzie nadal generować kombinacje algorytmów cechowania, uczenia i parametrów do momentu `MaxExperimentTimeInSeconds` osiągnięcia lub eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="51032-193">AutoML will continue to generate combinations of featurization, learning algorithms, and hyperparameters until the `MaxExperimentTimeInSeconds` is reached or the experiment is terminated.</span></span>

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

<span data-ttu-id="51032-194">Zapoznaj się z innymi przeciążeniami `Execute()` , jeśli chcesz przekazać dane sprawdzania poprawności, informacje o kolumnie wskazujące cel kolumny lub prefeaturizers.</span><span class="sxs-lookup"><span data-stu-id="51032-194">Explore other overloads for `Execute()` if you want to pass in validation data, column information indicating the column purpose, or prefeaturizers.</span></span>

## <a name="training-modes"></a><span data-ttu-id="51032-195">Tryby szkoleniowe</span><span class="sxs-lookup"><span data-stu-id="51032-195">Training modes</span></span>

### <a name="training-dataset"></a><span data-ttu-id="51032-196">Zestaw danych szkoleniowych</span><span class="sxs-lookup"><span data-stu-id="51032-196">Training dataset</span></span>

<span data-ttu-id="51032-197">AutoML zapewnia przeciążoną metodę wykonywania eksperymentu, która umożliwia dostarczanie danych szkoleniowych.</span><span class="sxs-lookup"><span data-stu-id="51032-197">AutoML provides an overloaded experiment execute method which allows you to provide training data.</span></span> <span data-ttu-id="51032-198">Wewnętrznie, zautomatyzowanej ML dzieli dane na pociąg-Validate Splits.</span><span class="sxs-lookup"><span data-stu-id="51032-198">Internally, automated ML divides the data into train-validate splits.</span></span>

```csharp
experiment.Execute(trainDataView);
```

### <a name="custom-validation-dataset"></a><span data-ttu-id="51032-199">Niestandardowy zestaw danych walidacji</span><span class="sxs-lookup"><span data-stu-id="51032-199">Custom validation dataset</span></span>

<span data-ttu-id="51032-200">Użyj niestandardowego zestawu danych walidacji, jeśli podział losowy nie jest akceptowalny, jak zwykle jest to przypadek z danymi szeregów czasowych.</span><span class="sxs-lookup"><span data-stu-id="51032-200">Use custom validation dataset if random split is not acceptable, as is usually the case with time series data.</span></span> <span data-ttu-id="51032-201">Możesz określić własny zestaw danych walidacji.</span><span class="sxs-lookup"><span data-stu-id="51032-201">You can specify your own validation dataset.</span></span> <span data-ttu-id="51032-202">Model zostanie oceniony względem określonego zestawu danych walidacji, a nie do co najmniej jednego losowo ustawionego typu danych.</span><span class="sxs-lookup"><span data-stu-id="51032-202">The model will be evaluated against the validation dataset specified instead of one or more random datasets.</span></span>

```csharp
experiment.Execute(trainDataView, validationDataView);
```

## <a name="explore-model-metrics"></a><span data-ttu-id="51032-203">Eksplorowanie metryk modelu</span><span class="sxs-lookup"><span data-stu-id="51032-203">Explore model metrics</span></span>

<span data-ttu-id="51032-204">Po każdej iteracji eksperymentu ML są przechowywane metryki dotyczące tego zadania.</span><span class="sxs-lookup"><span data-stu-id="51032-204">After each iteration of an ML experiment, metrics relating to that task are stored.</span></span>

<span data-ttu-id="51032-205">Można na przykład uzyskać dostęp do metryk walidacji z najlepszego przebiegu:</span><span class="sxs-lookup"><span data-stu-id="51032-205">For example, we can access validation metrics from the best run:</span></span>

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

<span data-ttu-id="51032-206">Poniżej znajdują się wszystkie dostępne metryki na ML zadania:</span><span class="sxs-lookup"><span data-stu-id="51032-206">The following are all the available metrics per ML task:</span></span>

* [<span data-ttu-id="51032-207">Metryki klasyfikacji binarnej</span><span class="sxs-lookup"><span data-stu-id="51032-207">Binary classification metrics</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [<span data-ttu-id="51032-208">Metryki klasyfikacji wieloklasowej</span><span class="sxs-lookup"><span data-stu-id="51032-208">Multiclass classification metrics</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [<span data-ttu-id="51032-209">Metryki rekomendacji & regresji</span><span class="sxs-lookup"><span data-stu-id="51032-209">Regression & recommendation metrics</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a><span data-ttu-id="51032-210">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="51032-210">See also</span></span>

<span data-ttu-id="51032-211">Aby uzyskać pełne przykłady kodu i więcej informacji, odwiedź repozytorium [dotnet/machinelearning-Samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) w witrynie GitHub.</span><span class="sxs-lookup"><span data-stu-id="51032-211">For full code samples and more visit the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub repository.</span></span>
