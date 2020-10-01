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
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a>Wdrażanie modelu w ASP.NET Core Web API

Dowiedz się, jak obsłużyć wstępnie szkolony model uczenia maszynowego ML.NET w sieci Web przy użyciu ASP.NET Core internetowego interfejsu API. Obsługa modelu przez internetowy interfejs API umożliwia prognozowanie za pośrednictwem standardowych metod HTTP.

## <a name="prerequisites"></a>Wymagania wstępne

- [Program Visual studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) lub nowszy albo program visual Studio 2017 w wersji 15,6 lub nowszej z zainstalowanym obciążeniem "Programowanie dla wielu platform" platformy .NET Core.
- Narzędzia.
- Model wstępnie szkolony. Użyj [samouczka analiza tonacji ml.NET](../tutorials/sentiment-analysis.md) , aby skompilować własny model lub pobrać ten [wstępnie szkolony model uczenia maszynowego analizy tonacji](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)

## <a name="create-aspnet-core-web-api-project"></a>Tworzenie projektu interfejsu API sieci Web ASP.NET Core

1. Otwórz program Visual Studio 2017. Wybierz pozycję **plik > nowy > projekt** na pasku menu. W oknie dialogowym Nowy projekt wybierz węzeł **Visual C#** , a następnie węzeł **sieci Web** . Następnie wybierz szablon projektu **aplikacji sieci Web ASP.NET Core** . W polu tekstowym **Nazwa** wpisz "SentimentAnalysisWebAPI", a następnie wybierz przycisk **OK** .

1. W oknie, w którym są wyświetlane różne typy projektów ASP.NET Core, wybierz pozycję **interfejs API** i wybierz przycisk **OK** .

1. Utwórz katalog o nazwie *MLModels* w projekcie, aby zapisać wstępnie utworzone pliki modelu uczenia maszynowego:

    W Eksplorator rozwiązań kliknij prawym przyciskiem myszy projekt i wybierz polecenie Dodaj > nowy folder. Wpisz "MLModels" i naciśnij klawisz ENTER.

1. Zainstaluj **pakiet NuGet Microsoft.ml**:

    W Eksplorator rozwiązań kliknij prawym przyciskiem myszy projekt i wybierz polecenie **Zarządzaj pakietami NuGet**. Wybierz pozycję "nuget.org" jako źródło pakietu, wybierz kartę Przeglądaj, Wyszukaj pozycję **Microsoft.ml**, wybierz ten pakiet z listy, a następnie wybierz przycisk Instaluj. Wybierz przycisk **OK** w oknie dialogowym **Podgląd zmian** , a następnie **Wybierz przycisk** Akceptuję w oknie dialogowym akceptacji licencji, jeśli zgadzasz się z postanowieniami licencyjnymi dotyczącymi wymienionych pakietów.

1. Zainstaluj **pakiet Nuget Microsoft.Extensions.ml**:

    W Eksplorator rozwiązań kliknij prawym przyciskiem myszy projekt i wybierz polecenie **Zarządzaj pakietami NuGet**. Wybierz pozycję "nuget.org" jako źródło pakietu, wybierz kartę Przeglądaj, Wyszukaj pozycję **Microsoft.Extensions.ml**, wybierz ten pakiet z listy, a następnie wybierz przycisk Instaluj. Wybierz przycisk **OK** w oknie dialogowym **Podgląd zmian** , a następnie **Wybierz przycisk** Akceptuję w oknie dialogowym akceptacji licencji, jeśli zgadzasz się z postanowieniami licencyjnymi dotyczącymi wymienionych pakietów.

### <a name="add-model-to-aspnet-core-web-api-project"></a>Dodaj model do projektu interfejsu API sieci Web ASP.NET Core

1. Skopiuj wstępnie utworzony model do katalogu *MLModels*
1. W Eksplorator rozwiązań kliknij prawym przyciskiem myszy plik zip modelu i wybierz polecenie Właściwości. W obszarze Zaawansowane Zmień wartość opcji Kopiuj do katalogu wyjściowego na Kopiuj, jeśli nowszy.

## <a name="create-data-models"></a>Tworzenie modeli danych

Należy utworzyć klasy dla danych wejściowych i prognoz. Dodaj nową klasę do projektu:

1. Utwórz katalog o nazwie *Datamodels* w projekcie, aby zapisać modele danych:

    W Eksplorator rozwiązań kliknij prawym przyciskiem myszy projekt i wybierz polecenie Dodaj > nowy folder. Wpisz "datamodels" i naciśnij klawisz **Enter**.

2. W Eksplorator rozwiązań kliknij prawym przyciskiem myszy katalog *Datamodels* , a następnie wybierz pozycję Dodaj > nowy element.
3. W oknie dialogowym **Dodaj nowy element** wybierz pozycję **Klasa** i zmień wartość pola **Nazwa** na *SentimentData.cs*. Następnie wybierz przycisk **Dodaj** . Plik *SentimentData.cs* zostanie otwarty w edytorze kodu. Dodaj następującą instrukcję using na początku *SentimentData.cs*:

    ```csharp
    using Microsoft.ML.Data;
    ```

    Usuń istniejącą definicję klasy i Dodaj następujący kod do pliku **SentimentData.cs** :

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

4. W Eksplorator rozwiązań kliknij prawym przyciskiem myszy katalog *Datamodels* , a następnie wybierz pozycję **Dodaj > nowy element**.
5. W oknie dialogowym **Dodaj nowy element** wybierz pozycję **Klasa** i zmień wartość pola **Nazwa** na *SentimentPrediction.cs*. Następnie wybierz przycisk Dodaj. Plik *SentimentPrediction.cs* zostanie otwarty w edytorze kodu. Dodaj następującą instrukcję using na początku *SentimentPrediction.cs*:

    ```csharp
    using Microsoft.ML.Data;
    ```

    Usuń istniejącą definicję klasy i Dodaj następujący kod do pliku *SentimentPrediction.cs* :

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    `SentimentPrediction` dziedziczy z `SentimentData` . Dzięki temu można łatwiej zobaczyć oryginalne dane we `SentimentText` właściwości wraz z danymi wyjściowymi generowanymi przez model.

## <a name="register-predictionenginepool-for-use-in-the-application"></a>Zarejestruj PredictionEnginePool do użycia w aplikacji

Aby wykonać pojedyncze prognozowanie, należy utworzyć [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) . [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) nie jest bezpieczny wątkowo. Ponadto należy utworzyć wystąpienie go wszędzie tam, gdzie jest to potrzebne w aplikacji. Gdy aplikacja zostanie powiększona, ten proces może być niezarządzany. Aby zwiększyć wydajność i bezpieczeństwo wątków, należy użyć kombinacji iniekcji zależności i `PredictionEnginePool` usługi, która tworzy [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) obiekty do użycia w całej aplikacji.

Poniższy link zawiera więcej informacji, jeśli chcesz dowiedzieć się więcej o [iniekcji zależności w ASP.NET Core](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).

1. Otwórz klasę *Startup.cs* i Dodaj następującą instrukcję using na początku pliku:

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. Dodaj następujący kod do metody *ConfigureServices* :

    ```csharp
    services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
        .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
    ```

Na wysokim poziomie ten kod inicjuje automatycznie obiekty i usługi do późniejszego użycia, gdy żądanie jest wymagane przez aplikację, a nie trzeba jej wykonać ręcznie.

Modele uczenia maszynowego nie są statyczne. Po udostępnieniu nowych danych szkoleniowych model zostanie ponownie przeszkolony i wdrożony ponownie. Jednym ze sposobów uzyskania najnowszej wersji modelu do aplikacji jest ponowne wdrożenie całej aplikacji. Powoduje to jednak wprowadzenie przestojów aplikacji. `PredictionEnginePool`Usługa udostępnia mechanizm umożliwiający ponowne załadowanie zaktualizowanego modelu bez przełączania aplikacji.

Ustaw `watchForChanges` parametr na `true` , a następnie uruchomi polecenie, `PredictionEnginePool` [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) które nasłuchuje w systemie plików powiadomienia o zmianie, i zgłasza zdarzenia w przypadku zmiany pliku. Zostanie wyświetlony komunikat z prośbą o `PredictionEnginePool` automatyczne załadowanie modelu.

Model jest identyfikowany przez `modelName` parametr, aby można było ponownie załadować więcej niż jeden model dla aplikacji po zmianie.

> [!TIP]
> Alternatywnie możesz użyć `FromUri` metody podczas pracy z modelami przechowywanymi zdalnie. Zamiast oglądać zdarzenia ze zmienionymi plikami, `FromUri` sonduje lokalizację zdalną pod kątem zmian. Interwał sondowania jest wartością domyślną 5 minut. Interwał sondowania można zwiększyć lub zmniejszyć w zależności od wymagań aplikacji. W poniższym przykładzie kodu `PredictionEnginePool` sonduje model przechowywany w określonym identyfikatorze URI co minutę.
>
>```csharp
>services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="create-predict-controller"></a>Utwórz kontroler predykcyjny

Aby przetwarzać przychodzące żądania HTTP, Utwórz kontroler.

1. W Eksplorator rozwiązań kliknij prawym przyciskiem myszy katalog *controllers* , a następnie wybierz pozycję **Dodaj kontroler >**.
1. W oknie dialogowym **Dodaj nowy element** wybierz pozycję **kontroler interfejsu API puste** i wybierz pozycję **Dodaj**.
1. W oknie monitu Zmień **nazwę kontrolera** na *PredictController.cs*. Następnie wybierz przycisk Dodaj. Plik *PredictController.cs* zostanie otwarty w edytorze kodu. Dodaj następującą instrukcję using na początku *PredictController.cs*:

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    Usuń istniejącą definicję klasy i Dodaj następujący kod do pliku *PredictController.cs* :

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

Ten kod przypisuje `PredictionEnginePool` przez przekazanie go do konstruktora kontrolera, który uzyskuje się za pośrednictwem iniekcji zależności. Następnie `Predict` `Post` Metoda kontrolera używa `PredictionEnginePool` do wykonywania prognoz przy użyciu `SentimentAnalysisModel` zarejestrowanej w `Startup` klasie i zwraca wyniki z powrotem do użytkownika, jeśli to się powiedzie.

## <a name="test-web-api-locally"></a>Testowanie lokalnego interfejsu API sieci Web

Po skonfigurowaniu wszystkiego czas na przetestowanie aplikacji.

1. Uruchom aplikację.
1. Otwórz program PowerShell i wprowadź następujący kod, gdzie PORT jest portem, na którym nasłuchuje aplikacja.

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    Jeśli to się powiedzie, dane wyjściowe powinny wyglądać podobnie do poniższego tekstu:

    ```powershell
    Negative
    ```

Gratulacje! Udało Ci się pomyślnie obsłużyć model, aby przekonywać prognoz przez Internet przy użyciu ASP.NET Core internetowego interfejsu API.

## <a name="next-steps"></a>Następne kroki

- [Wdróż na platformie Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs#deploy-the-app-to-azure)
