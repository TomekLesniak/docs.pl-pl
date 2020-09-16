---
title: Uczenie modelu uczenia maszynowego przy użyciu weryfikacji krzyżowej
description: Dowiedz się, jak tworzyć bardziej niezawodne modele uczenia maszynowego w programie ML.NET przy użyciu krzyżowego sprawdzania poprawności. Wzajemne sprawdzanie poprawności to technika szkoleń i oceny modelu, która dzieli dane na kilka partycji i pociąga za siebie wiele algorytmów na tych partycjach.
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to,title-hack-0625
ms.openlocfilehash: 02cec3d22588d8f10d36216422bc19faafffe94b
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679524"
---
# <a name="train-a-machine-learning-model-using-cross-validation"></a><span data-ttu-id="a5ce6-104">Uczenie modelu uczenia maszynowego przy użyciu weryfikacji krzyżowej</span><span class="sxs-lookup"><span data-stu-id="a5ce6-104">Train a machine learning model using cross validation</span></span>

<span data-ttu-id="a5ce6-105">Dowiedz się, jak korzystać z krzyżowego sprawdzania poprawności do uczenia bardziej niezawodnych modeli uczenia maszynowego w ML.NET.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-105">Learn how to use cross validation to train more robust machine learning models in ML.NET.</span></span>

<span data-ttu-id="a5ce6-106">Wzajemne sprawdzanie poprawności to technika szkoleń i oceny modelu, która dzieli dane na kilka partycji i pociąga za siebie wiele algorytmów na tych partycjach.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-106">Cross-validation is a training and model evaluation technique that splits the data into several partitions and trains multiple algorithms on these partitions.</span></span> <span data-ttu-id="a5ce6-107">Ta technika podnosi niezawodność modelu przez wyprowadzenie danych z procesu szkolenia.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-107">This technique improves the robustness of the model by holding out data from the training process.</span></span> <span data-ttu-id="a5ce6-108">Oprócz poprawy wydajności niewidocznych obserwacji w środowiskach z ograniczonymi danymi może być skutecznym narzędziem dla modeli szkoleniowych z mniejszym zestawem danych.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-108">In addition to improving performance on unseen observations, in data-constrained environments it can be an effective tool for training models with a smaller dataset.</span></span>

## <a name="the-data-and-data-model"></a><span data-ttu-id="a5ce6-109">Dane i model danych</span><span class="sxs-lookup"><span data-stu-id="a5ce6-109">The data and data model</span></span>

<span data-ttu-id="a5ce6-110">Dane z pliku o następującym formacie:</span><span class="sxs-lookup"><span data-stu-id="a5ce6-110">Given data from a file that has the following format:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
620.00, 148330.32, 140913.81, 136686.39, 146105.37
550.00, 557033.46, 529181.78, 513306.33, 548677.95
1127.00, 479320.99, 455354.94, 441694.30, 472131.18
1120.00, 47504.98, 45129.73, 43775.84, 46792.41
```

<span data-ttu-id="a5ce6-111">Dane można modelować według klasy, takiej jak `HousingData` i załadowanej do [`IDataView`](xref:Microsoft.ML.IDataView) .</span><span class="sxs-lookup"><span data-stu-id="a5ce6-111">The data can be modeled by a class like `HousingData` and loaded into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }

    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

## <a name="prepare-the-data"></a><span data-ttu-id="a5ce6-112">Przygotowywanie danych</span><span class="sxs-lookup"><span data-stu-id="a5ce6-112">Prepare the data</span></span>

<span data-ttu-id="a5ce6-113">Wstępnie przetwórz dane przed użyciem ich do kompilowania modelu uczenia maszynowego.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-113">Pre-process the data before using it to build the machine learning model.</span></span> <span data-ttu-id="a5ce6-114">W tym przykładzie `Size` `HistoricalPrices` kolumny i są łączone w jeden wektor funkcji, który jest wyprowadzany do nowej kolumny o nazwie `Features` przy użyciu [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A) metody.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-114">In this sample, the `Size` and `HistoricalPrices` columns are combined into a single feature vector,  which is output to a new column called `Features` using the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A) method.</span></span> <span data-ttu-id="a5ce6-115">Oprócz pobierania danych do formatu oczekiwanego przez algorytmy ML.NET, łączenie kolumn optymalizuje kolejne operacje w potoku przez zastosowanie operacji raz dla połączonej kolumny zamiast każdej oddzielnej kolumny.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-115">In addition to getting the data into the format expected by ML.NET algorithms, concatenating columns optimizes subsequent operations in the pipeline by applying the operation once for the concatenated column instead of each of the separate columns.</span></span>

<span data-ttu-id="a5ce6-116">Gdy kolumny są łączone w jeden wektor, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) są stosowane do `Features` kolumny do pobrania `Size` i `HistoricalPrices` w tym samym zakresie między 0-1.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-116">Once the columns are combined into a single vector, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) is applied to the `Features` column to get `Size` and `HistoricalPrices` in the same range between 0-1.</span></span>

```csharp
// Define data prep estimator
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// Transform data
IDataView transformedData = dataPrepTransformer.Transform(data);
```

## <a name="train-model-with-cross-validation"></a><span data-ttu-id="a5ce6-117">Uczenie modelu z krzyżowego sprawdzania poprawności</span><span class="sxs-lookup"><span data-stu-id="a5ce6-117">Train model with cross validation</span></span>

<span data-ttu-id="a5ce6-118">Gdy dane zostaną wstępnie przetworzone, czas na nauczenie modelu.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-118">Once the data has been pre-processed, it's time to train the model.</span></span> <span data-ttu-id="a5ce6-119">Najpierw wybierz algorytm najbardziej zbliżony do zadania uczenia maszynowego, które ma zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-119">First, select the algorithm that most closely aligns with the machine learning task to be performed.</span></span> <span data-ttu-id="a5ce6-120">Ponieważ przewidywana wartość jest wartością liczbową, to zadanie jest regresją.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-120">Because the predicted value is a numerically continuous value, the task is regression.</span></span> <span data-ttu-id="a5ce6-121">Jednym z algorytmów regresji implementowanych przez ML.NET jest [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) algorytm.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-121">One of the regression algorithms implemented by ML.NET is the [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) algorithm.</span></span> <span data-ttu-id="a5ce6-122">Aby przeprowadzić uczenie modelu z wykorzystaniem krzyżowego sprawdzania poprawności, użyj [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate%2A) metody.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-122">To train the model with cross-validation use the [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate%2A) method.</span></span>

> [!NOTE]
> <span data-ttu-id="a5ce6-123">Chociaż ten przykład używa modelu regresji liniowej, CrossValidate ma zastosowanie do wszystkich innych zadań uczenia maszynowego w ML.NET, z wyjątkiem wykrywania anomalii.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-123">Although this sample uses a linear regression model, CrossValidate is applicable to all other machine learning tasks in ML.NET except Anomaly Detection.</span></span>

```csharp
// Define StochasticDualCoordinateAscent algorithm estimator
IEstimator<ITransformer> sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Apply 5-fold cross validation
var cvResults = mlContext.Regression.CrossValidate(transformedData, sdcaEstimator, numberOfFolds: 5);
```

<span data-ttu-id="a5ce6-124">[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate%2A) wykonuje następujące operacje:</span><span class="sxs-lookup"><span data-stu-id="a5ce6-124">[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate%2A) performs the following operations:</span></span>

1. <span data-ttu-id="a5ce6-125">Dzieli dane na liczbę partycji równą wartości określonej w `numberOfFolds` parametrze.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-125">Partitions the data into a number of partitions equal to the value specified in the `numberOfFolds` parameter.</span></span> <span data-ttu-id="a5ce6-126">Wynikiem każdej partycji jest [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) obiekt.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-126">The result of each partition is a [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) object.</span></span>
1. <span data-ttu-id="a5ce6-127">Model jest przeszkolony na każdej partycji przy użyciu określonego algorytmu uczenia maszynowego szacowania w zestawie danych szkoleniowych.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-127">A model is trained on each of the partitions using the specified machine learning algorithm estimator on the training data set.</span></span>
1. <span data-ttu-id="a5ce6-128">Wydajność poszczególnych modeli jest oceniana przy użyciu [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) metody w zestawie danych testowych.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-128">Each model's performance is evaluated using the [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) method on the test data set.</span></span>
1. <span data-ttu-id="a5ce6-129">Model wraz z metrykami są zwracane dla każdego z modeli.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-129">The model along with its metrics are returned for each of the models.</span></span>

<span data-ttu-id="a5ce6-130">Wynik przechowywany w programie `cvResults` jest kolekcją [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) obiektów.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-130">The result stored in `cvResults` is a collection of [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) objects.</span></span> <span data-ttu-id="a5ce6-131">Ten obiekt obejmuje przeszkolony model, a także metryki, które są zarówno dostępne, jak [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) i [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics) właściwości.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-131">This object includes the trained model as well as metrics which are both accessible form the [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) and [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics) properties respectively.</span></span> <span data-ttu-id="a5ce6-132">W tym przykładzie `Model` Właściwość jest typu, [`ITransformer`](xref:Microsoft.ML.ITransformer) a `Metrics` Właściwość jest typu [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics) .</span><span class="sxs-lookup"><span data-stu-id="a5ce6-132">In this sample, the `Model` property is of type [`ITransformer`](xref:Microsoft.ML.ITransformer) and the `Metrics` property is of type [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics).</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="a5ce6-133">Ocena modelu</span><span class="sxs-lookup"><span data-stu-id="a5ce6-133">Evaluate the model</span></span>

<span data-ttu-id="a5ce6-134">Metryki dla różnych przeszkolonych modeli są dostępne za pomocą `Metrics` Właściwości indywidualnego [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) obiektu.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-134">Metrics for the different trained models can be accessed through the `Metrics` property of the individual [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) object.</span></span> <span data-ttu-id="a5ce6-135">W takim przypadku uzyskuje się dostęp do [metryki R-kwadrat](https://en.wikipedia.org/wiki/Coefficient_of_determination) i są one przechowywane w zmiennej `rSquared` .</span><span class="sxs-lookup"><span data-stu-id="a5ce6-135">In this case, the [R-Squared metric](https://en.wikipedia.org/wiki/Coefficient_of_determination) is accessed and stored in the variable `rSquared`.</span></span>

```csharp
IEnumerable<double> rSquared =
    cvResults
        .Select(fold => fold.Metrics.RSquared);
```

<span data-ttu-id="a5ce6-136">Jeśli sprawdzisz zawartość `rSquared` zmiennej, dane wyjściowe powinny mieć pięć wartości z zakresu od 0-1, gdzie najlepiej do 1.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-136">If you inspect the contents of the `rSquared` variable, the output should be five values ranging from 0-1 where closer to 1 means best.</span></span> <span data-ttu-id="a5ce6-137">Korzystając z metryk, takich jak R-Square, wybierz modele z największej do najgorszego wykonania.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-137">Using metrics like R-Squared, select the models from best to worst performing.</span></span> <span data-ttu-id="a5ce6-138">Następnie wybierz najwyższy model, aby dokonać prognoz lub wykonać dodatkowe operacje w programie.</span><span class="sxs-lookup"><span data-stu-id="a5ce6-138">Then, select the top model to make predictions or perform additional operations with.</span></span>

```csharp
// Select all models
ITransformer[] models =
    cvResults
        .OrderByDescending(fold => fold.Metrics.RSquared)
        .Select(fold => fold.Model)
        .ToArray();

// Get Top Model
ITransformer topModel = models[0];
```
