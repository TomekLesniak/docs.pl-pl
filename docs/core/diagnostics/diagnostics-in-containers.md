---
title: Zbieranie danych diagnostycznych w kontenerach
description: W tym artykule dowiesz się, jak narzędzia diagnostyczne programu .NET Core mogą być używane w kontenerach platformy Docker.
ms.date: 09/01/2020
ms.openlocfilehash: cf4bbdf75e943f093a2202f91303a2eea7125487
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916212"
---
# <a name="collect-diagnostics-in-containers"></a>Zbieranie danych diagnostycznych w kontenerach

Te same narzędzia diagnostyczne, które są przydatne do diagnozowania problemów z platformą .NET Core w innych scenariuszach, również działają w kontenerach platformy Docker. Jednak niektóre narzędzia wymagają specjalnych kroków do pracy w kontenerze. W tym artykule opisano, jak narzędzia do zbierania danych śledzenia wydajności i zbierania zrzutów mogą być używane w kontenerach platformy Docker.

## <a name="using-net-core-cli-tools-in-a-container"></a>Korzystanie z interfejs wiersza polecenia platformy .NET Core narzędzi w kontenerze

**Te narzędzia dotyczą: ✔️** .net Core 3,0 SDK i nowszych wersji

Globalne narzędzia diagnostyczne interfejsu wiersza polecenia platformy .NET Core ( [`dotnet-counters`](dotnet-counters.md) , [`dotnet-dump`](dotnet-dump.md) , [`dotnet-gcdump`](dotnet-gcdump.md) i [`dotnet-trace`](dotnet-trace.md) ) są przeznaczone do pracy w wielu różnych środowiskach i powinny być wykonywane bezpośrednio w kontenerach platformy Docker. W związku z tym narzędzia te są preferowaną metodą zbierania informacji diagnostycznych dotyczących scenariuszy .NET Core przeznaczonych dla platformy .NET Core 3,0 lub nowszej (lub 3,1 lub nowszej w przypadku `dotnet-gcdump` ) w kontenerach.

Jedynym czynnikiem, który komplikują korzystanie z tych narzędzi w kontenerze jest instalacja z zestaw .NET Core SDK i wiele kontenerów platformy Docker jest uruchomionych bez zestaw .NET Core SDK obecne. Jednym z łatwych rozwiązań tego problemu jest zainstalowanie narzędzi w początkowym obrazie platformy Docker. Narzędzia nie potrzebują zestaw .NET Core SDK do uruchomienia, tylko do zainstalowania. W związku z tym można utworzyć pliku dockerfile z [Wieloetapową kompilacją](https://docs.docker.com/develop/develop-images/multistage-build/) , która instaluje narzędzia na etapie kompilacji (w którym znajduje się zestaw .NET Core SDK), a następnie kopiuje pliki binarne do obrazu końcowego. Jedyną minusemem tego podejścia jest zwiększony rozmiar obrazu platformy Docker.

```dockerfile
# In build stage
# Install desired .NET CLI diagnostics tools
RUN dotnet tool install --tool-path /tools dotnet-trace
RUN dotnet tool install --tool-path /tools dotnet-counters
RUN dotnet tool install --tool-path /tools dotnet-dump

...

# In final stage
# Copy diagnostics tools
WORKDIR /tools
COPY --from=build /tools .
```

Alternatywnie, zestaw .NET Core SDK można zainstalować w kontenerze, gdy jest to konieczne w celu zainstalowania narzędzi interfejsu wiersza polecenia. Należy pamiętać, że zainstalowanie zestaw .NET Core SDK będzie miało wpływ na ponowną instalację środowiska uruchomieniowego platformy .NET Core. Upewnij się, że zainstalowano wersję zestawu SDK, która pasuje do środowiska uruchomieniowego znajdującego się w kontenerze.

### <a name="using-net-core-global-cli-tools-in-a-sidecar-container"></a>Korzystanie z globalnych narzędzi interfejsu wiersza polecenia platformy .NET Core w kontenerze przyczepki

Jeśli chcesz użyć narzędzi diagnostycznych globalnych interfejsu wiersza polecenia platformy .NET Core do diagnozowania procesów w innym kontenerze, weź pod uwagę następujące dodatkowe wymagania:

1. Kontenery muszą [udostępniać przestrzeń nazw procesu](https://docs.docker.com/engine/reference/run/#pid-settings---pid) (dzięki czemu narzędzia w kontenerze przyczepki mogą uzyskać dostęp do procesów w kontenerze docelowym).
2. Globalne narzędzia diagnostyczne interfejsu wiersza polecenia platformy .NET Core potrzebują dostępu do plików, które są zapisywane w środowisku uruchomieniowym .NET Core w katalogu/tmp, więc katalog/tmp musi być współużytkowany między docelowym i kontenerem przyczepki za pośrednictwem instalacji woluminu. Można to zrobić na przykład w przypadku, gdy kontenery korzystają ze wspólnego [woluminu](https://docs.docker.com/storage/volumes/#create-and-manage-volumes) lub woluminu [emptyDir](https://kubernetes.io/docs/concepts/storage/volumes/#emptydir) Kubernetes. W przypadku próby użycia narzędzi diagnostycznych z kontenera przyczepki bez udostępniania katalogu/tmp zostanie wyświetlony komunikat o błędzie dotyczący procesu "niezgodnego środowiska uruchomieniowego .NET".

## <a name="using-perfcollect-in-a-container"></a>Używanie `PerfCollect` w kontenerze

**To narzędzie dotyczy: ✔️** .net Core 2,1 i jego nowszych wersjach

[`PerfCollect`](./trace-perfcollect-lttng.md)Skrypt jest przydatny do zbierania danych śledzenia wydajności i jest zalecanym narzędziem do zbierania śladów przed platformą .NET Core 3,0. W przypadku używania `PerfCollect` w kontenerze należy pamiętać o następujących wymaganiach:

1. `PerfCollect`wymaga [ `SYS_ADMIN` możliwości](https://man7.org/linux/man-pages/man7/capabilities.7.html) (w celu uruchomienia `perf` Narzędzia), dlatego należy się upewnić, że kontener został [uruchomiony z tą możliwością](https://docs.docker.com/engine/reference/run/#runtime-privilege-and-linux-capabilities).
2. `PerfCollect` wymaga ustawienia niektórych zmiennych środowiskowych przed aplikacją, która jest uruchamiana. Można je ustawić w [pliku dockerfile](https://docs.docker.com/engine/reference/builder/#env) lub podczas [uruchamiania kontenera](https://docs.docker.com/engine/reference/run/#env-environment-variables). Ponieważ te zmienne nie powinny być ustawiane w normalnych środowiskach produkcyjnych, często należy je dodać podczas uruchamiania kontenera, który zostanie profilowany. Dwie zmienne, które PerfCollect wymagają:
    1. COMPlus_PerfMapEnabled = 1
    1. COMPlus_EnableEventLog = 1

### <a name="using-perfcollect-in-a-sidecar-container"></a>Używanie `PerfCollect` w kontenerze przyczepki

Jeśli chcesz uruchomić program `PerfCollect` w jednym kontenerze w celu profilowania procesu .NET Core w innym kontenerze, środowisko jest niemal takie samo, z wyjątkiem następujących różnic:

1. Zmienne środowiskowe wymienione wcześniej (COMPlus_PerfMapEnabled i COMPlus_EnableEventLog) muszą być ustawione dla kontenera docelowego (a nie z uruchomionym `PerfCollect` ).
2. Uruchomiony kontener `PerfCollect` musi mieć `SYS_ADMIN` możliwość (nie jest to kontener docelowy).
3. Dwa kontenery muszą [współdzielić przestrzeń nazw procesu](https://docs.docker.com/engine/reference/run/#pid-settings---pid).

## <a name="using-createdump-in-a-container"></a>Używanie `createdump` w kontenerze

**To narzędzie dotyczy: ✔️** .net Core 2,1 i jego nowszych wersjach

Alternatywą dla `dotnet-dump` programu [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) można użyć do tworzenia podstawowych zrzutów w systemie Linux zawierających zarówno informacje natywne, jak i zarządzane. `createdump`Narzędzie jest instalowane przy użyciu środowiska uruchomieniowego .NET Core i można je znaleźć obok libcoreclr.so (zazwyczaj w "/usr/share/dotnet/Shared/Microsoft.NETCore.App/[wersja]"). Narzędzie działa tak samo w kontenerze, jak w środowiskach z systemem Linux niekontenerów z pojedynczym wyjątkiem, że narzędzie wymaga tej [ `SYS_PTRACE` możliwości](https://man7.org/linux/man-pages/man7/capabilities.7.html), więc kontener platformy Docker musi być [uruchomiony z tą możliwością](https://docs.docker.com/engine/reference/run/#runtime-privilege-and-linux-capabilities).

### <a name="using-createdump-in-a-sidecar-container"></a>Używanie `createdump` w kontenerze przyczepki

Jeśli chcesz użyć `createdump` do utworzenia zrzutu z procesu w innym kontenerze, środowisko jest niemal takie samo, z wyjątkiem następujących różnic:

1. Uruchomiony kontener `createdump` musi mieć `SYS_PTRACE` możliwość (nie jest to kontener docelowy).
2. Dwa kontenery muszą [współdzielić przestrzeń nazw procesu](https://docs.docker.com/engine/reference/run/#pid-settings---pid).
