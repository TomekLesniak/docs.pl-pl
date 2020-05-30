---
title: Debugowanie aplikacji konsolowej .NET Core za pomocą Visual Studio Code
description: Dowiedz się, jak debugować aplikację konsolową .NET Core za pomocą Visual Studio Code.
ms.date: 05/26/2020
ms.openlocfilehash: eaeb97f54442006d2f0e29483a68dc3de89b5778
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202590"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-code"></a>Samouczek: debugowanie aplikacji konsolowej .NET Core przy użyciu Visual Studio Code

W tym samouczku przedstawiono narzędzia debugowania dostępne w Visual Studio Code do pracy z aplikacjami .NET Core.

## <a name="prerequisites"></a>Wymagania wstępne

- Ten samouczek współpracuje z aplikacją konsolową utworzoną w temacie [Tworzenie aplikacji konsolowej platformy .NET Core w Visual Studio Code](with-visual-studio-code.md).

## <a name="use-debug-build-configuration"></a>Użyj konfiguracji kompilacji debugowania

*Debugowanie* i *wydanie* są dwoma konfiguracjami kompilacji programu .NET Core. Konfiguracja kompilacji debugowania umożliwia debugowanie i konfigurację wydania dla ostatecznej dystrybucji wersji.

W konfiguracji debugowania program kompiluje z pełnymi symbolicznymi informacjami o debugowaniu i bez optymalizacji. Optymalizacja komplikuje debugowanie, ponieważ relacja między kodem źródłowym i wygenerowanymi instrukcjami jest bardziej skomplikowana. Konfiguracja wydania programu nie ma symbolicznych informacji o debugowaniu i jest w pełni zoptymalizowana.

 Domyślnie Visual Studio Code używa konfiguracji kompilacji debugowania, więc nie trzeba jej zmieniać przed debugowaniem.

## <a name="set-a-breakpoint"></a>Ustawianie punktu przerwania

Punkt przerwania tymczasowo przerywa wykonywanie aplikacji *przed* wykonaniem wiersza z punktem przerwania.

1. W *program.cs*Ustaw *punkt przerwania* w wierszu, który wyświetla nazwę, datę i godzinę, klikając na lewym marginesie okna kod. Lewy margines znajduje się po lewej stronie numerów wierszy. Innym sposobem ustawienia punktu przerwania jest umieszczenie kursora w wierszu kodu, a następnie naciśnięcie klawisza <kbd>F9</kbd>.

   Jak pokazano na poniższej ilustracji, Visual Studio Code wskazuje wiersz, w którym jest ustawiony punkt przerwania, wyświetlając czerwoną kropkę na lewym marginesie.

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-set.png" alt-text="Zestaw punktów przerwania":::

## <a name="set-up-for-terminal-input"></a>Konfiguracja dla danych wejściowych terminalu

Punkt przerwania znajduje się po `Console.ReadLine` wywołaniu metody. **Konsola debugowania** nie akceptuje danych wejściowych terminalu dla uruchomionego programu. Aby obsłużyć dane wejściowe terminalu podczas debugowania, można użyć zintegrowanego terminalu (jednego z Visual Studio Code systemu Windows) lub terminalu zewnętrznego. W tym samouczku użyjesz zintegrowanego terminalu.

1. Otwórz plik *. programu vscode/Launch. JSON*.

1. Zmień `console` ustawienie na `integratedTerminal` .

   Od:

   ```
   "console": "internalConsole",
   ```

   Do:

   ```
   "console": "integratedTerminal",
   ```

1. Zapisz zmiany.

## <a name="start-debugging"></a>Rozpocznij debugowanie

1. Otwórz widok debugowanie, wybierając ikonę debugowania w menu po lewej stronie.

   :::image type="content" source="media/debugging-with-visual-studio-code/select-debug-pane.png" alt-text="Otwórz kartę debugowanie w Visual Studio Code":::

1. Rozpocznij debugowanie, wybierając zieloną strzałkę w górnej części okienka, obok pozycji **.NET Core Launch (konsola)**.  Innym sposobem rozpoczęcia debugowania jest naciśnięcie klawisza <kbd>F5</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-code/start-debugging.png" alt-text="Rozpocznij debugowanie":::

1. Wybierz kartę **Terminal** , aby zobaczyć "Jaka jest Twoja nazwa?". Monituj o wyświetlenie programu przed oczekiwaniem na odpowiedź.

   :::image type="content" source="media/debugging-with-visual-studio-code/select-terminal.png" alt-text="Wybierz kartę Terminal":::

1. Wprowadź ciąg w oknie **terminalu** w odpowiedzi na monit o podanie nazwy, a następnie naciśnij klawisz <kbd>Enter</kbd>.

   Wykonanie programu zostaje zatrzymane po osiągnięciu punktu przerwania i przed wykonaniem `Console.WriteLine` metody. Sekcja **locales** w oknie **zmienne** zawiera wartości zmiennych, które są zdefiniowane w aktualnie wykonywanej metodzie.

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-hit.png" alt-text="Trafienie punktu przerwania, Wyświetlanie ustawień lokalnych":::

## <a name="change-variable-values"></a>Zmień wartości zmiennych

Okno **konsoli debugowania** umożliwia korzystanie z debugowanej aplikacji. Można zmienić wartość zmiennych, aby zobaczyć, jak ma to wpływ na program.

1. Wybierz kartę **konsola debugowania** .

1. Wprowadź `name = "Gracie"` w wierszu polecenia u dołu okna **konsoli debugowania** i naciśnij klawisz <kbd>Enter</kbd> .

   :::image type="content" source="media/debugging-with-visual-studio-code/change-variable-values.png" alt-text="Zmień wartości zmiennych":::

1. Wprowadź `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` w dolnej części okna **konsoli debugowania** i naciśnij klawisz <kbd>Enter</kbd> .

   W oknie **zmienne** są wyświetlane nowe wartości `name` `date` zmiennych i.

1. Kontynuuj wykonywanie programu, wybierając przycisk **Kontynuuj** na pasku narzędzi. Innym sposobem, aby kontynuować, jest naciśnięcie klawisza <kbd>F5</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-code/continue-debugging.png" alt-text="Kontynuuj debugowanie":::

1. Ponownie wybierz kartę **terminala** .

   Wartości wyświetlane w oknie konsoli odpowiadają zmianom wprowadzonym w **konsoli debugowania**.

   :::image type="content" source="media/debugging-with-visual-studio-code/changed-variable-values.png" alt-text="Terminal pokazujący wprowadzone wartości":::

1. Naciśnij dowolny klawisz, aby zamknąć aplikację i zatrzymać debugowanie.

## <a name="set-a-conditional-breakpoint"></a>Ustaw punkt przerwania warunkowego

Program wyświetla ciąg wprowadzony przez użytkownika. Co się stanie, jeśli użytkownik nie wprowadzi niczego? Można to sprawdzić za pomocą przydatnej funkcji debugowania zwanej *warunkowym punktem przerwania*.

1. Kliknij prawym przyciskiem myszy (<kbd>Ctrl</kbd>+ kliknięcie na macOS) w czerwonej kropki, która reprezentuje punkt przerwania. W menu kontekstowym wybierz pozycję **Edytuj punkt przerwania** , aby otworzyć okno dialogowe, które umożliwia wprowadzenie wyrażenia warunkowego.

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-context-menu.png" alt-text="Menu kontekstowe punktu przerwania":::

1. Wybierz `Expression` z listy rozwijanej, wprowadź następujące wyrażenie warunkowe, a następnie naciśnij klawisz <kbd>Enter</kbd>.

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/conditional-expression.png" alt-text="Wprowadź wyrażenie warunkowe":::

   Za każdym razem, gdy punkt przerwania został trafiony, debuger wywołuje `String.IsNullOrEmpty(name)` metodę i przerywa w tym wierszu tylko wtedy, gdy wywołanie metody zwróci wartość `true` .

   Zamiast wyrażenia warunkowego można określić *liczbę trafień*, która przerywa wykonywanie programu, zanim instrukcja zostanie wykonana określoną liczbę razy lub *warunek filtru*, który przerywa wykonywanie programu w oparciu o takie atrybuty jak identyfikator wątku, nazwa procesu lub nazwa wątku.

1. Uruchom program z debugowaniem, naciskając klawisz <kbd>F5</kbd>.

1. Na karcie **Terminal** naciśnij klawisz <kbd>Enter</kbd> po wyświetleniu monitu, aby wprowadzić swoją nazwę.

   Ponieważ określony warunek ( `name` is `null` lub) został <xref:System.String.Empty?displayProperty=nameWithType> spełniony, wykonanie programu zatrzyma się po osiągnięciu punktu przerwania i przed wykonaniem `Console.WriteLine` metody.

   Okno **zmienne** pokazuje, że wartość `name` zmiennej to `""` , lub <xref:System.String.Empty?displayProperty=nameWithType> .

1. Potwierdź, że wartość jest pustym ciągiem, wprowadzając poniższą instrukcję w wierszu **konsoli debugowania** i naciskając klawisz <kbd>Enter</kbd>. Wynik to `true` .

   ```csharp
   name == String.Empty
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/expression-in-debug-console.png" alt-text="Konsola debugowania zwracająca wartość true po wykonaniu instrukcji":::

1. Wybierz przycisk **Kontynuuj** na pasku narzędzi, aby kontynuować wykonywanie programu.

1. Wybierz kartę **Terminal** i naciśnij dowolny klawisz, aby wyjść z programu i zatrzymać debugowanie.

1. Wyczyść punkt przerwania, klikając kropkę na lewym marginesie okna kod. Innym sposobem na wyczyszczenie punktu przerwania jest naciśnięcie klawisza <kbd>F9</kbd> podczas wybierania wiersza kodu.

1. Jeśli zostanie wyświetlone ostrzeżenie, że warunek punktu przerwania zostanie utracony, wybierz pozycję **Usuń punkt przerwania**.

## <a name="step-through-a-program"></a>Przechodzenie przez program

Visual Studio Code umożliwia również krok po kroku w wierszu przez program i monitorowanie jego wykonania. Zwykle ustawiasz punkt przerwania i obserwuj przepływ programu za pomocą niewielkiej części kodu programu. Ponieważ ten program jest mały, możesz przejść przez cały program.

1. Ustaw punkt przerwania w otwierającym nawiasie klamrowym `Main` metody.

1. Naciśnij klawisz <kbd>F5</kbd>, aby uruchomić debugowanie.

   Visual Studio Code podświetla linię punktu przerwania.

   W tym momencie okno **zmienne** pokazuje, że `args` Tablica jest pusta i `name` i `date` ma wartości domyślne.

1. Wybierz pozycję **Wkrocz** lub naciśnij klawisz <kbd>F11</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-code/step-into.png" alt-text="Przycisk "krok po kroku"":::

   Visual Studio Code podświetla następny wiersz.

1. Wybierz pozycję **Wkrocz** lub naciśnij klawisz <kbd>F11</kbd>.

   Visual Studio Code wykonuje `Console.WriteLine` monit o podanie nazwy i wyróżnia następny wiersz wykonania. Następnym wierszem jest `Console.ReadLine` `name` . Okno **zmiennych** jest niezmienione, a na karcie **terminala** zostanie wyświetlona wartość "co to jest Twoja nazwa?" pytać.

1. Wybierz pozycję **Wkrocz** lub naciśnij klawisz <kbd>F11</kbd>.

   Program Visual Studio podświetla `name` przypisanie zmiennej. Okno **zmienne** pokazuje, że `name` jest nadal `null` .

1. Odpowiedz na monit, wprowadzając ciąg na karcie Terminal i naciskając klawisz <kbd>Enter</kbd>.

   Na karcie **terminala** może nie być wyświetlany ciąg wprowadzony podczas jego wprowadzania, ale <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> Metoda przechwytuje dane wejściowe.

1. Wybierz pozycję **Wkrocz** lub naciśnij klawisz <kbd>F11</kbd>.

   Visual Studio Code podświetla `date` przypisanie zmiennej. Okno **zmienne** pokazuje wartość zwracaną przez wywołanie <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> metody. Na karcie **Terminal** zostanie wyświetlony ciąg wprowadzony w wierszu polecenia.

1. Wybierz pozycję **Wkrocz** lub naciśnij klawisz <kbd>F11</kbd>.

   Okno **zmienne** zawiera wartość `date` zmiennej po przypisaniu z <xref:System.DateTime.Now?displayProperty=nameWithType> właściwości.

1. Wybierz pozycję **Wkrocz** lub naciśnij klawisz <kbd>F11</kbd>.

   Visual Studio Code wywołuje <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> metodę. W oknie konsoli zostanie wyświetlony sformatowany ciąg.

1. Wybierz pozycję **Wyjdź** lub naciśnij klawisz <kbd>SHIFT</kbd> + <kbd>F11</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-code/step-out.png" alt-text="Przycisk krok po kroku":::

1. Wybierz kartę **Terminal** .

   W terminalu zostanie wyświetlony komunikat "naciśnij dowolny klawisz, aby wyjść..."

1. Naciśnij dowolny klawisz, aby wyjść z programu.

## <a name="select-release-build-configuration"></a>Wybierz konfigurację kompilacji wydania

Po przetestowaniu wersji debugowania aplikacji należy również skompilować i przetestować wersję publikacji. Wersja wydania obejmuje optymalizacje kompilatora, które mogą mieć wpływ na zachowanie aplikacji. Na przykład optymalizacje kompilatora, które mają na celu poprawę wydajności, mogą tworzyć sytuacje wyścigu w aplikacjach wielowątkowych.

Aby skompilować i przetestować wydaną wersję aplikacji konsolowej, Otwórz **Terminal** i uruchom następujące polecenie:

```dotnetcli
dotnet run --configuration Release
```

## <a name="additional-resources"></a>Zasoby dodatkowe

* [Debugowanie w Visual Studio Code](https://code.visualstudio.com/docs/editor/debugging)

## <a name="next-steps"></a>Następne kroki

W tym samouczku użyto narzędzi debugowania Visual Studio Code. Aby dowiedzieć się, jak opublikować wdrożoną wersję aplikacji, zobacz temat [publikowanie aplikacji](cli-create-console-app.md#publish-your-app).

<!--In the next tutorial, you publish a deployable version of the app.

> [!div class="nextstepaction"]
> [Publish a .NET Core console application with Visual Studio Code](publishing-with-visual-studio-code.md)
-->