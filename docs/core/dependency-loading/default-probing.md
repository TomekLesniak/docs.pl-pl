---
title: Domyślna sondowanie — .NET Core
description: Omówienie elementu System. Runtime. Loader. AssemblyLoadContext. default sondowania w celu lokalizowania zależności.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 13ce4c7de5f6ce1b76b2e61db810c0f19717540f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608415"
---
# <a name="default-probing"></a>Domyślna sonda

<xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>Wystąpienie jest odpowiedzialne za lokalizowanie zależności zestawu. W tym artykule opisano <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> logikę sondowania wystąpienia.

## <a name="host-configured-probing-properties"></a>Host skonfigurował właściwości sondowania

Po uruchomieniu środowiska uruchomieniowego host środowiska uruchomieniowego udostępnia zestaw nazwanych właściwości, które konfigurują <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> ścieżki sondy.

Każda właściwość sondowania jest opcjonalna. Jeśli jest obecny, Każda właściwość jest wartością ciągu, która zawiera rozdzielaną listę ścieżek bezwzględnych. Ogranicznik to ";" w systemie Windows i ":" na wszystkich innych platformach.

|Nazwa właściwości                 |Opis  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | Lista ścieżek plików zestawu platformy i aplikacji. |
|`PLATFORM_RESOURCE_ROOTS`       | Lista ścieżek katalogów do wyszukiwania zestawów zasobów satelity. |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | Lista ścieżek katalogów do wyszukiwania niezarządzanych (natywnych) bibliotek.        |
|`APP_PATHS`                     | Lista ścieżek katalogów do wyszukiwania zestawów zarządzanych. |
|`APP_NI_PATHS`                  | Lista ścieżek katalogów do wyszukiwania natywnych obrazów zestawów zarządzanych. |

### <a name="how-are-the-properties-populated"></a>Jak są wypełniane właściwości?

Istnieją dwa główne scenariusze wypełniania właściwości w zależności od tego, czy * \<myapp>.deps.jsw* pliku istnieje.

- Gdy * \*.deps.jsw* pliku jest obecny, jest analizowany w celu wypełnienia właściwości sondowania.
- Gdy * \*.deps.jsw* pliku nie istnieje, zakłada się, że katalog aplikacji zawiera wszystkie zależności. Zawartość katalogu służy do wypełniania właściwości sondowania.

Ponadto * \*.deps.jsw* plikach dla dowolnych struktur, do których istnieją odwołania, są podobnie analizowane.

Na koniec zmienna środowiskowa `ADDITIONAL_DEPS` może służyć do dodawania dodatkowych zależności.  `dotnet.exe` zawiera również `--additional-deps` opcjonalny parametr, aby ustawić tę wartość przy uruchamianiu aplikacji.

`APP_PATHS`Właściwości i `APP_NI_PATHS` nie są domyślnie wypełniane i pomijane w przypadku większości aplikacji.

Do listy wszystkich * \*.deps.js* plików używanych w aplikacji można uzyskać dostęp za pośrednictwem programu `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")` .

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a>Jak mogę wyświetlić właściwości sondowania z kodu zarządzanego?

Każda właściwość jest dostępna przez wywołanie <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> funkcji z nazwą właściwości z powyższej tabeli.

### <a name="how-do-i-debug-the-probing-properties-construction"></a>Jak mogę debugować konstrukcję właściwości sondowania?

Host środowiska uruchomieniowego platformy .NET Core będzie wyprowadzać przydatne komunikaty śledzenia, gdy są włączone pewne zmienne środowiskowe:

|Zmienna środowiskowa        |Opis  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |Włącza śledzenie.|
|`COREHOST_TRACEFILE=<path>` |Ślady do ścieżki pliku zamiast wartości domyślnej `stderr` .|
|`COREHOST_TRACE_VERBOSITY`  |Ustawia poziom szczegółowości od 1 (najniższy) do 4 (najwyższy).|

## <a name="managed-assembly-default-probing"></a>Domyślna sondowanie zestawu zarządzanego

Podczas sondowania w celu zlokalizowania zestawu zarządzanego <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> wygląd wygląda następująco:

- Pliki pasujące do programu <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> `TRUSTED_PLATFORM_ASSEMBLIES` (po usunięciu rozszerzeń plików).
- Pliki zestawu obrazów natywnych w programie `APP_NI_PATHS` ze wspólnymi rozszerzeniami plików.
- Pliki zestawów w programie `APP_PATHS` ze wspólnymi rozszerzeniami plików.

## <a name="satellite-resource-assembly-probing"></a>Sonda zestawu (zasobów) dla satelity

Aby znaleźć zestaw satelicki dla określonej kultury, należy utworzyć zestaw ścieżek plików.

Dla każdej ścieżki w, `PLATFORM_RESOURCE_ROOTS` a następnie `APP_PATHS` Dołącz <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> ciąg, separator katalogu, <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> ciąg i rozszerzenie ". dll".

Jeśli istnieje odpowiedni plik, spróbuj załadować i zwrócić go.

## <a name="unmanaged-native-library-probing"></a>Badanie biblioteki niezarządzanej (natywnej)

Podczas sondowania w celu zlokalizowania biblioteki niezarządzanej `NATIVE_DLL_SEARCH_DIRECTORIES` są one przeszukiwane w poszukiwaniu zgodnej biblioteki.
