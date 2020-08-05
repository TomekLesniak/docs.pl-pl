---
title: 'Samouczek: analizowanie komentarzy witryny sieci Web — klasyfikacja binarna'
description: W tym samouczku przedstawiono sposób tworzenia aplikacji konsolowej .NET Core, która klasyfikuje tonacji z komentarzy w witrynie sieci Web i podejmuje odpowiednie działania. Tonacji klasyfikator binarny używa języka C# w programie Visual Studio.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: da972d793570a8dd6b906762640bd6bfe5531a5b
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557167"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="c1442-104">Samouczek: analizowanie tonacji komentarzy w witrynie sieci Web za pomocą klasyfikacji binarnej w ML.NET</span><span class="sxs-lookup"><span data-stu-id="c1442-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="c1442-105">W tym samouczku przedstawiono sposób tworzenia aplikacji konsolowej .NET Core, która klasyfikuje tonacji z komentarzy w witrynie sieci Web i podejmuje odpowiednie działania.</span><span class="sxs-lookup"><span data-stu-id="c1442-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="c1442-106">Tonacji klasyfikator binarny używa języka C# w programie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="c1442-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="c1442-107">Ten samouczek zawiera informacje na temat wykonywania następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="c1442-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="c1442-108">Tworzenie aplikacji konsolowej</span><span class="sxs-lookup"><span data-stu-id="c1442-108">Create a console application</span></span>
> - <span data-ttu-id="c1442-109">Przygotowywanie danych</span><span class="sxs-lookup"><span data-stu-id="c1442-109">Prepare data</span></span>
> - <span data-ttu-id="c1442-110">Ładowanie danych</span><span class="sxs-lookup"><span data-stu-id="c1442-110">Load the data</span></span>
> - <span data-ttu-id="c1442-111">Kompilowanie i uczenie modelu</span><span class="sxs-lookup"><span data-stu-id="c1442-111">Build and train the model</span></span>
> - <span data-ttu-id="c1442-112">Ocena modelu</span><span class="sxs-lookup"><span data-stu-id="c1442-112">Evaluate the model</span></span>
> - <span data-ttu-id="c1442-113">Tworzenie prognoz przy użyciu modelu</span><span class="sxs-lookup"><span data-stu-id="c1442-113">Use the model to make a prediction</span></span>
> - <span data-ttu-id="c1442-114">Zobacz wyniki</span><span class="sxs-lookup"><span data-stu-id="c1442-114">See the results</span></span>

<span data-ttu-id="c1442-115">Kod źródłowy dla tego samouczka można znaleźć w repozytorium [dotnet/Samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) .</span><span class="sxs-lookup"><span data-stu-id="c1442-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c1442-116">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="c1442-116">Prerequisites</span></span>

- <span data-ttu-id="c1442-117">[Program Visual Studio 2017 w wersji 15,6 lub nowszej](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) z zainstalowanym obciążeniem "Programowanie dla wielu platform" platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="c1442-117">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed</span></span>

- <span data-ttu-id="c1442-118">[UCI tonacji z etykietą zestawu danych](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (plik zip)</span><span class="sxs-lookup"><span data-stu-id="c1442-118">[UCI Sentiment Labeled Sentences dataset](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="c1442-119">Tworzenie aplikacji konsolowej</span><span class="sxs-lookup"><span data-stu-id="c1442-119">Create a console application</span></span>

1. <span data-ttu-id="c1442-120">Utwórz **aplikację konsolową .NET Core** o nazwie "SentimentAnalysis".</span><span class="sxs-lookup"><span data-stu-id="c1442-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="c1442-121">Utwórz katalog o nazwie *dane* w projekcie, aby zapisać pliki zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="c1442-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="c1442-122">Zainstaluj **pakiet NuGet Microsoft.ml**:</span><span class="sxs-lookup"><span data-stu-id="c1442-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="c1442-123">W Eksplorator rozwiązań kliknij prawym przyciskiem myszy projekt i wybierz polecenie **Zarządzaj pakietami NuGet**.</span><span class="sxs-lookup"><span data-stu-id="c1442-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="c1442-124">Wybierz pozycję "nuget.org" jako źródło pakietu, a następnie wybierz kartę **Przeglądaj** . wyszukaj pozycję **Microsoft.ml**, wybierz pakiet, a następnie wybierz przycisk **Instaluj** .</span><span class="sxs-lookup"><span data-stu-id="c1442-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="c1442-125">Kontynuuj instalację, zgadzając się z postanowieniami licencyjnymi dotyczącymi wybranego pakietu.</span><span class="sxs-lookup"><span data-stu-id="c1442-125">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="c1442-126">Przygotowywanie danych</span><span class="sxs-lookup"><span data-stu-id="c1442-126">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="c1442-127">Zestawy danych dla tego samouczka pochodzą z grupy "from do poszczególnych etykiet przy użyciu funkcji głębokiej", Kotzias et.</span><span class="sxs-lookup"><span data-stu-id="c1442-127">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="c1442-128">Al,.</span><span class="sxs-lookup"><span data-stu-id="c1442-128">al,.</span></span> <span data-ttu-id="c1442-129">KDD 2015 i hostowana w repozytorium Machine Learning/Dua, D. i Karra Taniskidou, E. (2017).</span><span class="sxs-lookup"><span data-stu-id="c1442-129">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="c1442-130">/Na Machine Learning repozytorium [ http://archive.ics.uci.edu/ml ].</span><span class="sxs-lookup"><span data-stu-id="c1442-130">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="c1442-131">Irvine, CA: University of Kalifornii, szkolna informacja i nauka komputera.</span><span class="sxs-lookup"><span data-stu-id="c1442-131">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="c1442-132">Pobierz [UCI tonacji oznaczone zdaniami w pliku zip](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)i rozpakuj.</span><span class="sxs-lookup"><span data-stu-id="c1442-132">Download [UCI Sentiment Labeled Sentences dataset ZIP file](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="c1442-133">Skopiuj `yelp_labelled.txt` plik do utworzonego katalogu *danych* .</span><span class="sxs-lookup"><span data-stu-id="c1442-133">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="c1442-134">W Eksplorator rozwiązań kliknij prawym przyciskiem myszy `yelp_labeled.txt` plik i wybierz polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="c1442-134">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="c1442-135">W obszarze **Zaawansowane**Zmień wartość opcji **Kopiuj do katalogu wyjściowego** na Kopiuj, **jeśli nowszy**.</span><span class="sxs-lookup"><span data-stu-id="c1442-135">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="c1442-136">Tworzenie klas i Definiowanie ścieżek</span><span class="sxs-lookup"><span data-stu-id="c1442-136">Create classes and define paths</span></span>

1. <span data-ttu-id="c1442-137">Dodaj następujące dodatkowe `using` instrukcje na początku pliku *program.cs* :</span><span class="sxs-lookup"><span data-stu-id="c1442-137">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](./snippets/sentiment-analysis/csharp/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="c1442-138">Dodaj następujący kod do wiersza bezpośrednio powyżej `Main` metody, aby utworzyć pole do przechowywania niedawno pobranej ścieżki pliku zestawu danych:</span><span class="sxs-lookup"><span data-stu-id="c1442-138">Add the following code to the line right above the `Main` method, to create a field to hold the recently downloaded dataset file path:</span></span>

    [!code-csharp[Declare global variables](./snippets/sentiment-analysis/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. <span data-ttu-id="c1442-139">Następnie utwórz klasy dla danych wejściowych i prognoz.</span><span class="sxs-lookup"><span data-stu-id="c1442-139">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="c1442-140">Dodaj nową klasę do projektu:</span><span class="sxs-lookup"><span data-stu-id="c1442-140">Add a new class to your project:</span></span>

    - <span data-ttu-id="c1442-141">W **Eksplorator rozwiązań**kliknij prawym przyciskiem myszy projekt, a następnie wybierz polecenie **Dodaj**  >  **nowy element**.</span><span class="sxs-lookup"><span data-stu-id="c1442-141">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="c1442-142">W oknie dialogowym **Dodaj nowy element** wybierz pozycję **Klasa** i zmień wartość pola **Nazwa** na *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="c1442-142">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="c1442-143">Następnie wybierz przycisk **Dodaj** .</span><span class="sxs-lookup"><span data-stu-id="c1442-143">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="c1442-144">Plik *SentimentData.cs* zostanie otwarty w edytorze kodu.</span><span class="sxs-lookup"><span data-stu-id="c1442-144">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="c1442-145">Dodaj następującą `using` instrukcję na początku *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="c1442-145">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](./snippets/sentiment-analysis/csharp/SentimentData.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="c1442-146">Usuń istniejącą definicję klasy i Dodaj następujący kod, który ma dwie klasy `SentimentData` i `SentimentPrediction` , do pliku *SentimentData.cs* :</span><span class="sxs-lookup"><span data-stu-id="c1442-146">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](./snippets/sentiment-analysis/csharp/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="c1442-147">Jak dane zostały przygotowane</span><span class="sxs-lookup"><span data-stu-id="c1442-147">How the data was prepared</span></span>

<span data-ttu-id="c1442-148">Wejściowa Klasa DataSet, `SentimentData` , ma `string` dla komentarzy użytkownika ( `SentimentText` ) i `bool` ( `Sentiment` ) wartość 1 (pozytywna) lub 0 (ujemna) dla tonacji.</span><span class="sxs-lookup"><span data-stu-id="c1442-148">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="c1442-149">Oba pola mają dołączone atrybuty [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) , które opisują kolejność plików danych każdego pola.</span><span class="sxs-lookup"><span data-stu-id="c1442-149">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="c1442-150">Ponadto `Sentiment` Właściwość ma atrybut [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) , aby wyznaczyć go jako `Label` pole.</span><span class="sxs-lookup"><span data-stu-id="c1442-150">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="c1442-151">Następujący przykładowy plik nie ma wiersza nagłówka i wygląda następująco:</span><span class="sxs-lookup"><span data-stu-id="c1442-151">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="c1442-152">SentimentText</span><span class="sxs-lookup"><span data-stu-id="c1442-152">SentimentText</span></span>                         |<span data-ttu-id="c1442-153">Tonacji (etykieta)</span><span class="sxs-lookup"><span data-stu-id="c1442-153">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="c1442-154">Waitress był nieco wolny w usłudze.</span><span class="sxs-lookup"><span data-stu-id="c1442-154">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="c1442-155">0</span><span class="sxs-lookup"><span data-stu-id="c1442-155">0</span></span>     |
|<span data-ttu-id="c1442-156">Crust nie jest dobry.</span><span class="sxs-lookup"><span data-stu-id="c1442-156">Crust is not good.</span></span>                    |    <span data-ttu-id="c1442-157">0</span><span class="sxs-lookup"><span data-stu-id="c1442-157">0</span></span>     |
|<span data-ttu-id="c1442-158">Wow... Uwielbiane to miejsce.</span><span class="sxs-lookup"><span data-stu-id="c1442-158">Wow... Loved this place.</span></span>              |    <span data-ttu-id="c1442-159">1</span><span class="sxs-lookup"><span data-stu-id="c1442-159">1</span></span>     |
|<span data-ttu-id="c1442-160">Usługa była bardzo monitem.</span><span class="sxs-lookup"><span data-stu-id="c1442-160">Service was very prompt.</span></span>              |    <span data-ttu-id="c1442-161">1</span><span class="sxs-lookup"><span data-stu-id="c1442-161">1</span></span>     |

<span data-ttu-id="c1442-162">`SentimentPrediction`jest klasą przewidywania używaną po przekształceniu modelu.</span><span class="sxs-lookup"><span data-stu-id="c1442-162">`SentimentPrediction` is the prediction class used after model training.</span></span> <span data-ttu-id="c1442-163">Dziedziczy po `SentimentData` , tak aby dane wejściowe `SentimentText` mogły być wyświetlane wraz z przewidywaniam danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="c1442-163">It inherits from `SentimentData` so that the input `SentimentText` can be displayed along with the output prediction.</span></span> <span data-ttu-id="c1442-164">`Prediction`Wartość logiczna jest wartością przewidywalną przez model, gdy jest dostarczany z nowymi danymi wejściowymi `SentimentText` .</span><span class="sxs-lookup"><span data-stu-id="c1442-164">The `Prediction` boolean is the value that the model predicts when supplied with new input `SentimentText`.</span></span>

<span data-ttu-id="c1442-165">Klasa Output `SentimentPrediction` zawiera dwie inne właściwości obliczone przez model: `Score` — nieprzetworzony wynik obliczony przez model i `Probability` -wynik uzyskany do prawdopodobieństwa, że tekst ma dodatnie tonacji.</span><span class="sxs-lookup"><span data-stu-id="c1442-165">The output class `SentimentPrediction` contains two other properties calculated by the model: `Score` - the raw score calculated by the model, and `Probability` - the score calibrated to the likelihood of the text having positive sentiment.</span></span>

<span data-ttu-id="c1442-166">W tym samouczku najważniejszym właściwość jest `Prediction` .</span><span class="sxs-lookup"><span data-stu-id="c1442-166">For this tutorial, the most important property is `Prediction`.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="c1442-167">Ładowanie danych</span><span class="sxs-lookup"><span data-stu-id="c1442-167">Load the data</span></span>

<span data-ttu-id="c1442-168">Dane w ML.NET są reprezentowane jako [Klasa IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="c1442-168">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="c1442-169">`IDataView`to elastyczny i wydajny sposób opisywania danych tabelarycznych (liczbowych i tekstowych).</span><span class="sxs-lookup"><span data-stu-id="c1442-169">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="c1442-170">Dane można ładować z pliku tekstowego lub w czasie rzeczywistym (na przykład bazy danych SQL lub plików dziennika) do `IDataView` obiektu.</span><span class="sxs-lookup"><span data-stu-id="c1442-170">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="c1442-171">[Klasa MLContext](xref:Microsoft.ML.MLContext) jest punktem początkowym dla wszystkich operacji ml.NET.</span><span class="sxs-lookup"><span data-stu-id="c1442-171">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="c1442-172">Inicjowanie `mlContext` tworzy nowe środowisko ml.NET, które może być współużytkowane przez obiekty przepływu pracy tworzenia modelu.</span><span class="sxs-lookup"><span data-stu-id="c1442-172">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="c1442-173">Jest to podobne, pojęciowo do `DBContext` w Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="c1442-173">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="c1442-174">Przygotujesz aplikację, a następnie załadujesz dane:</span><span class="sxs-lookup"><span data-stu-id="c1442-174">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="c1442-175">Zastąp `Console.WriteLine("Hello World!")` wiersz w `Main` metodzie poniższym kodem, aby zadeklarować i zainicjować zmienną mlContext:</span><span class="sxs-lookup"><span data-stu-id="c1442-175">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](./snippets/sentiment-analysis/csharp/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="c1442-176">Dodaj następujący kod jako następny wiersz kodu w `Main()` metodzie:</span><span class="sxs-lookup"><span data-stu-id="c1442-176">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](./snippets/sentiment-analysis/csharp/Program.cs#CallLoadData)]

3. <span data-ttu-id="c1442-177">Utwórz `LoadData()` metodę, tuż po `Main()` metodzie, przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="c1442-177">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="c1442-178">`LoadData()`Metoda wykonuje następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="c1442-178">The `LoadData()` method executes the following tasks:</span></span>

    - <span data-ttu-id="c1442-179">Ładuje dane.</span><span class="sxs-lookup"><span data-stu-id="c1442-179">Loads the data.</span></span>
    - <span data-ttu-id="c1442-180">Dzieli załadowany zestaw danych na pociąg i testowe zestawy danych.</span><span class="sxs-lookup"><span data-stu-id="c1442-180">Splits the loaded dataset into train and test datasets.</span></span>
    - <span data-ttu-id="c1442-181">Zwraca zestawienie pociągów i testów zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="c1442-181">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="c1442-182">Dodaj następujący kod jako pierwszy wiersz `LoadData()` metody:</span><span class="sxs-lookup"><span data-stu-id="c1442-182">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](./snippets/sentiment-analysis/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="c1442-183">Metoda [LoadFromTextFile ()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) definiuje schemat danych i odczytuje w pliku.</span><span class="sxs-lookup"><span data-stu-id="c1442-183">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) method defines the data schema and reads in the file.</span></span> <span data-ttu-id="c1442-184">Przyjmuje zmienne ścieżki danych i zwraca `IDataView` .</span><span class="sxs-lookup"><span data-stu-id="c1442-184">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="c1442-185">Podziel zestaw danych na potrzeby szkolenia i testowania modelu</span><span class="sxs-lookup"><span data-stu-id="c1442-185">Split the dataset for model training and testing</span></span>

<span data-ttu-id="c1442-186">Podczas przygotowywania modelu należy użyć części zestawu danych, aby szkolić i części zestawu danych w celu przetestowania dokładności modelu.</span><span class="sxs-lookup"><span data-stu-id="c1442-186">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="c1442-187">Aby podzielić dane załadowane do wymaganych zestawów danych, Dodaj następujący kod jako następny wiersz w `LoadData()` metodzie:</span><span class="sxs-lookup"><span data-stu-id="c1442-187">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](./snippets/sentiment-analysis/csharp/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="c1442-188">Poprzedni kod używa metody [TrainTestSplit ()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) , aby podzielić załadowany zestaw danych na pociąg i test zestawy danych i zwrócić je w <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData> klasie.</span><span class="sxs-lookup"><span data-stu-id="c1442-188">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData> class.</span></span> <span data-ttu-id="c1442-189">Określ wartość procentową zestawu testów dla danych z `testFraction` parametrem.</span><span class="sxs-lookup"><span data-stu-id="c1442-189">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="c1442-190">Wartość domyślna to 10%, w tym przypadku do obliczenia większej ilości danych służy 20%.</span><span class="sxs-lookup"><span data-stu-id="c1442-190">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="c1442-191">Zwróć na `splitDataView` końcu `LoadData()` metody:</span><span class="sxs-lookup"><span data-stu-id="c1442-191">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](./snippets/sentiment-analysis/csharp/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="c1442-192">Kompilowanie i uczenie modelu</span><span class="sxs-lookup"><span data-stu-id="c1442-192">Build and train the model</span></span>

1. <span data-ttu-id="c1442-193">Dodaj następujące wywołanie do `BuildAndTrainModel` metody jako następny wiersz kodu w `Main()` metodzie:</span><span class="sxs-lookup"><span data-stu-id="c1442-193">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](./snippets/sentiment-analysis/csharp/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="c1442-194">`BuildAndTrainModel()`Metoda wykonuje następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="c1442-194">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    - <span data-ttu-id="c1442-195">Wyodrębnia i przekształca dane.</span><span class="sxs-lookup"><span data-stu-id="c1442-195">Extracts and transforms the data.</span></span>
    - <span data-ttu-id="c1442-196">Pociąga za siebie model.</span><span class="sxs-lookup"><span data-stu-id="c1442-196">Trains the model.</span></span>
    - <span data-ttu-id="c1442-197">Przewidywania tonacji na podstawie danych testowych.</span><span class="sxs-lookup"><span data-stu-id="c1442-197">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="c1442-198">Zwraca model.</span><span class="sxs-lookup"><span data-stu-id="c1442-198">Returns the model.</span></span>

2. <span data-ttu-id="c1442-199">Utwórz `BuildAndTrainModel()` metodę, tuż po `Main()` metodzie, przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="c1442-199">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="c1442-200">Wyodrębnij i Przekształć dane</span><span class="sxs-lookup"><span data-stu-id="c1442-200">Extract and transform the data</span></span>

1. <span data-ttu-id="c1442-201">Wywołaj `FeaturizeText` jako następny wiersz kodu:</span><span class="sxs-lookup"><span data-stu-id="c1442-201">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](./snippets/sentiment-analysis/csharp/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="c1442-202">`FeaturizeText()`Metoda w poprzednim kodzie konwertuje kolumnę tekstową ( `SentimentText` ) na kolumnę typu wartości liczbowej `Features` używanej przez algorytm uczenia maszynowego i dodaje ją jako nową kolumnę zestawu danych:</span><span class="sxs-lookup"><span data-stu-id="c1442-202">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="c1442-203">SentimentText</span><span class="sxs-lookup"><span data-stu-id="c1442-203">SentimentText</span></span>                         |<span data-ttu-id="c1442-204">Opinia</span><span class="sxs-lookup"><span data-stu-id="c1442-204">Sentiment</span></span> |<span data-ttu-id="c1442-205">Funkcje</span><span class="sxs-lookup"><span data-stu-id="c1442-205">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="c1442-206">Waitress był nieco wolny w usłudze.</span><span class="sxs-lookup"><span data-stu-id="c1442-206">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="c1442-207">0</span><span class="sxs-lookup"><span data-stu-id="c1442-207">0</span></span>     |<span data-ttu-id="c1442-208">[0,76, 0,65, 0,44,...]</span><span class="sxs-lookup"><span data-stu-id="c1442-208">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="c1442-209">Crust nie jest dobry.</span><span class="sxs-lookup"><span data-stu-id="c1442-209">Crust is not good.</span></span>                    |    <span data-ttu-id="c1442-210">0</span><span class="sxs-lookup"><span data-stu-id="c1442-210">0</span></span>     |<span data-ttu-id="c1442-211">[0,98, 0,43, 0,54,...]</span><span class="sxs-lookup"><span data-stu-id="c1442-211">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="c1442-212">Wow... Uwielbiane to miejsce.</span><span class="sxs-lookup"><span data-stu-id="c1442-212">Wow... Loved this place.</span></span>              |    <span data-ttu-id="c1442-213">1</span><span class="sxs-lookup"><span data-stu-id="c1442-213">1</span></span>     |<span data-ttu-id="c1442-214">[0,35, 0,73, 0,46,...]</span><span class="sxs-lookup"><span data-stu-id="c1442-214">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="c1442-215">Usługa była bardzo monitem.</span><span class="sxs-lookup"><span data-stu-id="c1442-215">Service was very prompt.</span></span>              |    <span data-ttu-id="c1442-216">1</span><span class="sxs-lookup"><span data-stu-id="c1442-216">1</span></span>     |<span data-ttu-id="c1442-217">[0,39, 0, 0,75,...]</span><span class="sxs-lookup"><span data-stu-id="c1442-217">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="c1442-218">Dodawanie algorytmu uczenia</span><span class="sxs-lookup"><span data-stu-id="c1442-218">Add a learning algorithm</span></span>

<span data-ttu-id="c1442-219">Ta aplikacja używa algorytmu klasyfikacji, który klasyfikuje elementy lub wiersze danych.</span><span class="sxs-lookup"><span data-stu-id="c1442-219">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="c1442-220">Aplikacja klasyfikuje Komentarze witryny sieci Web jako wartość dodatnią lub ujemną, więc Użyj zadania klasyfikacji binarnej.</span><span class="sxs-lookup"><span data-stu-id="c1442-220">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="c1442-221">Dołącz zadanie uczenia maszynowego do definicji transformacji danych, dodając następujący kod jako następny wiersz kodu w `BuildAndTrainModel()` :</span><span class="sxs-lookup"><span data-stu-id="c1442-221">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](./snippets/sentiment-analysis/csharp/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="c1442-222">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) jest algorytmem szkoleniowym klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="c1442-222">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="c1442-223">Ta wartość jest dołączana do `estimator` i akceptuje featurized `SentimentText` ( `Features` ) i `Label` Parametry wejściowe, aby poznać dane historyczne.</span><span class="sxs-lookup"><span data-stu-id="c1442-223">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="c1442-224">Szkolenie modelu</span><span class="sxs-lookup"><span data-stu-id="c1442-224">Train the model</span></span>

<span data-ttu-id="c1442-225">Dopasuj model do `splitTrainSet` danych i zwróć przeszkolony model, dodając następujący kod jako następny wiersz kodu w `BuildAndTrainModel()` metodzie:</span><span class="sxs-lookup"><span data-stu-id="c1442-225">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](./snippets/sentiment-analysis/csharp/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="c1442-226">Metoda [dopasowywania ()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) pociąga za siebie model poprzez transformowanie zestawu danych i zastosowanie szkolenia.</span><span class="sxs-lookup"><span data-stu-id="c1442-226">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="c1442-227">Zwróć model przeszkolony do użycia na potrzeby oceny</span><span class="sxs-lookup"><span data-stu-id="c1442-227">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="c1442-228">Zwróć model na końcu `BuildAndTrainModel()` metody:</span><span class="sxs-lookup"><span data-stu-id="c1442-228">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](./snippets/sentiment-analysis/csharp/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="c1442-229">Ocena modelu</span><span class="sxs-lookup"><span data-stu-id="c1442-229">Evaluate the model</span></span>

<span data-ttu-id="c1442-230">Po przeszkoleniu modelu Użyj danych testowych do sprawdzenia wydajności modelu.</span><span class="sxs-lookup"><span data-stu-id="c1442-230">After your model is trained, use your test data to validate the model's performance.</span></span>

1. <span data-ttu-id="c1442-231">Utwórz `Evaluate()` metodę, tuż po `BuildAndTrainModel()` , przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="c1442-231">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="c1442-232">`Evaluate()`Metoda wykonuje następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="c1442-232">The `Evaluate()` method executes the following tasks:</span></span>

    - <span data-ttu-id="c1442-233">Ładuje zestaw danych testowych.</span><span class="sxs-lookup"><span data-stu-id="c1442-233">Loads the test dataset.</span></span>
    - <span data-ttu-id="c1442-234">Tworzy ewaluatora BinaryClassification.</span><span class="sxs-lookup"><span data-stu-id="c1442-234">Creates the BinaryClassification evaluator.</span></span>
    - <span data-ttu-id="c1442-235">Oblicza model i tworzy metryki.</span><span class="sxs-lookup"><span data-stu-id="c1442-235">Evaluates the model and creates metrics.</span></span>
    - <span data-ttu-id="c1442-236">Wyświetla metryki.</span><span class="sxs-lookup"><span data-stu-id="c1442-236">Displays the metrics.</span></span>

2. <span data-ttu-id="c1442-237">Dodaj wywołanie do nowej metody z `Main()` metody, bezpośrednio pod `BuildAndTrainModel()` wywołaniem metody, przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="c1442-237">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](./snippets/sentiment-analysis/csharp/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="c1442-238">Przekształć `splitTestSet` dane, dodając następujący kod do `Evaluate()` :</span><span class="sxs-lookup"><span data-stu-id="c1442-238">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](./snippets/sentiment-analysis/csharp/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="c1442-239">Poprzedni kod używa metody [Transform ()](xref:Microsoft.ML.ITransformer.Transform%2A) do przeprowadzania prognoz dla wielu podanych danych wejściowych dla testu zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="c1442-239">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="c1442-240">Oceń model poprzez dodanie następujących elementów jako następny wiersz kodu w `Evaluate()` metodzie:</span><span class="sxs-lookup"><span data-stu-id="c1442-240">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](./snippets/sentiment-analysis/csharp/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="c1442-241">Gdy posiadasz zestaw predykcyjny ( `predictions` ), Metoda [oceny ()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) ocenia model, który porównuje wartości przewidywane z wartością rzeczywistą `Labels` w testowanym zestawie danych i zwraca obiekt [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) , w jaki działa model.</span><span class="sxs-lookup"><span data-stu-id="c1442-241">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="c1442-242">Wyświetlanie metryk na potrzeby walidacji modelu</span><span class="sxs-lookup"><span data-stu-id="c1442-242">Displaying the metrics for model validation</span></span>

<span data-ttu-id="c1442-243">Użyj następującego kodu, aby wyświetlić metryki:</span><span class="sxs-lookup"><span data-stu-id="c1442-243">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](./snippets/sentiment-analysis/csharp/Program.cs#DisplayMetrics "Display selected metrics")]

- <span data-ttu-id="c1442-244">`Accuracy`Metryka pobiera dokładność modelu, który jest proporcją prawidłowych prognoz w zestawie testów.</span><span class="sxs-lookup"><span data-stu-id="c1442-244">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

- <span data-ttu-id="c1442-245">`AreaUnderRocCurve`Metryka wskazuje, jak pewność, że model prawidłowo klasyfikuje klasy dodatnie i ujemne.</span><span class="sxs-lookup"><span data-stu-id="c1442-245">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="c1442-246">Ma `AreaUnderRocCurve` być tak blisko jednego, jak to możliwe.</span><span class="sxs-lookup"><span data-stu-id="c1442-246">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

- <span data-ttu-id="c1442-247">`F1Score`Metryka pobiera wynik F1 modelu, który jest miarą równowagi między [dokładnością](../resources/glossary.md#precision) i [odwołaniem](../resources/glossary.md#recall).</span><span class="sxs-lookup"><span data-stu-id="c1442-247">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="c1442-248">Ma `F1Score` być tak blisko jednego, jak to możliwe.</span><span class="sxs-lookup"><span data-stu-id="c1442-248">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="c1442-249">Przewidywanie wyniku danych testowych</span><span class="sxs-lookup"><span data-stu-id="c1442-249">Predict the test data outcome</span></span>

1. <span data-ttu-id="c1442-250">Utwórz `UseModelWithSingleItem()` metodę, tuż po `Evaluate()` metodzie, przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="c1442-250">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="c1442-251">`UseModelWithSingleItem()`Metoda wykonuje następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="c1442-251">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    - <span data-ttu-id="c1442-252">Tworzy pojedynczy komentarz dotyczący danych testowych.</span><span class="sxs-lookup"><span data-stu-id="c1442-252">Creates a single comment of test data.</span></span>
    - <span data-ttu-id="c1442-253">Przewidywania tonacji na podstawie danych testowych.</span><span class="sxs-lookup"><span data-stu-id="c1442-253">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="c1442-254">Łączy dane testowe i prognozy na potrzeby raportowania.</span><span class="sxs-lookup"><span data-stu-id="c1442-254">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="c1442-255">Wyświetla przewidywane wyniki.</span><span class="sxs-lookup"><span data-stu-id="c1442-255">Displays the predicted results.</span></span>

2. <span data-ttu-id="c1442-256">Dodaj wywołanie do nowej metody z `Main()` metody, bezpośrednio pod `Evaluate()` wywołaniem metody, przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="c1442-256">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](./snippets/sentiment-analysis/csharp/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="c1442-257">Dodaj następujący kod, aby utworzyć jako pierwszy wiersz w `UseModelWithSingleItem()` metodzie:</span><span class="sxs-lookup"><span data-stu-id="c1442-257">Add the following code to create as the first line in the `UseModelWithSingleItem()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](./snippets/sentiment-analysis/csharp/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="c1442-258">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) jest WYGODNYm interfejsem API, który umożliwia prognozowanie jednego wystąpienia danych.</span><span class="sxs-lookup"><span data-stu-id="c1442-258">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="c1442-259">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)nie jest bezpieczny wątkowo.</span><span class="sxs-lookup"><span data-stu-id="c1442-259">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="c1442-260">Jest to możliwe do użycia w środowiskach wielowątkowych lub prototypowych.</span><span class="sxs-lookup"><span data-stu-id="c1442-260">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="c1442-261">Aby zwiększyć wydajność i bezpieczeństwo wątków w środowiskach produkcyjnych, należy użyć `PredictionEnginePool` usługi, która tworzy [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) obiekty do użycia w całej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c1442-261">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="c1442-262">Zapoznaj się z tym przewodnikiem dotyczącym [korzystania `PredictionEnginePool` z programu w ASP.NET Core INTERNETowym interfejsie API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="c1442-262">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c1442-263">`PredictionEnginePool`rozszerzenie usługi jest obecnie w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="c1442-263">`PredictionEnginePool` service extension is currently in preview.</span></span>

4. <span data-ttu-id="c1442-264">Dodaj komentarz, aby przetestować prognozę przeszkolonego modelu w `UseModelWithSingleItem()` metodzie, tworząc wystąpienie `SentimentData` :</span><span class="sxs-lookup"><span data-stu-id="c1442-264">Add a comment to test the trained model's prediction in the `UseModelWithSingleItem()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](./snippets/sentiment-analysis/csharp/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="c1442-265">Przekaż dane komentarza testowego do elementu [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) przez dodanie następujących elementów jako następnych wierszy kodu w `UseModelWithSingleItem()` metodzie:</span><span class="sxs-lookup"><span data-stu-id="c1442-265">Pass the test comment data to the [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](./snippets/sentiment-analysis/csharp/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="c1442-266">Funkcja [przewidywania ()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) dokonuje prognozowania dla pojedynczego wiersza danych.</span><span class="sxs-lookup"><span data-stu-id="c1442-266">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="c1442-267">Wyświetlaj `SentimentText` i odpowiadaj prognozie tonacji przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="c1442-267">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](./snippets/sentiment-analysis/csharp/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="c1442-268">Używanie modelu do przewidywania</span><span class="sxs-lookup"><span data-stu-id="c1442-268">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="c1442-269">Wdrażanie i prognozowanie elementów wsadowych</span><span class="sxs-lookup"><span data-stu-id="c1442-269">Deploy and predict batch items</span></span>

1. <span data-ttu-id="c1442-270">Utwórz `UseModelWithBatchItems()` metodę, tuż po `UseModelWithSingleItem()` metodzie, przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="c1442-270">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="c1442-271">`UseModelWithBatchItems()`Metoda wykonuje następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="c1442-271">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    - <span data-ttu-id="c1442-272">Tworzy dane testów wsadowych.</span><span class="sxs-lookup"><span data-stu-id="c1442-272">Creates batch test data.</span></span>
    - <span data-ttu-id="c1442-273">Przewidywania tonacji na podstawie danych testowych.</span><span class="sxs-lookup"><span data-stu-id="c1442-273">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="c1442-274">Łączy dane testowe i prognozy na potrzeby raportowania.</span><span class="sxs-lookup"><span data-stu-id="c1442-274">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="c1442-275">Wyświetla przewidywane wyniki.</span><span class="sxs-lookup"><span data-stu-id="c1442-275">Displays the predicted results.</span></span>

2. <span data-ttu-id="c1442-276">Dodaj wywołanie do nowej metody z `Main` metody, bezpośrednio pod `UseModelWithSingleItem()` wywołaniem metody, przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="c1442-276">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](./snippets/sentiment-analysis/csharp/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="c1442-277">Dodaj komentarze, aby przetestować przewidywania modeli przeszkolonych w `UseModelWithBatchItems()` metodzie:</span><span class="sxs-lookup"><span data-stu-id="c1442-277">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](./snippets/sentiment-analysis/csharp/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="c1442-278">Tonacji komentarz przewidywania</span><span class="sxs-lookup"><span data-stu-id="c1442-278">Predict comment sentiment</span></span>

<span data-ttu-id="c1442-279">Użyj modelu, aby przewidzieć tonacji danych komentarzy przy użyciu metody [Transform ()](xref:Microsoft.ML.ITransformer.Transform%2A) :</span><span class="sxs-lookup"><span data-stu-id="c1442-279">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](./snippets/sentiment-analysis/csharp/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="c1442-280">Łączenie i wyświetlanie prognoz</span><span class="sxs-lookup"><span data-stu-id="c1442-280">Combine and display the predictions</span></span>

<span data-ttu-id="c1442-281">Utwórz nagłówek dla prognoz przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="c1442-281">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](./snippets/sentiment-analysis/csharp/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="c1442-282">Ponieważ `SentimentPrediction` jest dziedziczona z `SentimentData` , `Transform()` Metoda jest wypełniana `SentimentText` polami przewidywanymi.</span><span class="sxs-lookup"><span data-stu-id="c1442-282">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="c1442-283">Gdy proces ML.NET przetwarza, każdy składnik dodaje kolumny, co ułatwia wyświetlanie wyników:</span><span class="sxs-lookup"><span data-stu-id="c1442-283">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](./snippets/sentiment-analysis/csharp/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="c1442-284">Wyniki</span><span class="sxs-lookup"><span data-stu-id="c1442-284">Results</span></span>

<span data-ttu-id="c1442-285">Wyniki powinny wyglądać podobnie do poniższego.</span><span class="sxs-lookup"><span data-stu-id="c1442-285">Your results should be similar to the following.</span></span> <span data-ttu-id="c1442-286">Podczas przetwarzania wyświetlane są komunikaty.</span><span class="sxs-lookup"><span data-stu-id="c1442-286">During processing, messages are displayed.</span></span> <span data-ttu-id="c1442-287">Mogą pojawić się ostrzeżenia lub przetwarzanie komunikatów.</span><span class="sxs-lookup"><span data-stu-id="c1442-287">You may see warnings, or processing messages.</span></span> <span data-ttu-id="c1442-288">Zostały one usunięte z następujących wyników dla przejrzystości.</span><span class="sxs-lookup"><span data-stu-id="c1442-288">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 83.96%
Auc: 90.51%
F1Score: 84.04%

=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.1027377
=============== End of Predictions ===============

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1369192
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9960636
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="c1442-289">Gratulacje!</span><span class="sxs-lookup"><span data-stu-id="c1442-289">Congratulations!</span></span> <span data-ttu-id="c1442-290">Pomyślnie skompilowano model uczenia maszynowego do klasyfikowania i przewidywania komunikatów tonacji.</span><span class="sxs-lookup"><span data-stu-id="c1442-290">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="c1442-291">Kompilowanie udanych modeli jest procesem iteracyjnym.</span><span class="sxs-lookup"><span data-stu-id="c1442-291">Building successful models is an iterative process.</span></span> <span data-ttu-id="c1442-292">Ten model ma wstępną niższą jakość, ponieważ samouczek używa małych zestawów danych w celu zapewnienia szybkiego szkolenia modeli.</span><span class="sxs-lookup"><span data-stu-id="c1442-292">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="c1442-293">Jeśli jakość modelu jest niezadowalająca, możesz spróbować go ulepszyć, dostarczając większe zestawy danych szkoleniowych lub wybierając różne algorytmy szkoleniowe z różnymi [parametrami funkcji Hyper-Parameters](../resources/glossary.md#hyperparameter) dla każdego algorytmu.</span><span class="sxs-lookup"><span data-stu-id="c1442-293">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md#hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="c1442-294">Kod źródłowy dla tego samouczka można znaleźć w repozytorium [dotnet/Samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) .</span><span class="sxs-lookup"><span data-stu-id="c1442-294">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c1442-295">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="c1442-295">Next steps</span></span>

<span data-ttu-id="c1442-296">W niniejszym samouczku zawarto informacje na temat wykonywania następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="c1442-296">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="c1442-297">Tworzenie aplikacji konsolowej</span><span class="sxs-lookup"><span data-stu-id="c1442-297">Create a console application</span></span>
> - <span data-ttu-id="c1442-298">Przygotowywanie danych</span><span class="sxs-lookup"><span data-stu-id="c1442-298">Prepare data</span></span>
> - <span data-ttu-id="c1442-299">Ładowanie danych</span><span class="sxs-lookup"><span data-stu-id="c1442-299">Load the data</span></span>
> - <span data-ttu-id="c1442-300">Kompilowanie i uczenie modelu</span><span class="sxs-lookup"><span data-stu-id="c1442-300">Build and train the model</span></span>
> - <span data-ttu-id="c1442-301">Ocena modelu</span><span class="sxs-lookup"><span data-stu-id="c1442-301">Evaluate the model</span></span>
> - <span data-ttu-id="c1442-302">Tworzenie prognoz przy użyciu modelu</span><span class="sxs-lookup"><span data-stu-id="c1442-302">Use the model to make a prediction</span></span>
> - <span data-ttu-id="c1442-303">Zobacz wyniki</span><span class="sxs-lookup"><span data-stu-id="c1442-303">See the results</span></span>

<span data-ttu-id="c1442-304">Przejdź do następnego samouczka, aby dowiedzieć się więcej</span><span class="sxs-lookup"><span data-stu-id="c1442-304">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="c1442-305">Klasyfikacja problemu</span><span class="sxs-lookup"><span data-stu-id="c1442-305">Issue Classification</span></span>](github-issue-classification.md)
