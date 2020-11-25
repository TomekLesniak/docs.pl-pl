---
title: Zrzuty — .NET
description: Wprowadzenie do zrzutów w programie .NET.
ms.date: 10/12/2020
ms.openlocfilehash: a5f12837e81edc82f420f7b325b0248f9f8989a3
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96034832"
---
# <a name="dumps"></a>Zrzuty

Zrzut to plik zawierający migawkę procesu w momencie jego utworzenia i może być przydatny do sprawdzania stanu aplikacji. Zrzuty mogą służyć do debugowania aplikacji .NET, gdy trudno jest dołączyć do niej debuger, taki jak środowisko produkcyjne lub środowiska CI. Użycie zrzutów umożliwia przechwycenie stanu problematycznego procesu i zbadanie go bez konieczności zatrzymywania aplikacji.

## <a name="collect-dumps"></a>Zbieraj zrzuty

Zrzuty mogą być zbierane na różne sposoby w zależności od platformy, w której uruchomiono aplikację.

> [!NOTE]
> Zbieranie zrzutu wewnątrz kontenera wymaga możliwości PTRACE, które można dodać za pośrednictwem `--cap-add=SYS_PTRACE` lub `--privileged` .

> [!NOTE]
> Zrzuty mogą zawierać informacje poufne, ponieważ mogą zawierać pełną pamięć procesu uruchomionego. Obsłuż je wszelkimi ograniczeniami zabezpieczeń i wskazówkami.

### <a name="collecting-dumps-on-crash"></a>Zbieranie zrzutów w przypadku awarii

Możesz użyć zmiennych środowiskowych, aby skonfigurować aplikację do zbierania zrzutu po awarii. Jest to przydatne, gdy chcesz uzyskać informacje o tym, dlaczego wystąpił awaria. Na przykład przechwytywanie zrzutu w przypadku zgłoszenia wyjątku ułatwia zidentyfikowanie problemu przez sprawdzenie stanu aplikacji w przypadku jej awarii.

W poniższej tabeli przedstawiono zmienne środowiskowe, które można skonfigurować w celu zbierania zrzutów po awarii.

|Zmienna środowiskowa|Opis|Wartość domyślna|
|-------|---------|---|
|`COMPlus_DbgEnableMiniDump`|W przypadku ustawienia wartości 1 Włącz generowanie zrzutów podstawowych.|0|
|`COMPlus_DbgMiniDumpType`|Typ zrzutu do zebrania. Aby uzyskać więcej informacji, zobacz poniższą tabelę.|2 ( `MiniDumpWithPrivateReadWriteMemory` )|
|`COMPlus_DbgMiniDumpName`|Ścieżka do pliku, w którym ma zostać zapisany zrzut.|`/tmp/coredump.<pid>`|
|`COMPlus_CreateDumpDiagnostics`|W przypadku ustawienia wartości 1 Włącz rejestrowanie diagnostyczne procesu zrzutu.|0|

W poniższej tabeli przedstawiono wszystkie opcje, których można użyć `COMPlus_DbgMiniDumpType` , dla których można określić jako wartość. Na przykład ustawienie wartość `COMPlus_DbgMiniDumpType` 1 oznacza `MiniDumpNormal` , że zrzut typu będzie zbierany w przypadku awarii.

|Wartość|Nazwa|Opis|
|-----|----|-----------|
|1|`MiniDumpNormal`|Uwzględnij tylko te informacje, które są niezbędne do przechwytywania śladów stosu dla wszystkich istniejących wątków w procesie. Ograniczona pamięć i informacje dotyczące sterty GC.|
|2|`MiniDumpWithPrivateReadWriteMemory`|Obejmuje sterty GC i informacje niezbędne do przechwytywania śladów stosu dla wszystkich istniejących wątków w procesie.|
|3|`MiniDumpFilterTriage`|Uwzględnij tylko te informacje, które są niezbędne do przechwytywania śladów stosu dla wszystkich istniejących wątków w procesie. Ograniczona pamięć i informacje dotyczące sterty GC.|
|4|`MiniDumpWithFullMemory`|Uwzględnij całą dostępną pamięć w procesie. Dane nieprzetworzonej pamięci są uwzględniane na końcu, aby struktury początkowe można mapować bezpośrednio bez informacji o pamięci nieprzetworzonej. Ta opcja może powodować bardzo duży plik.|

### <a name="collecting-dumps-at-specific-point-in-time"></a>Zbieranie zrzutów w określonym momencie

Może być konieczne zebranie zrzutu, gdy aplikacja nie uległa jeszcze awarii. Na przykład jeśli chcesz przejrzeć stan aplikacji, która wydaje się być zakleszczeniem, skonfigurowanie zmiennych środowiskowych w celu zbierania zrzutów w przypadku awarii nie będzie przydatne, ponieważ aplikacja nadal działa.

Aby zbierać zrzuty we własnym żądaniu, można użyć `dotnet-dump` , który jest narzędziem interfejsu wiersza polecenia do zbierania i analizowania zrzutów. Aby uzyskać więcej informacji na temat zbierania zrzutów za pomocą programu `dotnet-dump` , zobacz [zrzuty narzędzi do zbierania i analizy](dotnet-dump.md).

### <a name="types-of-dumps-in-net"></a>Typy zrzutów w programie .NET

Można zbierać różne typy zrzutów w zależności od przeznaczenia. Można skonfigurować przy użyciu `COMPlus_DbgMiniDumpType` zmiennej środowiskowej when lub `--type` flagi podczas korzystania z programu `dotnet-dump` . W poniższej tabeli przedstawiono typy zrzutów, które można zbierać w programie .NET.

|Wartość|Nazwa|Opis|
|-----|----|-----------|
|1|`MiniDumpNormal`|Uwzględnij tylko te informacje, które są niezbędne do przechwytywania śladów stosu dla wszystkich istniejących wątków w procesie. Ograniczona pamięć i informacje dotyczące sterty GC.|
|2|`MiniDumpWithPrivateReadWriteMemory`|Obejmuje sterty GC i informacje niezbędne do przechwytywania śladów stosu dla wszystkich istniejących wątków w procesie.|
|3|`MiniDumpFilterTriage`|Uwzględnij tylko te informacje, które są niezbędne do przechwytywania śladów stosu dla wszystkich istniejących wątków w procesie. Ograniczona pamięć i informacje dotyczące sterty GC.|
|4|`MiniDumpWithFullMemory`|Uwzględnij całą dostępną pamięć w procesie. Dane nieprzetworzonej pamięci są uwzględniane na końcu, aby struktury początkowe można mapować bezpośrednio bez informacji o pamięci nieprzetworzonej. Ta opcja może powodować bardzo duży plik.|

## <a name="analyze-dumps"></a>Analizowanie zrzutów

Zrzuty mogą być analizowane przy użyciu [`dotnet-dump`](dotnet-dump.md) .

## <a name="see-also"></a>Zobacz także

Dowiedz się więcej o tym, jak można wykorzystać zrzuty, aby pomóc w diagnozowaniu problemów w aplikacji .NET.

* Samouczek dotyczący [debugowania zrzutów systemu Linux](debug-linux-dumps.md) przeprowadzi Cię przez proces debugowania zrzutu, który został zebrany w systemie Linux.

* Samouczek [debugowania](debug-deadlock.md) — przeprowadzi Cię przez proces debugowania zakleszczenia w aplikacji .NET przy użyciu zrzutów.
