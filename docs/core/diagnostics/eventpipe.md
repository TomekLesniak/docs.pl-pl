---
title: EventPipe — Omówienie
description: Dowiedz się więcej o EventPipe i sposobach ich używania do śledzenia aplikacji .NET w celu diagnozowania problemów z wydajnością.
ms.date: 11/09/2020
ms.topic: overview
ms.openlocfilehash: d30cdf02c3ae300401febe2078dfd3431269c73e
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688574"
---
# <a name="eventpipe"></a>EventPipe

EventPipe to składnik środowiska uruchomieniowego, który może służyć do zbierania danych śledzenia, podobnie jak ETW lub LTTng. Celem EventPipe jest umożliwienie deweloperom platformy .NET śledzenia aplikacji platformy .NET bez konieczności polegania na specyficznych dla platformy systemach operacyjnych, takich jak ETW lub LTTng.

EventPipe jest mechanizmem za wiele narzędzi diagnostycznych i może służyć do konsumowania zdarzeń emitowanych przez środowisko uruchomieniowe oraz niestandardowych zdarzeń zapisanych przy użyciu elementu [EventSource](xref:System.Diagnostics.Tracing.EventSource).

Ten artykuł zawiera ogólne omówienie EventPipe opisujące, kiedy i jak używać EventPipe oraz jak skonfigurować go do własnych potrzeb.

## <a name="eventpipe-basics"></a>EventPipe — podstawy

EventPipe agreguje zdarzenia emitowane przez składniki środowiska uruchomieniowego — na przykład kompilator just in Time lub moduł wyrzucania elementów bezużytecznych, a także zdarzenia zapisywane z wystąpień elementu [EventSource](xref:System.Diagnostics.Tracing.EventSource) w bibliotekach i kodzie użytkownika.

Zdarzenia są następnie serializowane i mogą być zapisywane bezpośrednio do pliku lub używane przez port diagnostyki z zewnątrz. W systemie Windows porty diagnostyczne są implementowane jako `NamedPipe` s. Na platformach innych niż Windows, takich jak Linux lub macOS, są implementowane przy użyciu gniazd domen systemu UNIX. Aby uzyskać więcej informacji o porcie diagnostyki i sposobach współpracy z nim za pośrednictwem niestandardowego protokołu komunikacji między procesami, zapoznaj się z [dokumentacją dotyczącą protokołu IPC](https://github.com/dotnet/diagnostics/blob/master/documentation/design-docs/ipc-protocol.md).

EventPipe następnie zapisuje serializowane zdarzenia w `.nettrace` formacie pliku jako strumień za pośrednictwem portów diagnostycznych lub bezpośrednio do pliku. Aby dowiedzieć się więcej o formacie serializacji EventPipe, zapoznaj się z [dokumentacją w formacie EventPipe](https://github.com/microsoft/perfview/blob/master/src/TraceEvent/EventPipe/EventPipeFormat.md).

## <a name="eventpipe-vs-etwlttng"></a>EventPipe a ETW/LTTng

EventPipe jest częścią środowiska uruchomieniowego .NET (CoreCLR) i jest zaprojektowana tak, aby działała w ten sam sposób na wszystkich platformach obsługiwanych przez platformę .NET Core. Pozwala to na używanie narzędzi śledzenia opartych na EventPipe, takich jak `dotnet-counters` , `dotnet-gcdump` i `dotnet-trace` , w celu bezproblemowego działania między platformami.

Jednak ponieważ EventPipe jest składnikiem wbudowanym środowiska uruchomieniowego, jego zakres jest ograniczony do kodu zarządzanego i samego środowiska uruchomieniowego. EventPipe nie można używać do śledzenia pewnych zdarzeń niższego poziomu, takich jak rozpoznawanie natywnego stosu kodu lub uzyskiwanie różnych zdarzeń jądra. Jeśli używasz międzyoperacyjności C/C++ w aplikacji lub chcesz śledzić środowisko uruchomieniowe (które jest zapisywane w języku C++) lub chcesz uzyskać lepszą diagnostykę w zachowaniu aplikacji, która wymaga zdarzeń jądra (to znaczy zdarzenia przełączenia kontekstu natywnego wątku), należy użyć funkcji ETW lub [perf/LTTng](./trace-perfcollect-lttng.md).

Kolejną istotną różnicą między EventPipe i ETW/LTTng jest wymagania dotyczące uprawnień administratora/katalogu głównego. Aby śledzić aplikację przy użyciu funkcji ETW lub LTTng, musisz być administratorem/katalogiem głównym. Korzystając z EventPipe, można śledzić aplikacje tak długo, jak program śledzący (na przykład `dotnet-trace` ) jest uruchamiany jako ten sam użytkownik, który uruchomił aplikację.

Poniższa tabela zawiera podsumowanie różnic między EventPipe i ETW/LTTng.

|Obiekt feature|EventPipe|ETW|LTTng|
|-------|---------|---|-----------|
|Wiele platform|Tak|Nie (tylko w systemie Windows)|Nie (tylko w przypadku obsługiwanego dystrybucje systemu Linux)|
|Wymagaj uprawnienia administratora/elementu głównego|Nie|Tak|Tak|
|Może uzyskać zdarzenia systemu operacyjnego/jądra|Nie|Tak|Tak|
|Może rozpoznać natywny stosy wywołań|Nie|Tak|Tak|

## <a name="use-eventpipe-to-trace-your-net-application"></a>Śledzenie aplikacji platformy .NET za pomocą EventPipe

Możesz użyć EventPipe do śledzenia aplikacji .NET na wiele sposobów:

* Użyj jednego z [narzędzi diagnostycznych](#tools-using-eventpipe) , które są oparte na EventPipe.

* Za pomocą biblioteki [Microsoft. Diagnostics. servicecore. Client](https://github.com/dotnet/diagnostics/blob/master/documentation/diagnostics-client-library-instructions.md) można napisać własne narzędzie do samodzielnego konfigurowania i uruchamiania sesji EventPipe.

* Użyj [zmiennych środowiskowych](#trace-using-environment-variables) , aby uruchomić EventPipe.

Po wygenerowaniu `nettrace` pliku zawierającego zdarzenia EventPipe można wyświetlić plik w programie [`PerfView`](https://github.com/Microsoft/perfview#perfview-overview) lub programie Visual Studio. Na platformach innych niż Windows można skonwertować `nettrace` plik do `speedscope` `Chromium` formatu lub format śledzenia za pomocą [`dotnet-trace convert`](./dotnet-trace.md#dotnet-trace-convert) polecenia i wyświetlić go z [`speedscope`](https://www.speedscope.app/) lub Chrome devtools.

Możesz również analizować ślady EventPipe programowo przy użyciu [zdarzenie śledzenia](https://github.com/Microsoft/perfview/blob/master/documentation/TraceEvent/TraceEventLibrary.md).

### <a name="tools-that-use-eventpipe"></a>Narzędzia używające EventPipe

Jest to najprostszy sposób, aby używać EventPipe do śledzenia aplikacji. Aby dowiedzieć się więcej na temat korzystania z każdego z tych narzędzi, zapoznaj się z dokumentacją każdego narzędzia.

* Funkcja [dotnet-Counters](./dotnet-counters.md) umożliwia monitorowanie i zbieranie różnych metryk emitowanych przez środowisko uruchomieniowe .NET i biblioteki podstawowe, a także metryki niestandardowe, które można napisać.

* [dotnet-gcdump](./dotnet-gcdump.md) umożliwia zbieranie zrzutów sterty GC procesów na żywo na potrzeby analizowania sterty zarządzanej aplikacji.

* mechanizm [śledzenia dotnet](./dotnet-trace.md) umożliwia zbieranie śladów aplikacji do analizy pod kątem wydajności.

## <a name="trace-using-environment-variables"></a>Śledzenie przy użyciu zmiennych środowiskowych

Preferowanym mechanizmem korzystania z EventPipe jest użycie `dotnet-trace` programu lub `Microsoft.Diagnostics.NETCore.Client` biblioteki.

Można jednak użyć następujących zmiennych środowiskowych w celu skonfigurowania sesji EventPipe w aplikacji i zapisania śladu bezpośrednio do pliku. Aby zatrzymać śledzenie, zamknij aplikację.

* `COMPlus_EnableEventPipe`: Ustaw tę wartość na, `1` Aby uruchomić sesję EventPipe, która zapisuje bezpośrednio do pliku. Wartość domyślna to `0`.

* `COMPlus_EventPipeOutputPath`: Ścieżka do wyjściowego pliku śledzenia EventPipe, gdy jest on skonfigurowany do uruchamiania za pośrednictwem `COMPlus_EnableEventPipe` . Wartość domyślna to `trace.nettrace` , która zostanie utworzona w tym samym katalogu, w którym jest uruchomiona aplikacja.

* `COMPlus_CircularBufferMB`: Rozmiar wewnętrznego bufora, który jest używany przez EventPipe, gdy jest skonfigurowany do uruchamiania za pośrednictwem `COMPlus_EnableEventPipe` .

* `COMPlus_EventPipeConfig`: Konfiguruje konfigurację sesji EventPipe podczas uruchamiania sesji EventPipe z usługą `COMPlus_EnableEventPipe` .

  Składnia wygląda następująco:

  `<provider>:<keyword>:<level>`

  Można również określić wielu dostawców, łącząc je z przecinkiem:

  `<provider1>:<keyword1>:<level1>,<provider2>:<keyword2>:<level2>`

  Jeśli ta zmienna środowiskowa nie została ustawiona, ale EventPipe jest włączona przez `COMPlus_EnableEventPipe` program, rozpocznie śledzenie przez włączenie następujących dostawców z następującymi słowami kluczowymi i poziomami:

  - `Microsoft-Windows-DotNETRuntime:4c14fccbd:5`
  - `Microsoft-Windows-DotNETRuntimePrivate:4002000b:5`
  - `Microsoft-DotNETCore-SampleProfiler:0:5`
