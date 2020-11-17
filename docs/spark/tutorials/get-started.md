---
title: Wprowadzenie do platformy .NET dla Apache Spark
description: Dowiedz się, jak uruchomić aplikację .NET dla Apache Spark przy użyciu platformy .NET Core w systemach Windows, macOS i Ubuntu.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 16ccc8f40f290c4bc10f03d1f4d1b296b17f6b11
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687828"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Samouczek: Rozpoczynanie pracy z platformą .NET dla Apache Spark

W tym samouczku przedstawiono sposób uruchamiania aplikacji platformy .NET dla Apache Spark przy użyciu platformy .NET Core w systemach Windows, macOS i Ubuntu.

Z tego samouczka dowiesz się, jak wykonywać następujące czynności:

> [!div class="checklist"]
>
> * Przygotuj środowisko dla platformy .NET dla Apache Spark
> * Napisz swoją pierwszą aplikację .NET dla Apache Spark
> * Kompilowanie i uruchamianie aplikacji platformy .NET dla Apache Spark

## <a name="prepare-your-environment"></a>Przygotowywanie środowiska

Przed rozpoczęciem pisania aplikacji należy skonfigurować niektóre zależności wymagane wstępnie. Jeśli można uruchomić `dotnet` polecenie, `java` w `spark-shell` środowisku wiersza polecenia, środowisko jest już przygotowane i można przejść do następnej sekcji. Jeśli nie można uruchomić żadnego lub wszystkich poleceń, wykonaj następujące czynności.

### <a name="1-install-net"></a>1. Zainstaluj platformę .NET

Aby rozpocząć tworzenie aplikacji platformy .NET, należy pobrać i zainstalować zestaw .NET SDK (Software Development Kit).

Pobierz i zainstaluj [zestaw .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1). Zainstalowanie zestawu SDK dodaje `dotnet` łańcucha narzędzi do ścieżki.

Po zainstalowaniu zestaw .NET Core SDK Otwórz nowy wiersz polecenia lub terminal i uruchom polecenie `dotnet` .

Jeśli polecenie jest uruchamiane i drukuje informacje o sposobach korzystania z programu dotnet, można przejść do następnego kroku. Jeśli `'dotnet' is not recognized as an internal or external command` wystąpi błąd, upewnij się, że otwarto **Nowy** wiersz polecenia lub terminal przed uruchomieniem polecenia.

### <a name="2-install-java"></a>2. Zainstaluj środowisko Java

Zainstaluj [środowisko Java 8,1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) dla systemu Windows i MacOS lub [OpenJDK 8](https://openjdk.java.net/install/) dla Ubuntu.

Wybierz odpowiednią wersję systemu operacyjnego. Na przykład wybierz **jdk-8u201-windows-x64.exe** dla komputera z systemem Windows x64 (jak pokazano poniżej) lub **JDK-8u231-macosx-x64. dmg** dla macOS. Następnie użyj polecenia, `java` Aby zweryfikować instalację.

![Pobieranie w języku Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a>3. Zainstaluj oprogramowanie do kompresji

Apache Spark jest pobierany jako skompresowany plik TGZ. Użyj programu wyodrębniania, takiego jak [7-zip](https://www.7-zip.org/) lub [WinZip](https://www.winzip.com/), aby wyodrębnić plik.

### <a name="4-install-apache-spark"></a>4. Zainstaluj Apache Spark

[Pobierz i zainstaluj Apache Spark](https://spark.apache.org/downloads.html). Należy wybrać jedną z wersji 2,3. * lub 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 lub 3.0.1 (.NET dla Apache Spark nie jest zgodna z innymi wersjami Apache Spark).

Polecenia używane w poniższych krokach założono, że zostały [pobrane i zainstalowane Apache Spark 3.0.1](https://spark.apache.org/downloads.html). Jeśli chcesz użyć innej wersji, Zamień **3.0.1** na odpowiedni numer wersji. Następnie wyodrębnij plik **. tar** i pliki Apache Spark.

Aby wyodrębnić zagnieżdżony plik **tar** :

* Znajdź pobrany plik **Spark-3.0.1-bin-Hadoop 2.7. tgz** .
* Kliknij prawym przyciskiem myszy plik i wybierz **7-zip-> Wyodrębnij tutaj**.
* **Spark-3.0.1-bin-Hadoop 2.7. tar** jest tworzony obok pobranego pliku **. tgz** .

Aby wyodrębnić pliki Apache Spark:

* Kliknij prawym przyciskiem myszy pozycję **Spark-3.0.1-bin-Hadoop 2.7. tar** i wybierz pozycję **7-zip-> Wyodrębnianie plików...**
* Wprowadź **C:\Bin** w polu **Wyodrębnij do** .
* Usuń zaznaczenie pola wyboru pod polem **Wyodrębnij do** .
* Wybierz przycisk **OK**.
* Pliki Apache Spark są wyodrębniane do C:\bin\spark-3.0.1-bin-hadoop2.7\

![Zainstaluj platformę Spark](./media/spark-extract-with-7-zip.png)

Uruchom następujące polecenia, aby ustawić zmienne środowiskowe używane do lokalizowania Apache Spark. W systemie Windows pamiętaj, aby uruchomić wiersz polecenia w trybie administratora.

#### <a name="windows"></a>[Windows](#tab/windows)

```console
setx /M HADOOP_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M SPARK_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M PATH "%PATH%;%HADOOP_HOME%;%SPARK_HOME%\bin"
```

#### <a name="maclinux"></a>[System Mac/Linux](#tab/linux)

```bash
export SPARK_HOME=~/bin/spark-3.0.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

---

Po zainstalowaniu wszystkiego i ustawieniu zmiennych środowiskowych Otwórz **Nowy** wiersz polecenia lub terminal i uruchom następujące polecenie:

```text
spark-submit --version
```

Jeśli polecenie jest uruchamiane i drukuje informacje o wersji, można przejść do następnego kroku.

Jeśli `'spark-submit' is not recognized as an internal or external command` wystąpi błąd, upewnij się, że otwarto **Nowy** wiersz polecenia.

### <a name="5-install-net-for-apache-spark"></a>5. Zainstaluj program .NET dla Apache Spark

Pobierz wydanie [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) z platformy .net dla Apache Spark GitHub. Na przykład jeśli korzystasz z komputera z systemem Windows i planujesz używać platformy .NET Core, [Pobierz wydanie systemu Windows x64 netcoreapp 3.1](https://github.com/dotnet/spark/releases).

Aby wyodrębnić pakiet Microsoft. Spark. Worker:

* Znajdź pobrany plik **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-1.0.0.zip** .
* Kliknij prawym przyciskiem myszy i wybierz **7-zip-> Wyodrębnianie plików.**...
* Wprowadź **C:\Bin** w polu **Wyodrębnij do** .
* Usuń zaznaczenie pola wyboru pod polem **Wyodrębnij do** .
* Wybierz przycisk **OK**.

### <a name="6-install-winutils-windows-only"></a>6. Zainstaluj WinUtils (tylko system Windows)

Platforma .NET dla Apache Spark wymaga zainstalowania WinUtils razem z Apache Spark. [Pobierz winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe). Następnie skopiuj WinUtils do **C:\bin\spark-3.0.1-bin-hadoop2.7\bin**.

> [!NOTE]
> Jeśli używasz innej wersji usługi Hadoop, która ma adnotację na końcu nazwy folderu instalacji platformy Spark, [Wybierz wersję WinUtils](https://github.com/steveloughran/winutils) zgodną z wersją usługi Hadoop.

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a>7. Ustaw DOTNET_WORKER_DIR i sprawdź zależności

Uruchom jedno z następujących poleceń, aby ustawić `DOTNET_WORKER_DIR` zmienną środowiskową, która jest używana przez aplikacje platformy .NET do lokalizowania danych binarnych programu .NET dla Apache Spark. Upewnij się, że zastąpisz do katalogu, do którego `<PATH-DOTNET_WORKER_DIR>` został pobrany i wyodrębniony `Microsoft.Spark.Worker` . W systemie Windows pamiętaj, aby uruchomić wiersz polecenia w trybie administratora.

#### <a name="windows"></a>[Windows](#tab/windows)

```console
setx /M DOTNET_WORKER_DIR <PATH-DOTNET-WORKER-DIR>
```

#### <a name="maclinux"></a>[System Mac/Linux](#tab/linux)

```bash
export DOTNET_WORKER_DIR=<PATH-DOTNET-WORKER-DIR>
```

---

Na koniec sprawdź, czy można uruchomić `dotnet` polecenie, `java` `spark-shell` z poziomu wiersza polecenia przed przejściem do następnej sekcji.

## <a name="write-a-net-for-apache-spark-app"></a>Napisz aplikację platformy .NET dla Apache Spark

### <a name="1-create-a-console-app"></a>1. Tworzenie aplikacji konsolowej

W wierszu polecenia lub terminalu uruchom następujące polecenia, aby utworzyć nową aplikację konsolową:

```dotnetcli
dotnet new console -o MySparkApp
cd MySparkApp
```

`dotnet`Polecenie tworzy `new` aplikację typu `console` . `-o`Parametr tworzy katalog o nazwie *MySparkApp* , w którym jest przechowywana aplikacja i wypełnia je wymaganymi plikami. `cd MySparkApp`Polecenie zmienia katalog na utworzony katalog aplikacji.

### <a name="2-install-nuget-package"></a>2. Zainstaluj pakiet NuGet

Aby używać platformy .NET do Apache Spark w aplikacji, zainstaluj pakiet Microsoft. Spark. W wierszu polecenia lub terminalu uruchom następujące polecenie:

```dotnetcli
dotnet add package Microsoft.Spark
```

> [!NOTE]
> Ten samouczek używa najnowszej wersji `Microsoft.Spark` pakietu NuGet, o ile nie określono inaczej.

### <a name="3-write-your-app"></a>3. Napisz aplikację

Otwórz *program.cs* w Visual Studio Code lub dowolnym edytorze tekstów i Zastąp cały kod następującym kodem:

```csharp
using Microsoft.Spark.Sql;
using static Microsoft.Spark.Sql.Functions;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create Spark session
            SparkSession spark =
                SparkSession
                    .Builder()
                    .AppName("word_count_sample")
                    .GetOrCreate();

            // Create initial DataFrame
            string filePath = args[0];
            DataFrame dataFrame = spark.Read().Text(filePath);

            //Count words
            DataFrame words =
                dataFrame
                    .Select(Split(Col("value")," ").Alias("words"))
                    .Select(Explode(Col("words")).Alias("word"))
                    .GroupBy("word")
                    .Count()
                    .OrderBy(Col("count").Desc());

            // Display results
            words.Show();

            // Stop Spark session
            spark.Stop();
        }
    }
}
```

[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) to punkt wejścia aplikacji Apache Spark, który zarządza kontekstem i informacjami aplikacji. Przy użyciu metody [tekstowej](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) dane tekstowe z pliku określonego przez `filePath` jest odczytywane w [ramce Dataframe](xref:Microsoft.Spark.Sql.DataFrame). Element Dataframe to sposób organizowania danych w zestaw nazwanych kolumn. Następnie seria transformacji jest stosowana do dzielenia zdań w pliku, grupowania każdego z nich i policzania ich w kolejności malejącej. Wynik tych operacji jest przechowywany w innej ramce Dataframe. Należy zauważyć, że w tym momencie nie wykonano żadnych operacji, ponieważ platforma .NET dla Apache Spark opóźnieniem oblicza dane. Nie do momentu wywołania metody [show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) , aby wyświetlić zawartość `words` przekształconego ramki danych do konsoli, że operacje zdefiniowane w wierszach powyżej zostały wykonane. Gdy sesja platformy Spark nie jest już potrzebna, użyj metody [stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) , aby zatrzymać sesję.

### <a name="4-create-data-file"></a>4. Utwórz plik danych

Aplikacja przetwarza plik zawierający wiersze tekstu. Utwórz plik o nazwie *input.txt* pliku w katalogu *MySparkApp* , zawierający następujący tekst:

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

Zapisz zmiany i zamknij plik.

## <a name="run-your-net-for-apache-spark-app"></a>Uruchamianie aplikacji platformy .NET dla Apache Spark

Uruchom następujące polecenie, aby skompilować aplikację:

```dotnetcli
dotnet build
```

Przejdź do katalogu wyjściowego kompilacji i użyj polecenia, `spark-submit` Aby przesłać aplikację do uruchamiania na Apache Spark. Pamiętaj, aby zamienić na  `<version>` wersję programu .NET Worker i `<path-of-input.txt>` ścieżkę pliku *input.txt* .

### <a name="windows"></a>[Windows](#tab/windows)

```console
spark-submit ^
--class org.apache.spark.deploy.dotnet.DotnetRunner ^
--master local ^
microsoft-spark-3-0_2.12-<version>.jar ^
dotnet MySparkApp.dll <path-of-input.txt>
```

### <a name="maclinux"></a>[System Mac/Linux](#tab/linux)

```bash
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master local \
microsoft-spark-3-0_2.12-<version>.jar \
dotnet MySparkApp.dll <path-of-input.txt>
```

---

> [!NOTE]
> W tym poleceniu przyjęto założenie, że pobrano Apache Spark i dodano go do zmiennej środowiskowej PATH, aby można było użyć programu `spark-submit` . W przeciwnym razie należy użyć pełnej ścieżki (na przykład *C:\bin\apache-spark\bin\spark-Submit* lub *~/Spark/bin/Spark-Submit*).

Gdy aplikacja zostanie uruchomiona, dane zliczania wyrazów *input.txt* pliku są zapisywane w konsoli programu.

```console
+------+-----+
|  word|count|
+------+-----+
|  .NET|    3|
|Apache|    2|
|   app|    2|
|  This|    2|
| Spark|    2|
| World|    1|
|counts|    1|
|   for|    1|
| words|    1|
|  with|    1|
| Hello|    1|
|  uses|    1|
+------+-----+
```

Gratulacje! Pomyślnie utworzono i uruchomiono aplikację .NET dla Apache Spark.

## <a name="next-steps"></a>Następne kroki

W niniejszym samouczku zawarto informacje na temat wykonywania następujących czynności:
> [!div class="checklist"]
>
> * Przygotuj środowisko dla platformy .NET dla Apache Spark
> * Napisz swoją pierwszą aplikację .NET dla Apache Spark
> * Kompilowanie i uruchamianie aplikacji platformy .NET dla Apache Spark

Aby wyświetlić film wideo z objaśnieniem powyższych kroków, zapoznaj się z [serią filmów dla programu .net for Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).

Zapoznaj się ze stroną zasobów, aby dowiedzieć się więcej.
> [!div class="nextstepaction"]
> [Platforma .NET dla Apache Spark zasobów](../resources/index.md)
