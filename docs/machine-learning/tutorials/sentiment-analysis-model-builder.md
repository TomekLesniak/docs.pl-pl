---
title: 'Samouczek: analizowanie klasyfikacji tonacji-Binary'
description: W tym samouczku przedstawiono sposób tworzenia aplikacji Razor Pages, która klasyfikuje tonacji z komentarzy w witrynie sieci Web i podejmuje odpowiednie działania. Tonacji klasyfikator binarny używa konstruktora modelu w programie Visual Studio.
ms.date: 11/21/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc,mlnet-tooling
ms.openlocfilehash: 7761240055c90ae9c713b1c460e9e83316d256f9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/29/2020
ms.locfileid: "81278954"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a>Samouczek: analizowanie tonacji komentarzy witryny internetowej w aplikacji sieci Web przy użyciu konstruktora modelu ML.NET

Dowiedz się, jak analizować tonacji z komentarzy w czasie rzeczywistym w aplikacji sieci Web.

W tym samouczku pokazano, jak utworzyć aplikację Razor Pages ASP.NET Core, która klasyfikuje tonacji z komentarzy w witrynie sieci Web w czasie rzeczywistym.

Z tego samouczka dowiesz się, jak wykonywać następujące czynności:

> [!div class="checklist"]
>
> - Tworzenie aplikacji Razor Pages ASP.NET Core
> - Przygotuj i poznanie danych
> - Wybierz scenariusz
> - Ładowanie danych
> - Trenowanie modelu
> - Ocena modelu
> - Używanie modelu dla prognoz

> [!NOTE]
> Konstruktor modeli jest obecnie w wersji zapoznawczej.

Kod źródłowy dla tego samouczka można znaleźć w repozytorium [dotnet/machinelearning-Samples](https://github.com/dotnet/machinelearning-samples) .

## <a name="pre-requisites"></a>Wymagania wstępne

Listę wymagań wstępnych i instrukcji instalacji można znaleźć w [podręczniku instalacji konstruktora modeli](../how-to-guides/install-model-builder.md).

## <a name="create-a-razor-pages-application"></a>Tworzenie aplikacji Razor Pages

1. Utwórz **aplikację Razor Pages ASP.NET Core**.

    1. Otwórz program Visual Studio i wybierz pozycję **plik > nowy > projekt** na pasku menu.
    1. W oknie dialogowym Nowy projekt wybierz węzeł **Visual C#** , a następnie węzeł **sieci Web** .
    1. Następnie wybierz szablon projektu **aplikacji sieci Web ASP.NET Core** .
    1. W polu tekstowym **Nazwa** wpisz "SentimentRazor".
    1. Upewnij się, że w tym samym katalogu nie jest **zaznaczone pole wyboru** **Umieść rozwiązanie i projekt** (vs 2019) lub pozycję **Utwórz katalog dla rozwiązania** jest **zaznaczone** (vs 2017).
    1. Wybierz przycisk **OK**.
    1. W oknie Wybierz **aplikację sieci Web** , która wyświetla różne typy projektów ASP.NET Core, a następnie wybierz przycisk **OK** .

## <a name="prepare-and-understand-the-data"></a>Przygotuj i poznanie danych

Pobierz [zestaw danych detox Wikipedia](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv). Gdy zostanie otwarta strona sieci Web, kliknij prawym przyciskiem myszy na stronie, wybierz polecenie **Zapisz jako** i Zapisz plik w dowolnym miejscu na komputerze.

Każdy wiersz w zestawie danych *Wikipedia-detox-250-line-Data. tsv* reprezentuje inny przegląd, który został pozostawiony przez użytkownika w witrynie Wikipedia. Pierwsza kolumna reprezentuje tonacji tekstu (0 to nietoksyczne, 1 jest toksyczny), a druga kolumna reprezentuje komentarz, który został pozostawiony przez użytkownika. Kolumny są oddzielane znakami tabulacji. Dane wyglądają następująco:

| Opinia | SentimentText |
| :---: | :---: |
1 | = = Prosta = = informatyku, prosta to Carl Picture lub else.
1 | = = OK! = = BŁYSKAWICZNE PRZECHODZENIE DO VANDALIZE DZIKICH WITRYN TYPU WIKI, A NASTĘPNIE!!!
0 | Mam nadzieję, że to pomoże.

## <a name="choose-a-scenario"></a>Wybierz scenariusz

![Kreator konstruktora modelu w programie Visual Studio](./media/sentiment-analysis-model-builder/model-builder-screen.png)

Aby szkolić model, musisz wybrać z listy dostępnych scenariuszy uczenia maszynowego udostępnianych przez konstruktora modelu.

1. W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt *SentimentRazor* , a następnie wybierz pozycję **Dodaj**  >  **Machine Learning**.
1. Na potrzeby tego przykładu scenariusz jest tonacji analizy. W kroku *scenariusz* narzędzia model Builder wybierz scenariusz **Analiza tonacji** .

## <a name="load-the-data"></a>Ładowanie danych

Konstruktor modelu akceptuje dane z dwóch źródeł, bazy danych SQL Server lub lokalnego pliku w `csv` formacie lub `tsv` .

1. W kroku dane narzędzia model Builder wybierz pozycję **plik** z listy rozwijanej Źródło danych.
1. Wybierz przycisk obok pola tekstowego **Wybierz plik** i Użyj Eksploratora plików, aby przeglądać i wybrać plik *Wikipedia-detox-250-line-Data. tsv* .
1. Wybierz pozycję **tonacji** w **kolumnie do przewidywania (etykieta)** listy rozwijanej.
1. Pozostaw wartości domyślne dla listy rozwijanej **kolumny wejściowe (Features)** .
1. Wybierz łącze **uczenie** , aby przejść do następnego kroku w narzędziu model Builder.

## <a name="train-the-model"></a>Trenowanie modelu

Zadanie uczenia maszynowego używane do uczenia modelu analizy tonacji w tym samouczku jest klasyfikacją binarną. Podczas procesu uczenia modelowego, Konstruktor modelu pociąga za siebie różne modele przy użyciu różnych binarnych algorytmów klasyfikacji i ustawień, aby znaleźć najlepszy model dla zestawu danych.

Czas wymagany przez model do uczenia jest proporcjonalny do ilości danych. Konstruktor modelu automatycznie wybiera wartość domyślną dla **czasu do uczenia (w sekundach)** na podstawie rozmiaru źródła danych.

1. Chociaż Konstruktor modelu ustawia wartość **czasu do uczenia (sekundy)** do 10 sekund, zwiększ go do 30 sekund. Szkolenie przez dłuższy czas umożliwia konstruktorowi modelu Eksplorowanie większej liczby algorytmów i kombinacji parametrów podczas wyszukiwania najlepszego modelu.
1. Wybierz pozycję **Rozpocznij szkolenie**.

    W trakcie całego procesu szkolenia dane o postępie są wyświetlane w `Progress` sekcji kroku uczenie.

    - Stan przedstawia stan zakończenia procesu szkolenia.
    - Najlepsza dokładność przedstawia dokładność najlepszego modelu, który został znaleziony przez konstruktora modelu do tej pory. Większa dokładność oznacza, że model przewidywalno dokładniej na danych testowych.
    - Najlepszym algorytmem jest wyświetlana nazwa najlepszego wykonywania algorytmu, który został wykonany przez konstruktora modelu do tej pory.
    - Ostatni algorytm wyświetla nazwę algorytmu ostatnio używanego przez konstruktora modelu do uczenia modelu.

1. Po zakończeniu szkolenia wybierz łącze **Oceń** , aby przejść do następnego kroku.

## <a name="evaluate-the-model"></a>Ocena modelu

Wynikiem kroku szkolenia będzie jeden model, który ma najlepszą wydajność. W kroku szacowania narzędzia model Builder sekcja Output będzie zawierać algorytm używany przez optymalny model w najlepszym wpisie **modelu** oraz metryki o **najwyższej dokładności modelu**. Ponadto zostanie wyświetlona tabela podsumowująca zawierająca pięć najważniejszych modeli i ich metryki.

Jeśli Twoje metryki dokładności nie są zadowalające, niektóre łatwe sposoby podniesienia dokładności modelu polegają na zwiększeniu czasu na nauczenie modelu lub użyciu większej ilości danych. W przeciwnym razie wybierz łącze **kod** , aby przejść do ostatniego kroku w narzędziu model Builder.

## <a name="add-the-code-to-make-predictions"></a>Dodaj kod, aby tworzyć przewidywania

W wyniku procesu szkolenia zostaną utworzone dwa projekty.

### <a name="reference-the-trained-model"></a>Odwołuje się do przeszkolonego modelu

1. W kroku *Code* narzędzia model Builder wybierz pozycję **Dodaj projekty** , aby dodać automatycznie generowane projekty do rozwiązania.

    Następujące projekty powinny pojawić się w **Eksplorator rozwiązań**:

    - *SentimentRazorML. ConsoleApp*: Aplikacja konsolowa platformy .NET Core, która zawiera model szkoleń i kodu przewidywania.
    - *SentimentRazorML. model*: biblioteka klas .NET Standard zawierająca modele danych, które definiują schemat danych wejściowych i wyjściowych, a także zapisaną wersję najlepszego modelu podczas uczenia się.

    W tym samouczku używany jest tylko projekt *SentimentRazorML. model* , ponieważ przewidywania zostaną wykonane w aplikacji sieci Web *SentimentRazor* , a nie w konsoli programu. Chociaż *SentimentRazorML. ConsoleApp* nie będzie używany do oceniania, może służyć do ponownego uczenia modelu przy użyciu nowych danych w późniejszym czasie. W tym samouczku przeszkolenie zostało przeprowadzone poza zakresem.

### <a name="configure-the-predictionengine-pool"></a>Konfigurowanie puli PredictionEngine

Aby wykonać pojedyncze prognozowanie, należy utworzyć <xref:Microsoft.ML.PredictionEngine%602> . <xref:Microsoft.ML.PredictionEngine%602> nie jest bezpieczny wątkowo. Ponadto należy utworzyć wystąpienie go wszędzie tam, gdzie jest to potrzebne w aplikacji. Gdy aplikacja zostanie powiększona, ten proces może być niezarządzany. Aby zwiększyć wydajność i bezpieczeństwo wątków, należy użyć kombinacji iniekcji zależności i `PredictionEnginePool` usługi, która tworzy <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601> <xref:Microsoft.ML.PredictionEngine%602> obiekty do użycia w całej aplikacji.

1. Zainstaluj pakiet NuGet *Microsoft.Extensions.ml* :

    1. W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt i wybierz polecenie **Zarządzaj pakietami NuGet**.
    1. Wybierz pozycję "nuget.org" jako źródło pakietu.
    1. Wybierz kartę **Przeglądaj** i wyszukaj ciąg **Microsoft.Extensions.ml**.
    1. Wybierz pakiet z listy, a następnie wybierz przycisk **Instaluj** .
    1. Wybierz przycisk **OK** w oknie dialogowym **Podgląd zmian**
    1. Jeśli zgadzasz się z postanowieniami licencyjnymi dotyczącymi wymienionych pakietów, **Wybierz przycisk Akceptuję w oknie** dialogowym **akceptacji licencji** .

1. Otwórz plik *Startup.cs* w projekcie *SentimentRazor* .
1. Dodaj następujące instrukcje using, aby odwołać się do pakietu NuGet *Microsoft.Extensions.ml* i projektu *SentimentRazorML. model* :

    ```csharp
    using System.IO;
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

1. Utwórz zmienną globalną do przechowywania lokalizacji pliku z przeszkolonym modelem.

    ```csharp
    private readonly string _modelPath;
    ```

1. Plik modelu jest przechowywany w katalogu kompilacji obok plików zestawu aplikacji. Aby ułatwić dostęp, należy utworzyć metodę pomocnika wywołana `GetAbsolutePath` po `Configure` metodzie

    ```csharp
    public static string GetAbsolutePath(string relativePath)
    {
        FileInfo _dataRoot = new FileInfo(typeof(Program).Assembly.Location);
        string assemblyFolderPath = _dataRoot.Directory.FullName;

        string fullPath = Path.Combine(assemblyFolderPath, relativePath);
        return fullPath;
    }
    ```

1. Użyj `GetAbsolutePath` metody z `Startup` konstruktora klasy, aby ustawić `_modelPath` .

    ```csharp
    _modelPath = GetAbsolutePath("MLModel.zip");
    ```

1. Skonfiguruj `PredictionEnginePool` aplikację dla aplikacji w `ConfigureServices` metodzie:

    ```csharp
    services.AddPredictionEnginePool<ModelInput, ModelOutput>()
            .FromFile(_modelPath);
    ```

### <a name="create-sentiment-analysis-handler"></a>Utwórz procedurę obsługi analizy tonacji

Przewidywania zostaną wykonane wewnątrz strony głównej aplikacji. W związku z tym metoda, która pobiera dane wejściowe użytkownika i używa `PredictionEnginePool` do zwrócenia prognozy, musi zostać dodana.

1. Otwórz plik *index.cshtml.cs* znajdujący się w katalogu *Pages* i Dodaj następujące instrukcje using:

    ```csharp
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

    Aby można było użyć `PredictionEnginePool` skonfigurowanej klasy w `Startup` klasie, należy wstrzyknąć ją do konstruktora modelu, w którym ma być używany.

1. Dodaj zmienną, aby odwołać się do `PredictionEnginePool` wewnątrz `IndexModel` klasy.

    ```csharp
    private readonly PredictionEnginePool<ModelInput, ModelOutput> _predictionEnginePool;
    ```

1. Utwórz konstruktora w `IndexModel` klasie i wstrzyknąć `PredictionEnginePool` do niego usługę.

    ```csharp
    public IndexModel(PredictionEnginePool<ModelInput, ModelOutput> predictionEnginePool)
    {
        _predictionEnginePool = predictionEnginePool;
    }
    ```

1. Utwórz procedurę obsługi metody, która używa `PredictionEnginePool` do tworzenia prognoz z danych wejściowych użytkownika otrzymanych ze strony sieci Web.

    1. Poniżej `OnGet` metody Utwórz nową metodę o nazwie `OnGetAnalyzeSentiment`

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. Wewnątrz `OnGetAnalyzeSentiment` metody Zwróć *neutralną* tonacji, jeśli dane wejściowe użytkownika są puste lub mają wartość null.

        ```csharp
        if (String.IsNullOrEmpty(text)) return Content("Neutral");
        ```

    1. Podaje prawidłowe dane wejściowe, Utwórz nowe wystąpienie `ModelInput` .

        ```csharp
        var input = new ModelInput { SentimentText = text };
        ```

    1. Użyj `PredictionEnginePool` do przewidywania tonacji.

        ```csharp
        var prediction = _predictionEnginePool.Predict(input);
        ```

    1. Przekonwertuj przewidywaną `bool` wartość na toksyczną lub nietoksyczną przy użyciu poniższego kodu.

        ```csharp
        var sentiment = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";
        ```

    1. Na koniec Zwróć tonacji z powrotem do strony sieci Web.

        ```csharp
        return Content(sentiment);
        ```

### <a name="configure-the-web-page"></a>Skonfiguruj stronę sieci Web

Wyniki zwrócone przez `OnGetAnalyzeSentiment` program będą dynamicznie wyświetlane na `Index` stronie sieci Web.

1. Otwórz plik *index. cshtml* w katalogu *stron* i Zastąp jego zawartość następującym kodem:

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. Następnie Dodaj kod stylów CSS do końca strony *site. css* w katalogu *wwwroot\css* :

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. Następnie Dodaj kod, aby wysłać dane wejściowe ze strony sieci Web do `OnGetAnalyzeSentiment` procedury obsługi.

    1. W pliku *site.js* znajdującym się w katalogu *wwwroot\js* Utwórz funkcję o nazwie, `getSentiment` Aby wykonać żądanie Get http z danymi wejściowymi użytkownika do `OnGetAnalyzeSentiment` programu obsługi.

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. Poniżej można dodać kolejną funkcję o nazwie, `updateMarker` aby dynamicznie aktualizować pozycję znacznika na stronie sieci Web w miarę przewidywania tonacji.

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. Utwórz funkcję programu obsługi zdarzeń o nazwie `updateSentiment` , aby pobrać dane wejściowe od użytkownika, wysłać je do `OnGetAnalyzeSentiment` funkcji przy użyciu `getSentiment` funkcji i zaktualizować znacznik przy użyciu `updateMarker` funkcji.

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. Na koniec Zarejestruj program obsługi zdarzeń i powiąż go `textarea` z elementem z `id=Message` atrybutem.

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a>Uruchamianie aplikacji

Teraz, gdy aplikacja jest skonfigurowana, uruchom aplikację, która powinna być uruchamiana w przeglądarce.

Po uruchomieniu aplikacji, wprowadź *wartość Konstruktor modeli jest chłodna!* w obszarze tekstu. Wyświetlona tonacji nie powinna być *toksyczna*.

![Uruchamianie okna z przewidywanym oknem tonacji](./media/sentiment-analysis-model-builder/web-app.png)

Jeśli musisz odwołać się do projektów wygenerowanych przez konstruktora modeli w późniejszym czasie w innym rozwiązaniu, możesz je znaleźć w `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` katalogu.

## <a name="next-steps"></a>Następne kroki

W niniejszym samouczku zawarto informacje na temat wykonywania następujących czynności:
> [!div class="checklist"]
>
> - Tworzenie aplikacji Razor Pages ASP.NET Core
> - Przygotuj i poznanie danych
> - Wybierz scenariusz
> - Ładowanie danych
> - Trenowanie modelu
> - Ocena modelu
> - Używanie modelu dla prognoz

### <a name="additional-resources"></a>Dodatkowe zasoby

Aby dowiedzieć się więcej na temat tematów wymienionych w tym samouczku, odwiedź następujące zasoby:

- [Scenariusze konstruktora modelu](../automate-training-with-model-builder.md#scenario)
- [Klasyfikacja binarna](../resources/glossary.md#binary-classification)
- [Metryki binarnego modelu klasyfikacji](../resources/metrics.md#evaluation-metrics-for-binary-classification)
