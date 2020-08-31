---
title: Przycinanie aplikacji samodzielnych
description: Dowiedz się, jak przyciąć aplikacje samodzielne w celu zmniejszenia ich rozmiaru. Platforma .NET Core udostępnia pakiet środowiska uruchomieniowego z aplikacją, która jest publikowana w sposób niezależny i ogólnie zawiera więcej informacji o środowisku uruchomieniowym.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: 7a4731e2cbaa3835e6aa6ba558dfa8cd03828e01
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053110"
---
# <a name="trim-self-contained-deployments-and-executables"></a>Przycinanie samodzielnych wdrożeń i plików wykonywalnych

[Model wdrożenia zależny od platformy](index.md#publish-framework-dependent) był najbardziej pomyślnym modelem wdrożenia od momentu rozpoczęcia działania programu .NET. W tym scenariuszu Deweloper aplikacji korzysta tylko z aplikacji i zestawów innych firm z oczekiwaniami, gdy środowisko uruchomieniowe platformy .NET i biblioteki struktury będą dostępne na komputerze klienckim. Ten model wdrażania jest nadal jedynym podmiotem w programie .NET Core, ale istnieją pewne scenariusze, w których model zależny od struktury nie jest optymalny. Alternatywą jest opublikowanie [aplikacji samodzielnej](index.md#publish-self-contained), w której środowisko uruchomieniowe i struktura platformy .NET Core są powiązane ze sobą wraz z aplikacjami i zestawami innych firm.

Niezależny od przycinania model wdrażania to wyspecjalizowana wersja modelu wdrażania, który jest zoptymalizowany pod kątem zmniejszenia rozmiaru wdrożenia. Minimalizacja rozmiaru wdrożenia jest wymaganiem krytycznym dla niektórych scenariuszy po stronie klienta, takich jak aplikacje Blazor. W zależności od złożoności aplikacji przywoływany jest tylko podzestaw zestawów Framework, a podzestaw kodu w każdym zestawie jest wymagany do uruchomienia aplikacji. Nieużywane części bibliotek są zbędne i mogą być przycinane z spakowanej aplikacji.

Istnieje jednak ryzyko, że analiza czasu kompilacji aplikacji może spowodować błędy w czasie wykonywania, ze względu na to, że nie jest możliwe niezawodne analizowanie różnych niezawodnych wzorców kodu (w przeważającej mierze przy użyciu odbicia). Ponieważ niezawodności nie można zagwarantować, ten model wdrażania jest oferowany jako funkcja w wersji zapoznawczej.

Aparat analizy czasu kompilacji zawiera ostrzeżenia dla deweloperów wzorców kodu, które są problemmatic do wykrywania, który inny kod jest wymagany. Do kodu można dodawać adnotacje z atrybutami, aby poznać element dostosowujący, który ma zostać uwzględniony. Wiele wzorców odbicia można zamienić na generowanie kodu w czasie kompilacji przy użyciu [generatorów źródeł](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md).

Tryb przycinania dla aplikacji jest konfigurowany przy użyciu `TrimMode` Ustawienia. Wartość domyślna to `copyused` i pakiety, do których odwołują się zestawy z aplikacją. Ta `link` wartość jest używana z aplikacjami Webassembly Blazor i przycina nieużywany kod w zestawach. Ostrzeżenia analizy przycinające zapewniają informacje dotyczące wzorców kodu, w których nie było możliwe przeprowadzenie analizy pełnej zależności. Te ostrzeżenia są domyślnie pomijane i można je włączyć, ustawiając flagę `SuppressTrimAnalysisWarnings` na `false` . Aby uzyskać więcej informacji na temat dostępnych opcji przycinania, zobacz [Opcje przycinania](trimming-options.md).

> [!NOTE]
> Przycinanie jest funkcją eksperymentalną w programie .NET Core 3,1, 5,0 i jest dostępna _tylko_ dla aplikacji, które są publikowane samodzielnie.

## <a name="prevent-assemblies-from-being-trimmed"></a>Uniemożliwiaj przycinanie zestawów

Istnieją scenariusze, w których funkcje przycinania nie będą wykrywać odwołań. Na przykład gdy odbicie jest używane w zestawie czasu wykonywania, przez aplikację lub bibliotekę, do której odwołuje się aplikacja, zestaw nie jest bezpośrednio przywoływany. Przycinanie jest nieświadome tych pośrednich odwołań i wykluczają bibliotekę z opublikowanego folderu.

Gdy kod jest pośrednio odwołujący się do zestawu poprzez odbicie, można zapobiec przycinaniu zestawu przy użyciu tego `<TrimmerRootAssembly>` Ustawienia. Poniższy przykład pokazuje, jak zapobiec przycinaniu zestawu o nazwie `System.Security` Assembly:

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a>Przytnij aplikację — interfejs wiersza polecenia

Przytnij aplikację przy użyciu polecenia [dotnet Publish](../tools/dotnet-publish.md) . Po opublikowaniu aplikacji ustaw następujące właściwości:

- Publikuj jako samodzielną aplikację dla określonego środowiska uruchomieniowego: `-r win-x64`
- Włącz przycinanie: `/p:PublishTrimmed=true`

Poniższy przykład publikuje aplikację dla systemu Windows jako samodzielny i przycina dane wyjściowe.

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

Poniższy przykład publikuje aplikację w trybie agresywnego przycinania, w którym nieużywany kod w ramach zestawów zostanie przycięty i włączono ostrzeżenia elementu dostosowującego.

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</PropertyGroup>
```

Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).

## <a name="trim-your-app---visual-studio"></a>Przycinanie aplikacji — Visual Studio

Program Visual Studio tworzy Profile publikowania wielokrotnego użytku, które kontrolują sposób publikowania aplikacji.

01. W okienku **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt, który chcesz opublikować. Wybierz pozycję **Publikuj...**.

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Eksplorator rozwiązań z menu po kliknięciu prawym przyciskiem myszy wyróżnianie opcji Publikuj.":::

    Jeśli nie masz jeszcze profilu publikowania, postępuj zgodnie z instrukcjami, aby utworzyć jeden, i wybierz typ docelowy **folderu** .

01. Wybierz pozycję **Edytuj**.

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Profil publikacji programu Visual Studio za pomocą przycisku Edytuj.":::

01. W oknie dialogowym **Ustawienia profilu** ustaw następujące opcje:

    - Ustaw **Tryb wdrożenia** na **własny**.
    - Ustaw **docelowy środowisko uruchomieniowe** na platformę, w której chcesz publikować.
    - Wybierz pozycję **Przytnij nieużywane zestawy (w wersji zapoznawczej)**.

    Wybierz pozycję **Zapisz** , aby zapisać ustawienia i powrócić do okna dialogowego **Publikowanie** .

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Opcje okna dialogowego Ustawienia profilu z trybem wdrożenia, cel środowiska uruchomieniowego i nieużywane Zestawy przycinania.":::

01. Wybierz pozycję **Publikuj** , aby opublikować aplikację przycięty.

Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą programu Visual Studio](deploy-with-vs.md).

## <a name="trim-your-app---visual-studio-for-mac"></a>Przytnij aplikację — Visual Studio dla komputerów Mac

Visual Studio dla komputerów Mac nie udostępnia opcji przycinania aplikacji podczas publikowania. Należy opublikować ręcznie, postępując zgodnie z instrukcjami podanymi w sekcji [Trim The App-CLI](#trim-your-app---cli) . Aby uzyskać więcej informacji, zobacz [publikowanie aplikacji .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).

## <a name="see-also"></a>Zobacz też

- [Wdrażanie aplikacji .NET Core](index.md).
- [Publikowanie aplikacji platformy .NET Core za pomocą interfejs wiersza polecenia platformy .NET Core](deploy-with-cli.md).
- [Publikowanie aplikacji platformy .NET Core w programie Visual Studio](deploy-with-vs.md).
- [dotnet Publish polecenie](../tools/dotnet-publish.md).
