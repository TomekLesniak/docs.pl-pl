---
title: Tworzenie aplikacji konsolowej .NET przy użyciu programu Visual Studio
description: Dowiedz się, jak utworzyć aplikację konsolową .NET przy użyciu języka C# lub Visual Basic za pomocą programu Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: e395122e59f17ed66bbd9d83b01610993f663ce1
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915948"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio"></a>Samouczek: Tworzenie aplikacji konsolowej .NET przy użyciu programu Visual Studio

W tym samouczku pokazano, jak utworzyć i uruchomić aplikację konsolową .NET w programie Visual Studio 2019.

## <a name="prerequisites"></a>Wymagania wstępne

- [Program Visual Studio 2019 w wersji 16,8 lub nowszej](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) z zainstalowanym **wieloplatformowym obciążeniem programistycznym dla platformy .NET Core** . Zestaw .NET 5,0 SDK jest instalowany automatycznie po wybraniu tego obciążenia.

  Aby uzyskać więcej informacji, zobacz [Instalowanie zestawu .NET SDK przy użyciu programu Visual Studio](../install/windows.md#install-with-visual-studio).

## <a name="create-the-app"></a>Tworzenie aplikacji

Utwórz projekt aplikacji konsolowej platformy .NET o nazwie "HelloWorld".

1. Uruchom program Visual Studio 2019.

1. Wybierz pozycję **Narzędzia**  >  **Opcje**  >  **środowisko**  >  w **wersji zapoznawczej**, a następnie wybierz pozycję **Pokaż wszystkie szablony .NET Core w nowym projekcie (wymaga ponownego uruchomienia)**.

   :::image type="content" source="media/with-visual-studio/dotnet-options.png" alt-text="Pokaż wszystkie szablony platformy .NET — opcja":::

1. Zamknij i ponownie otwórz program Visual Studio.

1. Na stronie startowej wybierz pozycję **Utwórz nowy projekt**.

   :::image type="content" source="./media/with-visual-studio/start-window.png" alt-text="Przycisk Utwórz nowy projekt wybrany na stronie startowej programu Visual Studio":::

1. Na stronie **Tworzenie nowego projektu** wprowadź w polu wyszukiwania **konsolę** . Następnie wybierz pozycję **C#** lub **Visual Basic** z listy język, a następnie wybierz pozycję **wszystkie platformy** z listy platform. Wybierz szablon **aplikacja konsoli** , a następnie wybierz przycisk **dalej**.

   :::image type="content" source="./media/with-visual-studio/create-new-project.png" alt-text="Utwórz nowe okno projektu z wybranymi filtrami":::

   > [!TIP]
   > Jeśli szablony platformy .NET nie są widoczne, prawdopodobnie brakuje wymaganego obciążenia. W obszarze **nie można znaleźć tego, czego szukasz?** komunikat wybierz łącze **Zainstaluj więcej narzędzi i funkcji** . Zostanie otwarty Instalator programu Visual Studio. Upewnij się, że masz zainstalowaną **Międzyplatformowe obciążenie programistyczne dla platformy .NET Core** .

1. W oknie dialogowym **Konfigurowanie nowego projektu** wprowadź **HelloWorld** w polu **Nazwa projektu** . Następnie wybierz pozycję **Utwórz**.

   :::image type="content" source="./media/with-visual-studio/configure-new-project.png" alt-text="Skonfiguruj okno nowego projektu z nazwą projektu, lokalizacją i polami nazw rozwiązań":::

1. W oknie dialogowym **Informacje dodatkowe** wybierz pozycję **.NET 5,0 (bieżące)**, a następnie wybierz pozycję **Utwórz**.

   :::image type="content" source="media/with-visual-studio/additional-info.png" alt-text="Okno dialogowe informacji dodatkowych":::

Szablon tworzy prostą aplikację "Hello world". Wywołuje metodę, <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> Aby wyświetlić "Hello World!" w oknie konsoli.

Kod szablonu definiuje klasę, `Program` przy użyciu pojedynczej metody, `Main` która przyjmuje <xref:System.String> tablicę jako argument:

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

```vb
Imports System

Module Program
    Sub Main(args As String())
        Console.WriteLine("Hello World!")
    End Sub
End Module
```

`Main` jest punktem wejścia aplikacji, metoda, która jest wywoływana automatycznie przez środowisko uruchomieniowe podczas uruchamiania aplikacji. Wszystkie argumenty wiersza polecenia dostarczone podczas uruchamiania aplikacji są dostępne w tablicy *args* .

Jeśli język, którego chcesz użyć, nie jest wyświetlany, Zmień selektor języka w górnej części strony.

## <a name="run-the-app"></a>Uruchamianie aplikacji

1. Naciśnij klawisz <kbd>Ctrl</kbd> + <kbd>F5</kbd> , aby uruchomić program bez debugowania.

   Zostanie otwarte okno konsoli z tekstem "Hello world!" Wydrukowano na ekranie.

   :::image type="content" source="./media/with-visual-studio/hello-world-console.png" alt-text="Okno konsoli z pokazanymi Hello world naciśnij dowolny klawisz, aby kontynuować":::

1. Naciśnij dowolny klawisz, aby zamknąć okno konsoli.

## <a name="enhance-the-app"></a>Ulepszanie aplikacji

Podnieś poziom aplikacji, aby monitować użytkownika o jego nazwę i wyświetlić go wraz z datą i godziną.

1. W programie *program.cs* lub *program. vb* Zastąp zawartość `Main` metody, która jest wierszem, który wywołuje `Console.WriteLine` , przy użyciu następującego kodu:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::
   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="MainMethod":::

   Ten kod wyświetla monit w oknie konsoli i czeka, aż użytkownik wprowadzi ciąg, a następnie klawisz <kbd>Enter</kbd> . Ten ciąg jest przechowywany w zmiennej o nazwie `name` . Pobiera również wartość <xref:System.DateTime.Now?displayProperty=nameWithType> właściwości, która zawiera bieżący czas lokalny i przypisuje go do zmiennej o nazwie `date` ( `currentDate` w Visual Basic). I wyświetla te wartości w oknie konsoli. Na koniec wyświetla monit w oknie konsoli i wywołuje <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> metodę, aby czekać na dane wejściowe użytkownika.

   `\n`( `vbCrLf` W Visual Basic) reprezentuje znak nowego wiersza.

   Znak dolara ( `$` ) przed ciągiem umożliwia umieszczenie wyrażeń takich jak nazwy zmiennych w nawiasach klamrowych w ciągu. Wartość wyrażenia jest wstawiana do ciągu zamiast wyrażenia. Ta składnia jest określana mianem [ciągów interpolowanych](../../csharp/language-reference/tokens/interpolated.md).

1. Naciśnij klawisz <kbd>Ctrl</kbd> + <kbd>F5</kbd> , aby uruchomić program bez debugowania.

1. Odpowiedz na monit, wprowadzając nazwę i naciskając klawisz <kbd>Enter</kbd> .

   :::image type="content" source="./media/with-visual-studio/hello-world-update.png" alt-text="Okno konsoli ze zmodyfikowanym wyjściem programu":::

1. Naciśnij dowolny klawisz, aby zamknąć okno konsoli.

## <a name="additional-resources"></a>Zasoby dodatkowe

- [Bieżące wersje i wersje długoterminowe pomocy technicznej](../releases-and-support.md#net-core-and-net-5-version-lifecycles)

## <a name="next-steps"></a>Następne kroki

W tym samouczku utworzono aplikację konsolową .NET. W następnym samouczku debugujesz aplikację.

> [!div class="nextstepaction"]
> [Debugowanie aplikacji konsolowej .NET przy użyciu programu Visual Studio](debugging-with-visual-studio.md)
