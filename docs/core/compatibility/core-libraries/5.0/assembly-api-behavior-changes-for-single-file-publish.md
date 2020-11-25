---
title: 'Istotna zmiana: zmiany zachowania interfejsu API związane z zestawem dla formatu publikowania pojedynczego pliku'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których wiele interfejsów API związanych z lokalizacją pliku zestawu ma zmiany zachowania, gdy są wywoływane w formacie publikowania pojedynczego pliku.
ms.date: 11/01/2020
ms.openlocfilehash: d77e30318040c8298065073a41caab56f2ca3875
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761528"
---
# <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a>Zmiany zachowania interfejsu API związane z zestawem dla formatu publikowania pojedynczego pliku

Wiele interfejsów API związanych z lokalizacją pliku zestawu ma zmiany zachowania, gdy są wywoływane w formacie publikowania pojedynczego pliku.

## <a name="change-description"></a>Zmień opis

W przypadku publikowania jednoplikowego dla programu .NET 5,0 i nowszych wersji zestawy powiązane są ładowane z pamięci zamiast wyodrębniane na dysk. W przypadku aplikacji publikowanych jednoplikowo oznacza to, że niektóre interfejsy API powiązane z lokalizacją zwracają różne wartości na platformie .NET 5,0 i nowszych niż w poprzednich wersjach programu .NET. Zmiany są następujące:

| Interfejs API | Poprzednie wersje | .NET 5,0 i nowsze |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | Zwraca wyodrębnioną ścieżkę pliku DLL | Zwraca pusty ciąg dla zestawów w pakiecie |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | Zwraca wyodrębnioną ścieżkę pliku DLL | Zgłasza wyjątek dla zestawów w pakiecie |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | Zwraca `null` dla zestawów w pakiecie | Zgłasza wyjątek dla zestawów w pakiecie |
| `Environment.GetCommandLineArgs()[0]` | Wartość to nazwa biblioteki DLL punktu wejścia | Wartość jest nazwą pliku wykonywalnego hosta |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | Wartość jest katalogiem tymczasowym wyodrębniania | Wartość jest katalogiem zawierającym plik wykonywalny hosta |

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

Należy unikać zależności między lokalizacją pliku zestawów podczas publikowania jako pojedynczy plik.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
