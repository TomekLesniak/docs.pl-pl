---
title: Publikowanie aplikacji konsolowej .NET przy użyciu programu Visual Studio
description: Dowiedz się, jak za pomocą programu Visual Studio utworzyć zestaw plików, które są konieczne do uruchomienia aplikacji platformy .NET.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: b0c6bd85ddf86f0eb11c56f01abb74a7e9786363
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916032"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio"></a>Samouczek: publikowanie aplikacji konsolowej .NET przy użyciu programu Visual Studio

W tym samouczku pokazano, jak opublikować aplikację konsolową, tak aby inni użytkownicy mogli ją uruchomić. Publikowanie tworzy zestaw plików, które są konieczne do uruchomienia aplikacji. Aby wdrożyć pliki, skopiuj je na maszynę docelową.

## <a name="prerequisites"></a>Wymagania wstępne

- Ten samouczek współpracuje z aplikacją konsolową utworzoną w temacie [Tworzenie aplikacji konsolowej platformy .NET przy użyciu programu Visual Studio](with-visual-studio.md).

## <a name="publish-the-app"></a>Publikowanie aplikacji

1. Uruchom program Visual Studio.

1. Otwórz projekt *HelloWorld* , który został utworzony w temacie [Tworzenie aplikacji konsolowej platformy .NET przy użyciu programu Visual Studio](with-visual-studio.md).

1. Upewnij się, że program Visual Studio używa konfiguracji kompilacji wydania. W razie potrzeby zmień ustawienie konfiguracji kompilacji na pasku narzędzi z **Debuguj** na **Release**.

   :::image type="content" source="media/publishing-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Program Visual Studio Toolbar z wybraną kompilacją wydania":::

1. Kliknij prawym przyciskiem myszy projekt **HelloWorld** (nie rozwiązanie HelloWorld) i wybierz polecenie **Publikuj** z menu.

   :::image type="content" source="media/publishing-with-visual-studio/publish-context-menu.png" alt-text="Menu kontekstowe publikacji programu Visual Studio":::

1. Na karcie **Target** strony **Publikowanie** wybierz pozycję **folder**, a następnie wybierz pozycję **dalej**.

   :::image type="content" source="media/publishing-with-visual-studio/pick-publish-target.png" alt-text="Wybieranie elementu docelowego publikowania w programie Visual Studio":::

1. Na karcie **określony cel** strony **Publikowanie** wybierz pozycję **folder**, a następnie wybierz pozycję **dalej**.

   :::image type="content" source="media/publishing-with-visual-studio/pick-specific-publish-target.png" alt-text="Wybieranie określonego docelowego publikowania w programie Visual Studio":::

1. Na karcie **Lokalizacja** strony **Publikowanie** wybierz pozycję **Zakończ**.

   :::image type="content" source="media/publishing-with-visual-studio/publish-page-loc-tab.png" alt-text="Karta Lokalizacja strony publikacji programu Visual Studio":::

1. Na karcie **Publikowanie** okna **Publikowanie** wybierz pozycję **Publikuj**.

   :::image type="content" source="media/publishing-with-visual-studio/publish-page.png" alt-text="Okno publikowania programu Visual Studio":::

## <a name="inspect-the-files"></a>Inspekcja plików

Domyślnie proces publikowania tworzy wdrożenie zależne od platformy, które jest typem wdrożenia, w którym jest uruchomiona opublikowana aplikacja na komputerze z zainstalowanym środowiskiem uruchomieniowym platformy .NET. Użytkownicy mogą uruchamiać opublikowaną aplikację przez dwukrotne kliknięcie pliku wykonywalnego lub wydawanie `dotnet HelloWorld.dll` polecenia z wiersza polecenia.

W poniższych krokach zawarto Podgląd plików utworzonych przez proces publikowania.

1. W **Eksplorator rozwiązań** wybierz opcję **Pokaż wszystkie pliki**.

1. W folderze projektu rozwiń węzeł *bin/Release/NET 5.0/Publikuj*.

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Eksplorator rozwiązań wyświetlania opublikowanych plików":::

   W miarę wyświetlania obrazu opublikowane dane wyjściowe zawierają następujące pliki:

   * *HelloWorld.deps.jsna*

      Jest to plik zależności środowiska uruchomieniowego aplikacji. Definiuje składniki platformy .NET i biblioteki (w tym bibliotekę dołączaną dynamicznie, która zawiera aplikację) potrzebną do uruchomienia aplikacji. Aby uzyskać więcej informacji, zobacz [pliki konfiguracji środowiska uruchomieniowego](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

   * *HelloWorld.dll*

      Jest to [zależna od platformy wersja wdrożenia](../deploying/deploy-with-cli.md#framework-dependent-deployment) aplikacji. Aby wykonać tę bibliotekę dołączaną dynamicznie, wprowadź `dotnet HelloWorld.dll` w wierszu polecenia. Ta metoda uruchamiania aplikacji działa na dowolnej platformie, na której zainstalowano środowisko uruchomieniowe platformy .NET.

   * *HelloWorld.exe*

      Jest to [zależna od struktury wersja pliku wykonywalnego](../deploying/deploy-with-cli.md#framework-dependent-executable) aplikacji. Aby uruchomić tę opcję, wprowadź `HelloWorld.exe` w wierszu polecenia. Plik działa w systemie operacyjnym.

   * *HelloWorld. pdb* (opcjonalnie dla wdrożenia)

      Jest to plik symboli debugowania. Nie musisz wdrażać tego pliku wraz z aplikacją, chociaż należy je zapisać w zdarzeniu, które trzeba debugować opublikowaną wersję aplikacji.

   * *HelloWorld.runtimeconfig.jsna*

      To jest plik konfiguracji czasu wykonywania aplikacji. Identyfikuje wersję platformy .NET, w której aplikacja została skompilowana. Możesz również dodać do niej opcje konfiguracji. Aby uzyskać więcej informacji, zobacz [Ustawienia konfiguracji środowiska uruchomieniowego .NET](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Uruchom opublikowaną aplikację

1. W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy folder *Publikowanie* , a następnie wybierz polecenie **Kopiuj pełną ścieżkę**.

1. Otwórz wiersz polecenia i przejdź do folderu *Publikowanie* . W tym celu wprowadź, `cd` a następnie wklej pełną ścieżkę. Przykład:

   ```console
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. Uruchom aplikację przy użyciu pliku wykonywalnego:

   1. Wprowadź `HelloWorld.exe` i naciśnij klawisz <kbd>Enter</kbd>.

   1. Wprowadź nazwę w odpowiedzi na monit, a następnie naciśnij dowolny klawisz, aby wyjść.

1. Uruchom aplikację za pomocą `dotnet` polecenia:

   1. Wprowadź `dotnet HelloWorld.dll` i naciśnij klawisz <kbd>Enter</kbd>.

   1. Wprowadź nazwę w odpowiedzi na monit, a następnie naciśnij dowolny klawisz, aby wyjść.

## <a name="additional-resources"></a>Zasoby dodatkowe

- [Wdrażanie aplikacji .NET](../deploying/index.md)

## <a name="next-steps"></a>Następne kroki

W tym samouczku opublikowano aplikację konsolową. W następnym samouczku utworzysz bibliotekę klas.

> [!div class="nextstepaction"]
> [Tworzenie biblioteki klas .NET przy użyciu programu Visual Studio](library-with-visual-studio.md)
