---
title: dotnet-gcdump-.NET Core
description: Instalowanie i używanie narzędzia wiersza polecenia dotnet-gcdump.
ms.date: 07/26/2020
ms.openlocfilehash: 10e4c7e9e3a1df5d0eb58e68d38c0af091aeedc1
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88575684"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a>Narzędzie do analizy sterty (dotnet-gcdump)

**Ten artykuł ma zastosowanie do:** ✔️ .net Core 3,1 SDK i nowszych wersjach

## <a name="install-dotnet-gcdump"></a>Zainstaluj dotnet-gcdump

Aby zainstalować najnowszą wersję `dotnet-gcdump` [pakietu NuGet](https://www.nuget.org/packages/dotnet-gcdump), użyj polecenia [Narzędzia dotnet Install](../tools/dotnet-tool-install.md) :

```dotnetcli
dotnet tool install -g dotnet-gcdump
```

## <a name="synopsis"></a>Streszczenie

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a>Opis

`dotnet-gcdump`Globalnym narzędziem jest sposób zbierania zrzutów GC (Moduł wyrzucania elementów bezużytecznych) procesów .NET na żywo. Używa technologii EventPipe, która jest wieloplatformową alternatywą dla funkcji ETW w systemie Windows. Zrzuty GC są tworzone przez wyzwolenie GC w procesie docelowym, włączenie zdarzeń specjalnych i ponowne wygenerowanie grafu obiektów głównych obiektu ze strumienia zdarzeń. Pozwala to na zbieranie zrzutów GC, gdy proces jest uruchomiony, przy minimalnym obciążeniu. Te zrzuty są przydatne w kilku scenariuszach:

- Porównanie liczby obiektów w stercie w kilku punktach w czasie.
- Analizowanie katalogów głównych obiektów (odpowiedzi na pytania, takie jak nadal ma odwołanie do tego typu?).
- Zbieranie ogólnych statystyk o liczbie obiektów na stercie.

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a>Wyświetlanie zrzutu pamięci podręcznej przechwycone z programu dotnet-gcdump

W systemie Windows `.gcdump` pliki można wyświetlać w [Narzędzia PerfView](https://github.com/microsoft/perfview) na potrzeby analizy lub w programie Visual Studio. Obecnie nie ma możliwości otwierania `.gcdump` na platformach innych niż Windows.

Można zbierać wiele `.gcdump` i otwierać je jednocześnie w programie Visual Studio w celu uzyskania porównania.

## <a name="options"></a>Opcje

- **`--version`**

  Wyświetla wersję `dotnet-gcdump` Narzędzia.

- **`-h|--help`**

  Wyświetla pomoc w wierszu polecenia.

## `dotnet-gcdump collect`

Zbiera zrzut GC z aktualnie uruchomionego procesu.

### <a name="synopsis"></a>Streszczenie

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a>Opcje

- **`-h|--help`**

  Wyświetla pomoc w wierszu polecenia.

- **`-p|--process-id <pid>`**

  Identyfikator procesu, z którego ma zostać zebrany zrzut GC.

- **`-o|--output <gcdump-file-path>`**

  Ścieżka, w której powinny być zapisywane zebrane zrzuty GC. Wartość domyślna to *. \\ RRRRMMDD \_ HHMMSS \_ \<pid> . gcdump*.

- **`-v|--verbose`**

  Wyprowadza dziennik podczas zbierania zrzutu GC.

- **`-t|--timeout <timeout>`**

  Zastanów się nad zbieraniem zrzutu pamięci podręcznej, jeśli trwa dłużej niż wynosi to wiele sekund. Wartość domyślna to 30.

- **`-n|--name <name>`**

  Nazwa procesu, z którego ma zostać zebrany zrzut GC.

## `dotnet-gcdump ps`

Wyświetla listę procesów dotnet, dla których można zbierać zrzuty GC.

### <a name="synopsis"></a>Streszczenie

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

Wygeneruj Raport z wcześniej wygenerowanego zrzutu GC lub z uruchomionego procesu, a następnie wpisz polecenie `stdout` .

### <a name="synopsis"></a>Streszczenie

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a>Opcje

- **`-h|--help`**

  Wyświetla pomoc w wierszu polecenia.

- **`-p|--process-id <pid>`**

  Identyfikator procesu, z którego ma zostać zebrany zrzut GC.

- **`-t|--report-type <HeapStat>`**

  Typ raportu do wygenerowania. Dostępne opcje: heapstat (domyślnie).

## <a name="troubleshoot"></a>Rozwiązywanie problemów

- Brak informacji o typie w gcdump.

   Przed platformą .NET Core 3,1 wystąpił problem polegający na tym, że pamięć podręczna typu nie została wyczyszczona między gcdumps, gdy zostały wywołane z EventPipe. Spowodowało to zdarzenia, które trzeba wykonać, aby określić informacje o typie, które nie są wysyłane dla drugiego i kolejnego gcdumps. Ten problem został rozwiązany w programie .NET Core 3,1-preview2.

- COM i typy statyczne nie znajdują się w zrzucie odzyskiwania pamięci.

   Przed uruchomieniem programu .NET Core 3,1-preview2 wystąpił problem polegający na tym, że typy statyczne i COM nie zostały wysłane, gdy zrzut GC został wywołany za pośrednictwem EventPipe. Ten problem został rozwiązany w programie .NET Core 3,1-preview2.
