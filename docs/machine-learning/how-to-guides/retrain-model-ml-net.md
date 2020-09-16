---
title: Ponowne trenowanie modelu
description: Dowiedz się, jak ponownie nauczyć model w ML.NET
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 50f35e3511acc344339b1e150b47d7ce6de94254
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679563"
---
# <a name="re-train-a-model"></a><span data-ttu-id="15341-103">Ponowne trenowanie modelu</span><span class="sxs-lookup"><span data-stu-id="15341-103">Re-train a model</span></span>

<span data-ttu-id="15341-104">Dowiedz się, jak ponownie przeprowadzić uczenie modelu uczenia maszynowego w programie ML.NET.</span><span class="sxs-lookup"><span data-stu-id="15341-104">Learn how to retrain a machine learning model in ML.NET.</span></span>

<span data-ttu-id="15341-105">Na całym świecie dane zmieniają się w stałym tempie.</span><span class="sxs-lookup"><span data-stu-id="15341-105">The world and the data around it change at a constant pace.</span></span> <span data-ttu-id="15341-106">W związku z tym modele muszą ulec zmianie i zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="15341-106">As such, models need to change and update as well.</span></span> <span data-ttu-id="15341-107">ML.NET oferuje funkcje dla modeli do ponownego uczenia przy użyciu parametrów modelu, które są punktem wyjścia do ciągłego kompilowania na podstawie poprzedniego środowiska, zamiast rozpoczynać się za każdym razem.</span><span class="sxs-lookup"><span data-stu-id="15341-107">ML.NET provides functionality for re-training models using learned model parameters as a starting point to continually build on previous experience rather than starting from scratch every time.</span></span>

<span data-ttu-id="15341-108">Następujące algorytmy są ponownie pouczeni w ML.NET:</span><span class="sxs-lookup"><span data-stu-id="15341-108">The following algorithms are re-trainable in ML.NET:</span></span>

- [<span data-ttu-id="15341-109">AveragedPerceptronTrainer</span><span class="sxs-lookup"><span data-stu-id="15341-109">AveragedPerceptronTrainer</span></span>](xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer)
- [<span data-ttu-id="15341-110">FieldAwareFactorizationMachineTrainer</span><span class="sxs-lookup"><span data-stu-id="15341-110">FieldAwareFactorizationMachineTrainer</span></span>](xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer)
- [<span data-ttu-id="15341-111">LbfgsLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="15341-111">LbfgsLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer)
- [<span data-ttu-id="15341-112">LbfgsMaximumEntropyMulticlassTrainer</span><span class="sxs-lookup"><span data-stu-id="15341-112">LbfgsMaximumEntropyMulticlassTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer)
- [<span data-ttu-id="15341-113">LbfgsPoissonRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="15341-113">LbfgsPoissonRegressionTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer)
- [<span data-ttu-id="15341-114">LinearSvmTrainer</span><span class="sxs-lookup"><span data-stu-id="15341-114">LinearSvmTrainer</span></span>](xref:Microsoft.ML.Trainers.LinearSvmTrainer)
- [<span data-ttu-id="15341-115">OnlineGradientDescentTrainer</span><span class="sxs-lookup"><span data-stu-id="15341-115">OnlineGradientDescentTrainer</span></span>](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer)
- [<span data-ttu-id="15341-116">SgdCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="15341-116">SgdCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdCalibratedTrainer)
- [<span data-ttu-id="15341-117">SgdNonCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="15341-117">SgdNonCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdNonCalibratedTrainer)
- [<span data-ttu-id="15341-118">SymbolicSgdLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="15341-118">SymbolicSgdLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer)

## <a name="load-pre-trained-model"></a><span data-ttu-id="15341-119">Załaduj wstępnie szkolony model</span><span class="sxs-lookup"><span data-stu-id="15341-119">Load pre-trained model</span></span>

<span data-ttu-id="15341-120">Najpierw Załaduj wstępnie szkolony model do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="15341-120">First, load the pre-trained model into your application.</span></span> <span data-ttu-id="15341-121">Aby dowiedzieć się więcej na temat ładowania potoków szkoleń i modeli, zobacz [Zapisywanie i ładowanie nauczonego modelu](save-load-machine-learning-models-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="15341-121">To learn more about loading training pipelines and models, see [Save and load a trained model](save-load-machine-learning-models-ml-net.md).</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema of data prep pipeline and trained model
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip", out dataPrepPipelineSchema);

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("ogd_model.zip", out modelSchema);
```

## <a name="extract-pre-trained-model-parameters"></a><span data-ttu-id="15341-122">Wyodrębnij wstępnie przeszkolone parametry modelu</span><span class="sxs-lookup"><span data-stu-id="15341-122">Extract pre-trained model parameters</span></span>

<span data-ttu-id="15341-123">Po załadowaniu modelu Wyodrębnij uzyskane parametry modelu, uzyskując dostęp do [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase%601.Model%2A) właściwości wstępnie przeszkolonego modelu.</span><span class="sxs-lookup"><span data-stu-id="15341-123">Once the model is loaded, extract the learned model parameters by accessing the [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase%601.Model%2A) property of the pre-trained model.</span></span> <span data-ttu-id="15341-124">Model wstępnie szkolony został przeszkolony przy użyciu modelu regresji liniowej, [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) który tworzy [`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601) te dane wyjściowe [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) .</span><span class="sxs-lookup"><span data-stu-id="15341-124">The pre-trained model was trained using the linear regression model [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) which creates a [`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601) that outputs [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters).</span></span> <span data-ttu-id="15341-125">Te parametry modelu regresji liniowej zawierają rozmieszczoną wagę i wagi lub współczynniki modelu.</span><span class="sxs-lookup"><span data-stu-id="15341-125">These linear regression model parameters contain the learned bias and weights or coefficients of the model.</span></span> <span data-ttu-id="15341-126">Te wartości będą używane jako punkt wyjścia dla nowego modelu ponownie szkolony.</span><span class="sxs-lookup"><span data-stu-id="15341-126">These values will be used as a starting point for the new re-trained model.</span></span>

```csharp
// Extract trained model parameters
LinearRegressionModelParameters originalModelParameters =
    ((ISingleFeaturePredictionTransformer<object>)trainedModel).Model as LinearRegressionModelParameters;
```

## <a name="re-train-model"></a><span data-ttu-id="15341-127">Model ponownego uczenia</span><span class="sxs-lookup"><span data-stu-id="15341-127">Re-train model</span></span>

<span data-ttu-id="15341-128">Proces ponownego szkolenia modelu nie różni się od poziomu szkolenia modelu.</span><span class="sxs-lookup"><span data-stu-id="15341-128">The process for retraining a model is no different than that of training a model.</span></span> <span data-ttu-id="15341-129">Jedyną różnicą jest to, że [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer%602.Fit%2A) Metoda, oprócz danych, przyjmuje jako dane wejściowe pierwotne informacje o parametrach modelu, a także używa ich jako punktu wyjścia w procesie ponownego uczenia.</span><span class="sxs-lookup"><span data-stu-id="15341-129">The only difference is, the [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer%602.Fit%2A) method in addition to the data also takes as input the original learned model parameters and uses them as a starting point in the re-training process.</span></span>

```csharp
// New Data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};

//Load New Data
IDataView newData = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Preprocess Data
IDataView transformedNewData = dataPrepPipeline.Transform(newData);

// Retrain model
RegressionPredictionTransformer<LinearRegressionModelParameters> retrainedModel =
    mlContext.Regression.Trainers.OnlineGradientDescent()
        .Fit(transformedNewData, originalModelParameters);
```

## <a name="compare-model-parameters"></a><span data-ttu-id="15341-130">Porównaj parametry modelu</span><span class="sxs-lookup"><span data-stu-id="15341-130">Compare model parameters</span></span>

<span data-ttu-id="15341-131">Jak można sprawdzić, czy ponowne szkolenie rzeczywiście się zaszło?</span><span class="sxs-lookup"><span data-stu-id="15341-131">How do you know if re-training actually happened?</span></span> <span data-ttu-id="15341-132">Jednym ze sposobów jest porównanie, czy parametry modelu, który został przeszkolony, różnią się od modelu oryginalnego.</span><span class="sxs-lookup"><span data-stu-id="15341-132">One way would be to compare whether the re-trained model's parameters are different than those of the original model.</span></span> <span data-ttu-id="15341-133">Poniższy przykład kodu porównuje oryginalny z odszkolonymi wagami modelu i wyprowadza je do konsoli.</span><span class="sxs-lookup"><span data-stu-id="15341-133">The code sample below compares the original against the re-trained model weights and outputs them to the console.</span></span>

```csharp
// Extract Model Parameters of re-trained model
LinearRegressionModelParameters retrainedModelParameters = retrainedModel.Model as LinearRegressionModelParameters;

// Inspect Change in Weights
var weightDiffs =
    originalModelParameters.Weights.Zip(
        retrainedModelParameters.Weights, (original, retrained) => original - retrained).ToArray();

Console.WriteLine("Original | Retrained | Difference");
for(int i=0;i < weightDiffs.Count();i++)
{
    Console.WriteLine($"{originalModelParameters.Weights[i]} | {retrainedModelParameters.Weights[i]} | {weightDiffs[i]}");
}
```

<span data-ttu-id="15341-134">W poniższej tabeli pokazano, jak dane wyjściowe mogą wyglądać podobnie.</span><span class="sxs-lookup"><span data-stu-id="15341-134">The table below shows what the output might look like.</span></span>

|<span data-ttu-id="15341-135">Oryginał</span><span class="sxs-lookup"><span data-stu-id="15341-135">Original</span></span> | <span data-ttu-id="15341-136">Przeszkol ponownie</span><span class="sxs-lookup"><span data-stu-id="15341-136">Retrained</span></span> | <span data-ttu-id="15341-137">Różnica</span><span class="sxs-lookup"><span data-stu-id="15341-137">Difference</span></span> |
|---|---|---|
| <span data-ttu-id="15341-138">33039,86</span><span class="sxs-lookup"><span data-stu-id="15341-138">33039.86</span></span> | <span data-ttu-id="15341-139">56293,76</span><span class="sxs-lookup"><span data-stu-id="15341-139">56293.76</span></span> | <span data-ttu-id="15341-140">-23253,9</span><span class="sxs-lookup"><span data-stu-id="15341-140">-23253.9</span></span> |
| <span data-ttu-id="15341-141">29099,14</span><span class="sxs-lookup"><span data-stu-id="15341-141">29099.14</span></span> | <span data-ttu-id="15341-142">49586,03</span><span class="sxs-lookup"><span data-stu-id="15341-142">49586.03</span></span> | <span data-ttu-id="15341-143">-20486,89</span><span class="sxs-lookup"><span data-stu-id="15341-143">-20486.89</span></span> |
| <span data-ttu-id="15341-144">28938,38</span><span class="sxs-lookup"><span data-stu-id="15341-144">28938.38</span></span> | <span data-ttu-id="15341-145">48609,23</span><span class="sxs-lookup"><span data-stu-id="15341-145">48609.23</span></span> | <span data-ttu-id="15341-146">-19670,85</span><span class="sxs-lookup"><span data-stu-id="15341-146">-19670.85</span></span> |
| <span data-ttu-id="15341-147">30484,02</span><span class="sxs-lookup"><span data-stu-id="15341-147">30484.02</span></span> | <span data-ttu-id="15341-148">53745,43</span><span class="sxs-lookup"><span data-stu-id="15341-148">53745.43</span></span> | <span data-ttu-id="15341-149">-23261,41</span><span class="sxs-lookup"><span data-stu-id="15341-149">-23261.41</span></span> |
