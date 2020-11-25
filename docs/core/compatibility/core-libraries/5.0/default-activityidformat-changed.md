---
title: 'Zmiana podziału: wartość domyślna ActivityIdFormat jest W3C'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w podstawowych bibliotekach platformy .NET, w których domyślnym ActivityIdFormat jest teraz W3C.
ms.date: 11/01/2020
ms.openlocfilehash: 77ee705ac18065c84ddeab3127e01b6a40c3b84d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761560"
---
# <a name="default-activityidformat-is-w3c"></a>ActivityIdFormat domyślny to W3C

Domyślny format identyfikatora dla działania ( <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> ) to teraz <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType> .

## <a name="change-description"></a>Zmień opis

Format identyfikatora działania W3C został wprowadzony w programie .NET Core 3,0 jako alternatywa dla formatu identyfikatora hierarchicznego. Jednak w celu zachowania zgodności format W3C nie został wprowadzony domyślnie do programu .NET 5,0. Wartość domyślna została zmieniona w programie .NET 5,0, ponieważ [format W3C został ratyfikowany](https://www.w3.org/TR/trace-context/) i uzyskano trakcję w wielu implementacjach języka.

Jeśli aplikacja jest przeznaczona na platformę inną niż .NET 5,0 lub nowsza, środowisko będzie miało stare zachowanie, gdzie <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> jest formatem domyślnym. Ta wartość domyślna dotyczy platform net45 +, standard 1.1 + i netcoreapp (1. x, 2. x i 3. x). W programie .NET 5,0 i nowszych <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> jest ustawiona na <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType> .

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

Jeśli aplikacja jest niezależny od do identyfikatora, który jest używany na potrzeby śledzenia rozproszonego, nie jest wymagana żadna akcja. Biblioteki, takie jak ASP.NET Core i <xref:System.Net.Http.HttpClient> mogą zużywać lub propagować obie wersje programu <xref:System.Diagnostics.ActivityIdFormat> .

Jeśli wymagane jest współdziałanie z istniejącymi systemami lub bieżące systemy korzystają z formatu identyfikatora, można zachować stare zachowanie przez ustawienie wartości <xref:System.Diagnostics.Activity.DefaultIdFormat> <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType> . Alternatywnie można ustawić przełącznik AppContext na jeden z trzech sposobów:

- W pliku projektu.

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- W *runtimeconfig.js* pliku.

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- Za przy użyciu zmiennej środowiskowej.

  Ustaw `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` wartość `true` lub 1.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
