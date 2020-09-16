---
title: Zapisz i Załaduj modele przeszkolone
description: Dowiedz się, jak zapisywać i ładować przeszkolone modele
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 681a35956a8959e2f1cbb5a7023e0ef29b67097e
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679537"
---
# <a name="save-and-load-trained-models"></a><span data-ttu-id="77a26-103">Zapisz i Załaduj modele przeszkolone</span><span class="sxs-lookup"><span data-stu-id="77a26-103">Save and load trained models</span></span>

<span data-ttu-id="77a26-104">Dowiedz się, jak zapisywać i ładować modele przeszkolone w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="77a26-104">Learn how to save and load trained models in your application.</span></span>

<span data-ttu-id="77a26-105">W całym procesie konstruowania modelu, model jest w pamięci i jest dostępny w całym cyklu życia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="77a26-105">Throughout the model building process, a model lives in memory and is accessible throughout the application's lifecycle.</span></span> <span data-ttu-id="77a26-106">Jeśli jednak aplikacja przestanie działać, jeśli model nie zostanie zapisany lokalnie lub zdalnie, nie jest już dostępny.</span><span class="sxs-lookup"><span data-stu-id="77a26-106">However, once the application stops running, if the model is not saved somewhere locally or remotely, it's no longer accessible.</span></span> <span data-ttu-id="77a26-107">Zazwyczaj modele są używane w pewnym momencie po szkoleniu w innych aplikacjach do wnioskowania lub ponownego uczenia się.</span><span class="sxs-lookup"><span data-stu-id="77a26-107">Typically models are used at some point after training in other applications either for inference or re-training.</span></span> <span data-ttu-id="77a26-108">W związku z tym ważne jest, aby zachować model.</span><span class="sxs-lookup"><span data-stu-id="77a26-108">Therefore, it's important to store the model.</span></span> <span data-ttu-id="77a26-109">Zapisz i Załaduj modele, korzystając z kroków opisanych w kolejnych sekcjach tego dokumentu w przypadku używania potoków przygotowywania danych i szkoleń modeli, takich jak przedstawione poniżej.</span><span class="sxs-lookup"><span data-stu-id="77a26-109">Save and load models using the steps described in subsequent sections of this document when using data preparation and model training pipelines like the one detailed below.</span></span> <span data-ttu-id="77a26-110">Chociaż ten przykład używa modelu regresji liniowej, ten sam proces ma zastosowanie do innych algorytmów ML.NET.</span><span class="sxs-lookup"><span data-stu-id="77a26-110">Although this sample uses a linear regression model, the same process applies to other ML.NET algorithms.</span></span>

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f, 125000f, 122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    }
};

// Create MLContext
MLContext mlContext = new MLContext();

// Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Define data preparation estimator
EstimatorChain<RegressionPredictionTransformer<LinearRegressionModelParameters>> pipelineEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"))
        .Append(mlContext.Regression.Trainers.Sdca());

// Train model
ITransformer trainedModel = pipelineEstimator.Fit(data);

// Save model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

<span data-ttu-id="77a26-111">Ponieważ większość modeli i potoków przygotowywania danych dziedziczy z tego samego zestawu klas, sygnatury metody Zapisz i Załaduj dla tych składników są takie same.</span><span class="sxs-lookup"><span data-stu-id="77a26-111">Because most models and data preparation pipelines inherit from the same set of classes, the save and load method signatures for these components is the same.</span></span> <span data-ttu-id="77a26-112">W zależności od przypadku użycia można połączyć proces przygotowywania danych i model do jednego, [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) który będzie wyprowadzał pojedynczy [`ITransformer`](xref:Microsoft.ML.ITransformer) lub oddzielny, w ten sposób tworząc oddzielne [`ITransformer`](xref:Microsoft.ML.ITransformer) dla każdej z nich.</span><span class="sxs-lookup"><span data-stu-id="77a26-112">Depending on your use case, you can either combine the data preparation pipeline and model into a single [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) which would output a single [`ITransformer`](xref:Microsoft.ML.ITransformer) or separate them thus creating a separate [`ITransformer`](xref:Microsoft.ML.ITransformer) for each.</span></span>

## <a name="save-a-model-locally"></a><span data-ttu-id="77a26-113">Lokalne zapisywanie modelu</span><span class="sxs-lookup"><span data-stu-id="77a26-113">Save a model locally</span></span>

<span data-ttu-id="77a26-114">Podczas zapisywania modelu potrzebne są dwa elementy:</span><span class="sxs-lookup"><span data-stu-id="77a26-114">When saving a model you need two things:</span></span>

1. <span data-ttu-id="77a26-115">[`ITransformer`](xref:Microsoft.ML.ITransformer)Modelu.</span><span class="sxs-lookup"><span data-stu-id="77a26-115">The [`ITransformer`](xref:Microsoft.ML.ITransformer) of the model.</span></span>
2. <span data-ttu-id="77a26-116">[`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) [`ITransformer`](xref:Microsoft.ML.ITransformer) Oczekiwane dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="77a26-116">The [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) of the [`ITransformer`](xref:Microsoft.ML.ITransformer)'s expected input.</span></span>

<span data-ttu-id="77a26-117">Po przekształceniu modelu Użyj metody, [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save%2A) Aby zapisać przeszkolony model do pliku o nazwie `model.zip` przy użyciu `DataViewSchema` danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="77a26-117">After training the model, use the [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save%2A) method to save the trained model to a file called `model.zip` using the `DataViewSchema` of the input data.</span></span>

```csharp
// Save Trained Model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

## <a name="load-a-model-stored-locally"></a><span data-ttu-id="77a26-118">Ładowanie modelu przechowywanego lokalnie</span><span class="sxs-lookup"><span data-stu-id="77a26-118">Load a model stored locally</span></span>

<span data-ttu-id="77a26-119">Modele przechowywane lokalnie można używać w innych procesach lub aplikacjach, takich jak `ASP.NET Core` i `Serverless Web Applications` .</span><span class="sxs-lookup"><span data-stu-id="77a26-119">Models stored locally can be used in other processes or applications like `ASP.NET Core` and `Serverless Web Applications`.</span></span> <span data-ttu-id="77a26-120">Zobacz [używanie ml.NET w interfejsie API sieci Web](./serve-model-web-api-ml-net.md) i [wdrażanie aplikacji sieci Web bezserwerowych ml.NET](./serve-model-serverless-azure-functions-ml-net.md) , aby dowiedzieć się więcej.</span><span class="sxs-lookup"><span data-stu-id="77a26-120">See [Use ML.NET in Web API](./serve-model-web-api-ml-net.md) and [Deploy ML.NET Serverless Web App](./serve-model-serverless-azure-functions-ml-net.md) how-to articles to learn more.</span></span>

<span data-ttu-id="77a26-121">W oddzielnej aplikacji lub procesie Użyj [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A) metody wraz ze ścieżką pliku, aby uzyskać model przeszkolony do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="77a26-121">In a separate application or process, use the [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A) method along with the file path to get the trained model into your application.</span></span>

```csharp
//Define DataViewSchema for data preparation pipeline and trained model
DataViewSchema modelSchema;

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```

## <a name="load-a-model-stored-remotely"></a><span data-ttu-id="77a26-122">Załaduj zdalnie przechowywany model</span><span class="sxs-lookup"><span data-stu-id="77a26-122">Load a model stored remotely</span></span>

<span data-ttu-id="77a26-123">Aby załadować potoki przygotowywania danych i modele przechowywane w lokalizacji zdalnej do aplikacji, należy użyć [`Stream`](xref:System.IO.Stream) zamiast niej ścieżki pliku w [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A) metodzie.</span><span class="sxs-lookup"><span data-stu-id="77a26-123">To load data preparation pipelines and models stored in a remote location into your application, use a [`Stream`](xref:System.IO.Stream) instead of a file path in the [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A) method.</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema and ITransformers
DataViewSchema modelSchema;
ITransformer trainedModel;

// Load data prep pipeline and trained model
using (HttpClient client = new HttpClient())
{
    Stream modelFile = await client.GetStreamAsync("<YOUR-REMOTE-FILE-LOCATION>");

    trainedModel = mlContext.Model.Load(modelFile, out modelSchema);
}
```

## <a name="working-with-separate-data-preparation-and-model-pipelines"></a><span data-ttu-id="77a26-124">Praca z oddzielnymi potokami przygotowywania i tworzenia danych</span><span class="sxs-lookup"><span data-stu-id="77a26-124">Working with separate data preparation and model pipelines</span></span>

> [!NOTE]
> <span data-ttu-id="77a26-125">Praca z oddzielnymi potokami przygotowywania i uczenia modeli jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="77a26-125">Working with separate data preparation and model training pipelines is optional.</span></span> <span data-ttu-id="77a26-126">Rozdzielenie potoków ułatwia sprawdzenie poznaniych parametrów modelu.</span><span class="sxs-lookup"><span data-stu-id="77a26-126">Separation of pipelines makes it easier to inspect the learned model parameters.</span></span> <span data-ttu-id="77a26-127">W przypadku prognoz można łatwiej zapisywać i ładować pojedynczy potok, który obejmuje operacje przygotowywania i szkolenia modelu danych.</span><span class="sxs-lookup"><span data-stu-id="77a26-127">For predictions, it's easier to save and load a single pipeline that includes the data preparation and model training operations.</span></span>

<span data-ttu-id="77a26-128">Podczas pracy z oddzielnymi potokami i modelami przygotowywania danych jest stosowany ten sam proces jak pojedynczy potok; z wyjątkiem przypadków, w których teraz oba potoki muszą być zapisane i ładowane jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="77a26-128">When working with separate data preparation pipelines and models, the same process as single pipelines applies; except now both pipelines need to be saved and loaded simultaneously.</span></span>

<span data-ttu-id="77a26-129">Podane oddzielne potoki przygotowywania i szkolenia modeli:</span><span class="sxs-lookup"><span data-stu-id="77a26-129">Given separate data preparation and model training pipelines:</span></span>

```csharp
// Define data preparation estimator
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data preparation transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Pre-process data using data prep operations
IDataView transformedData = dataPrepTransformer.Transform(data);

// Train regression model
RegressionPredictionTransformer<LinearRegressionModelParameters> trainedModel = sdcaEstimator.Fit(transformedData);
```

### <a name="save-data-preparation-pipeline-and-trained-model"></a><span data-ttu-id="77a26-130">Zapisywanie potoku przygotowywania danych i modelu przeszkolonego</span><span class="sxs-lookup"><span data-stu-id="77a26-130">Save data preparation pipeline and trained model</span></span>

<span data-ttu-id="77a26-131">Aby zapisać zarówno potok przygotowania danych, jak i model przeszkolony, użyj następujących poleceń:</span><span class="sxs-lookup"><span data-stu-id="77a26-131">To save both the data preparation pipeline and trained model, use the following commands:</span></span>

```csharp
// Save Data Prep transformer
mlContext.Model.Save(dataPrepTransformer, data.Schema, "data_preparation_pipeline.zip");

// Save Trained Model
mlContext.Model.Save(trainedModel, transformedData.Schema, "model.zip");
```

### <a name="load-data-preparation-pipeline-and-trained-model"></a><span data-ttu-id="77a26-132">Załaduj potok przygotowywania danych i model szkolony</span><span class="sxs-lookup"><span data-stu-id="77a26-132">Load data preparation pipeline and trained model</span></span>

<span data-ttu-id="77a26-133">W oddzielnym procesie lub aplikacji Załaduj potok przygotowywania danych i model szkolony jednocześnie w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="77a26-133">In a separate process or application, load the data preparation pipeline and trained model simultaneously as follows:</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define data preparation and trained model schemas
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline and trained model
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip",out dataPrepPipelineSchema);
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```
