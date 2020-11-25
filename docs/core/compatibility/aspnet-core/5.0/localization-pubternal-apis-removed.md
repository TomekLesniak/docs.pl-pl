---
title: 'Zmiana podziału: Usunięto interfejsy API Pubternal'
description: Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0, gdzie zostały usunięte niektóre interfejsy API lokalizacji pubternal
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: ae647d66b716175536edb3c978b027ebb7d3ddac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761407"
---
# <a name="localization-pubternal-apis-removed"></a>Lokalizacja: Usunięto interfejsy API "Pubternal"

Aby lepiej zachować powierzchnię publicznego interfejsu API ASP.NET Core, niektóre :::no-loc text="\"pubternal\""::: interfejsy API lokalizacji zostały usunięte. :::no-loc text="\"pubternal\"":::Interfejs API ma `public` modyfikator dostępu i jest zdefiniowany w przestrzeni nazw, która oznacza przeznaczenie [wewnętrzne](../../../../csharp/language-reference/keywords/internal.md) .

Aby zapoznać się z omówieniem, zobacz [dotnet/aspnetcore # 22291](https://github.com/dotnet/aspnetcore/issues/22291).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 6

## <a name="old-behavior"></a>Stare zachowanie

Następujące interfejsy API `public` :

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` przeciążenia konstruktora akceptujące jeden z następujących typów parametrów:
  - `AssemblyWrapper`
  - `IResourceStringProvider`

## <a name="new-behavior"></a>Nowe zachowanie

Na poniższej liście przedstawiono zmiany:

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper` stała `Microsoft.Extensions.Localization.AssemblyWrapper` się i jest teraz `internal` .
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` stała `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` się i jest teraz `internal` .
- `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` przeciążenia konstruktora akceptujące jeden z następujących typów parametrów są teraz `internal` :
  - `AssemblyWrapper`
  - `IResourceStringProvider`

## <a name="reason-for-change"></a>Przyczyna zmiany

Wyjaśniono dokładniej dla [ASPNET/anonsów # 377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: typy zostały usunięte z `public` powierzchni interfejsu API. Te zmiany dostosowują więcej klas do tej decyzji projektowej. Omawiane klasy były przeznaczone jako punkty rozszerzenia dla wewnętrznego testowania zespołu.

## <a name="recommended-action"></a>Zalecana akcja

Chociaż jest to mało prawdopodobne, niektóre aplikacje mogą celowo lub przypadkowo zależeć od :::no-loc text="\"pubternal\""::: typów. Zapoznaj się z nowymi sekcjami [zachowania](#new-behavior) , aby określić, jak przeprowadzić migrację z typów.

W przypadku zidentyfikowania scenariusza, który publiczny interfejs API jest dozwolony przed tą zmianą, ale nie teraz, należy rozwiązać problem w programie [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).

## <a name="affected-apis"></a>Dotyczy interfejsów API

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
