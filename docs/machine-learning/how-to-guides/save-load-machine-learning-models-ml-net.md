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
# <a name="save-and-load-trained-models"></a>Zapisz i Załaduj modele przeszkolone

Dowiedz się, jak zapisywać i ładować modele przeszkolone w aplikacji.

W całym procesie konstruowania modelu, model jest w pamięci i jest dostępny w całym cyklu życia aplikacji. Jeśli jednak aplikacja przestanie działać, jeśli model nie zostanie zapisany lokalnie lub zdalnie, nie jest już dostępny. Zazwyczaj modele są używane w pewnym momencie po szkoleniu w innych aplikacjach do wnioskowania lub ponownego uczenia się. W związku z tym ważne jest, aby zachować model. Zapisz i Załaduj modele, korzystając z kroków opisanych w kolejnych sekcjach tego dokumentu w przypadku używania potoków przygotowywania danych i szkoleń modeli, takich jak przedstawione poniżej. Chociaż ten przykład używa modelu regresji liniowej, ten sam proces ma zastosowanie do innych algorytmów ML.NET.

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

Ponieważ większość modeli i potoków przygotowywania danych dziedziczy z tego samego zestawu klas, sygnatury metody Zapisz i Załaduj dla tych składników są takie same. W zależności od przypadku użycia można połączyć proces przygotowywania danych i model do jednego, [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) który będzie wyprowadzał pojedynczy [`ITransformer`](xref:Microsoft.ML.ITransformer) lub oddzielny, w ten sposób tworząc oddzielne [`ITransformer`](xref:Microsoft.ML.ITransformer) dla każdej z nich.

## <a name="save-a-model-locally"></a>Lokalne zapisywanie modelu

Podczas zapisywania modelu potrzebne są dwa elementy:

1. [`ITransformer`](xref:Microsoft.ML.ITransformer)Modelu.
2. [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) [`ITransformer`](xref:Microsoft.ML.ITransformer) Oczekiwane dane wejściowe.

Po przekształceniu modelu Użyj metody, [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save%2A) Aby zapisać przeszkolony model do pliku o nazwie `model.zip` przy użyciu `DataViewSchema` danych wejściowych.

```csharp
// Save Trained Model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

## <a name="load-a-model-stored-locally"></a>Ładowanie modelu przechowywanego lokalnie

Modele przechowywane lokalnie można używać w innych procesach lub aplikacjach, takich jak `ASP.NET Core` i `Serverless Web Applications` . Zobacz [używanie ml.NET w interfejsie API sieci Web](./serve-model-web-api-ml-net.md) i [wdrażanie aplikacji sieci Web bezserwerowych ml.NET](./serve-model-serverless-azure-functions-ml-net.md) , aby dowiedzieć się więcej.

W oddzielnej aplikacji lub procesie Użyj [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A) metody wraz ze ścieżką pliku, aby uzyskać model przeszkolony do aplikacji.

```csharp
//Define DataViewSchema for data preparation pipeline and trained model
DataViewSchema modelSchema;

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```

## <a name="load-a-model-stored-remotely"></a>Załaduj zdalnie przechowywany model

Aby załadować potoki przygotowywania danych i modele przechowywane w lokalizacji zdalnej do aplikacji, należy użyć [`Stream`](xref:System.IO.Stream) zamiast niej ścieżki pliku w [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A) metodzie.

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

## <a name="working-with-separate-data-preparation-and-model-pipelines"></a>Praca z oddzielnymi potokami przygotowywania i tworzenia danych

> [!NOTE]
> Praca z oddzielnymi potokami przygotowywania i uczenia modeli jest opcjonalna. Rozdzielenie potoków ułatwia sprawdzenie poznaniych parametrów modelu. W przypadku prognoz można łatwiej zapisywać i ładować pojedynczy potok, który obejmuje operacje przygotowywania i szkolenia modelu danych.

Podczas pracy z oddzielnymi potokami i modelami przygotowywania danych jest stosowany ten sam proces jak pojedynczy potok; z wyjątkiem przypadków, w których teraz oba potoki muszą być zapisane i ładowane jednocześnie.

Podane oddzielne potoki przygotowywania i szkolenia modeli:

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

### <a name="save-data-preparation-pipeline-and-trained-model"></a>Zapisywanie potoku przygotowywania danych i modelu przeszkolonego

Aby zapisać zarówno potok przygotowania danych, jak i model przeszkolony, użyj następujących poleceń:

```csharp
// Save Data Prep transformer
mlContext.Model.Save(dataPrepTransformer, data.Schema, "data_preparation_pipeline.zip");

// Save Trained Model
mlContext.Model.Save(trainedModel, transformedData.Schema, "model.zip");
```

### <a name="load-data-preparation-pipeline-and-trained-model"></a>Załaduj potok przygotowywania danych i model szkolony

W oddzielnym procesie lub aplikacji Załaduj potok przygotowywania danych i model szkolony jednocześnie w następujący sposób:

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define data preparation and trained model schemas
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline and trained model
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip",out dataPrepPipelineSchema);
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```
