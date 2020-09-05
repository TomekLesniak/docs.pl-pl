---
title: Aplikacja pojedynczego pliku
description: Dowiedz się, co to jest aplikacja z pojedynczym plikiem i dlaczego należy rozważyć użycie tego modelu wdrażania aplikacji.
author: lakshanf
ms.author: lakshanf
ms.date: 08/28/2020
ms.openlocfilehash: 795ea98a9fd9d672b199eb2d9b24151340ef8246
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495800"
---
# <a name="single-file-deployment-and-executable"></a>Wdrożenie pojedynczego pliku i plik wykonywalny

Zgrupowanie wszystkich plików zależnych od aplikacji do jednego pliku binarnego zapewnia deweloperowi aplikacji z opcją atrakcyjną w celu wdrożenia i dystrybucji aplikacji jako pojedynczy plik. Ten model wdrażania został udostępniony od platformy .NET Core 3,0 i został ulepszony w programie .NET 5,0. Wcześniej w programie .NET Core 3,0, gdy użytkownik uruchamia aplikację z jednym plikiem, host .NET Core najpierw wyodrębnia wszystkie pliki do katalogu tymczasowego przed uruchomieniem aplikacji. Program .NET 5,0 podnosi to środowisko, bezpośrednio uruchamiając kod bez konieczności wyodrębniania plików z aplikacji.

Wdrożenie pojedynczego pliku jest dostępne zarówno dla [modelu wdrażania zależnego od platformy](index.md#publish-framework-dependent) , jak i [aplikacji samodzielnych](index.md#publish-self-contained). Rozmiar pojedynczego pliku w aplikacji samodzielnej jest duży, ponieważ będzie obejmował środowisko uruchomieniowe i biblioteki struktury. Opcja wdrożenia pojedynczego pliku może być łączona z [ReadyToRun](../tools/dotnet-publish.md) i [Trim (funkcja eksperymentalna w programie .NET 5,0)](trim-self-contained.md) opcje publikowania.

Istnieją pewne ograniczenia, które należy wziąć pod uwagę przy użyciu pojedynczych plików, przy czym najpierw są używane informacje o ścieżce do lokalizowania plików względem lokalizacji aplikacji. <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>Interfejs API zwróci pusty ciąg, który jest domyślnym zachowaniem dla zestawów ładowanych z pamięci. Kompilator wyświetli ostrzeżenie dla tego interfejsu API w czasie kompilacji, aby poinformować dewelopera o określonym zachowaniu. Jeśli wymagana jest ścieżka do katalogu aplikacji, <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> interfejs API zwróci katalog, w którym znajduje się AppHost (sam pakiet pojedynczego pliku). Zarządzane aplikacje C++ nie są dobrze dopasowane do wdrożenia jednoplikowego i zalecamy zapisanie aplikacji w języku C# w celu zapewnienia zgodności z pojedynczym plikiem.

Pojedynczy plik domyślnie nie obsługuje bibliotek natywnych. W systemie Linux wstępnie łączymy środowisko uruchomieniowe z pakietem i tylko biblioteki natywne aplikacji są wdrażane w tym samym katalogu, w którym znajduje się aplikacja Jednoplikowa. W systemie Windows połączymy tylko kod hostingu, a biblioteki natywne środowiska uruchomieniowego i aplikacji są wdrażane w tym samym katalogu, w którym znajduje się aplikacja pojedynczego pliku. Jest to konieczne w celu zapewnienia dobrego środowiska debugowania, które wymaga wykluczenia plików natywnych z pojedynczego pliku. Istnieje możliwość ustawienia flagi, `IncludeNativeLibrariesForSelfExtract` Aby uwzględnić biblioteki natywne w pojedynczym zbiorze plików, ale te pliki zostaną wyodrębnione do katalogu tymczasowego na komputerze klienckim po uruchomieniu aplikacji pojedynczego pliku.

## <a name="exclude-files-from-being-embedded"></a>Wykluczanie plików z osadzania

Niektóre pliki można jawnie wykluczyć z osadzania w pojedynczym pliku przez ustawienie następujących metadanych:

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

Na przykład w celu umieszczenia niektórych plików w katalogu publikowania, ale nie są one powiązane z pojedynczym plikiem:

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="publish-a-single-file-app---cli"></a>Publikowanie pojedynczego pliku aplikacji — interfejs wiersza polecenia

Opublikuj aplikację pojedynczego pliku przy użyciu polecenia [dotnet Publish](../tools/dotnet-publish.md) . Po opublikowaniu aplikacji ustaw następujące właściwości:

- Publikuj dla określonego środowiska uruchomieniowego: `-r win-x64`
- Publikuj jako pojedynczy plik: `-p:PublishSingleFile=true`

W poniższym przykładzie jest publikowana aplikacja dla systemu Windows jako samodzielna aplikacja pojedynczego pliku.

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

Poniższy przykład umożliwia opublikowanie aplikacji dla systemu Linux jako zależnej od struktury aplikacji pojedynczego pliku.

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).

## <a name="publish-a-single-file-app---visual-studio"></a>Publikowanie aplikacji pojedynczego pliku — Visual Studio

Program Visual Studio tworzy Profile publikowania wielokrotnego użytku, które kontrolują sposób publikowania aplikacji.

01. W okienku **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt, który chcesz opublikować. Kliknij pozycję **Opublikuj**.

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="Eksplorator rozwiązań z menu po kliknięciu prawym przyciskiem myszy wyróżnianie opcji Publikuj.":::

    Jeśli nie masz jeszcze profilu publikowania, postępuj zgodnie z instrukcjami, aby utworzyć jeden, i wybierz typ docelowy **folderu** .

01. Wybierz pozycję **Edytuj**.

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Profil publikacji programu Visual Studio za pomocą przycisku Edytuj.":::

01. W oknie dialogowym **Ustawienia profilu** ustaw następujące opcje:

    - Ustaw **Tryb wdrożenia** na **własny**.
    - Ustaw **docelowy środowisko uruchomieniowe** na platformę, w której chcesz publikować.
    - Wybierz pozycję **Wygeneruj pojedynczy plik**.

    Wybierz pozycję **Zapisz** , aby zapisać ustawienia i powrócić do okna dialogowego **Publikowanie** .

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="Okno dialogowe ustawień profilu z trybem wdrożenia, docelowym środowiskiem uruchomieniowym i opcją pojedynczego pliku.":::

01. Wybierz pozycję **Publikuj** , aby opublikować aplikację jako pojedynczy plik.

Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą programu Visual Studio](deploy-with-vs.md).

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a>Publikowanie aplikacji pojedynczego pliku — Visual Studio dla komputerów Mac

Visual Studio dla komputerów Mac nie udostępnia opcji publikowania aplikacji jako pojedynczego pliku. Należy opublikować ręcznie, postępując zgodnie z instrukcjami zawartymi w sekcji [Publikowanie pojedynczego pliku App-CLI](#publish-a-single-file-app---cli) . Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).

## <a name="see-also"></a>Zobacz także

- [Wdrażanie aplikacji .NET Core](index.md).
- [Publikowanie aplikacji platformy .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).
- [Publikowanie aplikacji platformy .NET Core w programie Visual Studio](deploy-with-vs.md).
- [ `dotnet publish` polecenie](../tools/dotnet-publish.md).
