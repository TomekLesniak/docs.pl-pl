---
title: Publikowanie aplikacji konsolowej .NET przy użyciu Visual Studio Code
description: Dowiedz się, jak używać Visual Studio Code i interfejsu wiersza polecenia platformy .NET do tworzenia zestawu plików, które są konieczne do uruchomienia aplikacji platformy .NET.
ms.date: 11/17/2020
ms.openlocfilehash: 9cfe490203d2d3254103ad2f0a4c4ff74972ec64
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915892"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio-code"></a>Samouczek: publikowanie aplikacji konsolowej .NET przy użyciu Visual Studio Code

W tym samouczku pokazano, jak opublikować aplikację konsolową, tak aby inni użytkownicy mogli ją uruchomić. Publikowanie tworzy zestaw plików, które są konieczne do uruchomienia aplikacji. Aby wdrożyć pliki, skopiuj je na maszynę docelową.

Interfejs wiersza polecenia platformy .NET jest używany do publikowania aplikacji, więc możesz wykonać czynności opisane w tym samouczku z edytorem kodu innym niż Visual Studio Code, jeśli wolisz.

## <a name="prerequisites"></a>Wymagania wstępne

- Ten samouczek współpracuje z aplikacją konsolową utworzoną w temacie [Tworzenie aplikacji konsolowej platformy .NET przy użyciu Visual Studio Code](with-visual-studio-code.md).

## <a name="publish-the-app"></a>Publikowanie aplikacji

1. Uruchom program Visual Studio Code.

1. Otwórz folder projektu *HelloWorld* , który został utworzony w temacie [Tworzenie aplikacji konsolowej platformy .net przy użyciu Visual Studio Code](with-visual-studio-code.md).

1. Wybierz pozycję **Wyświetl**  >  **Terminal** z menu głównego.

   Terminal zostanie otwarty w folderze *HelloWorld* .

1. Uruchom następujące polecenie:

   ```dotnetcli
   dotnet publish --configuration Release
   ```

   Domyślną konfiguracją kompilacji jest *debugowanie*, dlatego to polecenie określa konfigurację kompilacji *wydania* . Dane wyjściowe z konfiguracji kompilacji wydania zawierają minimalne informacje dotyczące debugowania symbolicznego i są w pełni zoptymalizowane.

   Dane wyjściowe polecenia są podobne do poniższego przykładu:

   ```output
   Microsoft (R) Build Engine version 16.7.0+b89cb5fde for .NET
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\HelloWorld.dll
     HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

## <a name="inspect-the-files"></a>Inspekcja plików

Domyślnie proces publikowania tworzy wdrożenie zależne od platformy, które jest typem wdrożenia, gdzie opublikowana aplikacja jest uruchamiana na komputerze, na którym zainstalowano środowisko uruchomieniowe platformy .NET. Aby uruchomić opublikowaną aplikację, można użyć pliku wykonywalnego lub uruchomić `dotnet HelloWorld.dll` polecenie z wiersza polecenia.

W poniższych krokach zawarto Podgląd plików utworzonych przez proces publikowania.

1. Wybierz **Eksploratora** na lewym pasku nawigacyjnym.

1. Rozwiń gałąź *bin/Release/NET 5.0/Publikuj*.

   :::image type="content" source="media/publishing-with-visual-studio-code/published-files-output.png" alt-text="Eksplorator przedstawiający opublikowane pliki":::

   W miarę wyświetlania obrazu opublikowane dane wyjściowe zawierają następujące pliki:

   * *HelloWorld.deps.jsna*

      Jest to plik zależności środowiska uruchomieniowego aplikacji. Definiuje składniki platformy .NET i biblioteki (w tym bibliotekę dołączaną dynamicznie, która zawiera aplikację) potrzebną do uruchomienia aplikacji. Aby uzyskać więcej informacji, zobacz [pliki konfiguracji środowiska uruchomieniowego](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

   * *HelloWorld.dll*

      Jest to [zależna od platformy wersja wdrożenia](../deploying/deploy-with-cli.md#framework-dependent-deployment) aplikacji. Aby wykonać tę bibliotekę dołączaną dynamicznie, wprowadź `dotnet HelloWorld.dll` w wierszu polecenia. Ta metoda uruchamiania aplikacji działa na dowolnej platformie, na której zainstalowano środowisko uruchomieniowe platformy .NET.

   * *HelloWorld.exe* (*HelloWorld* w systemie Linux, nie utworzono w witrynie macOS).

      Jest to [zależna od struktury wersja pliku wykonywalnego](../deploying/deploy-with-cli.md#framework-dependent-executable) aplikacji. Plik działa w systemie operacyjnym.

   * *HelloWorld. pdb* (opcjonalnie dla wdrożenia)

      Jest to plik symboli debugowania. Nie musisz wdrażać tego pliku wraz z aplikacją, chociaż należy je zapisać w zdarzeniu, które trzeba debugować opublikowaną wersję aplikacji.

   * *HelloWorld.runtimeconfig.jsna*

      To jest plik konfiguracji czasu wykonywania aplikacji. Identyfikuje wersję platformy .NET, w której aplikacja została skompilowana. Możesz również dodać do niej opcje konfiguracji. Aby uzyskać więcej informacji, zobacz [Ustawienia konfiguracji środowiska uruchomieniowego .NET](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Uruchom opublikowaną aplikację

1. W **Eksploratorze** kliknij prawym przyciskiem myszy folder *Publikowanie* (<kbd>kliknij</kbd>pozycję macOS), a następnie wybierz pozycję **Otwórz w terminalu**.

   :::image type="content" source="media/publishing-with-visual-studio-code/open-in-terminal.png" alt-text="Menu kontekstowe pokazujące otwarty w terminalu":::

1. W systemie Windows lub Linux Uruchom aplikację przy użyciu pliku wykonywalnego.

   1. W systemie Windows wpisz `.\HelloWorld.exe` i naciśnij klawisz <kbd>Enter</kbd>.

   1. W systemie Linux wpisz `./HelloWorld` i naciśnij klawisz <kbd>Enter</kbd>.

   1. Wprowadź nazwę w odpowiedzi na monit, a następnie naciśnij dowolny klawisz, aby wyjść.

1. Na dowolnej platformie Uruchom aplikację za pomocą  [`dotnet`](../tools/dotnet.md) polecenia:

   1. Wprowadź `dotnet HelloWorld.dll` i naciśnij klawisz <kbd>Enter</kbd>.

   1. Wprowadź nazwę w odpowiedzi na monit, a następnie naciśnij dowolny klawisz, aby wyjść.

## <a name="additional-resources"></a>Zasoby dodatkowe

- [Wdrażanie aplikacji .NET](../deploying/index.md)

## <a name="next-steps"></a>Następne kroki

W tym samouczku opublikowano aplikację konsolową. W następnym samouczku utworzysz bibliotekę klas.

> [!div class="nextstepaction"]
> [Tworzenie biblioteki klas .NET przy użyciu Visual Studio Code](library-with-visual-studio-code.md)
