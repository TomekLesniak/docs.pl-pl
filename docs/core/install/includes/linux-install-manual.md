---
ms.openlocfilehash: 3932cf51b5194dba7956cd62ced3985a2e6311f0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506826"
---

<!-- Note, this content is copied in ../macos.md. Any fixes should be applied there too, though content may be different -->

Jako alternatywę dla menedżerów pakietów można pobrać i ręcznie zainstalować zestaw SDK i środowisko uruchomieniowe. Instalacja ręczna jest zwykle wykonywana w ramach testowania ciągłej integracji lub nieobsługiwanej dystrybucji systemu Linux. W przypadku deweloperów lub użytkowników zazwyczaj lepiej jest używać Menedżera pakietów.

W przypadku instalowania zestawu .NET SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego. Najpierw pobierz wydanie **binarne** dla zestawu SDK lub środowiska uruchomieniowego z jednej z następujących lokacji:

- ✔️ [pliki do pobrania w programie .net 5,0](https://dotnet.microsoft.com/download/dotnet/5.0)
- [pliki do pobrania ✔️ .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [pliki do pobrania ✔️ .NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [Wszystkie pliki do pobrania z platformy .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

Następnie wyodrębnij pobrany plik i użyj polecenia, `export` Aby ustawić zmienne używane przez platformę .NET, a następnie upewnij się, że platforma .NET znajduje się w ścieżce.

Aby wyodrębnić środowisko uruchomieniowe i udostępnić polecenie interfejsu wiersza polecenia platformy .NET w terminalu, najpierw Pobierz wydanie binarne platformy .NET. Następnie otwórz Terminal i uruchom następujące polecenia z katalogu, w którym zapisano plik. Nazwa pliku archiwum może się różnić w zależności od pobranych informacji.

**Aby wyodrębnić środowisko uruchomieniowe, użyj następującego polecenia** :

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

**Użyj następującego polecenia, aby wyodrębnić zestaw SDK** :

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> Powyższe `export` polecenia sprawiają, że dla sesji terminala, w której został uruchomiony, są dostępne tylko polecenia interfejsu CLI platformy .NET.
>
> Możesz edytować profil powłoki, aby trwale dodać polecenia. Istnieje wiele różnych powłok dostępnych dla systemu Linux, a każdy z nich ma inny profil. Przykład:
>
> - **Bash Shell** : *~/.bash_profile* , *~/.bashrc.*
> - **Powłoka Korn** : *~/.KSHRC* lub *. profile*
> - **Powłoka Z** : *~/.zshrc* lub *. zprofile*
>
> Edytuj odpowiedni plik źródłowy dla powłoki i Dodaj `:$HOME/dotnet` na końcu istniejącej `PATH` instrukcji. Jeśli `PATH` instrukcja nie jest uwzględniona, Dodaj nowy wiersz za pomocą `export PATH=$PATH:$HOME/dotnet` .
>
> Ponadto Dodaj `export DOTNET_ROOT=$HOME/dotnet` na końcu pliku.

Takie podejście umożliwia zainstalowanie różnych wersji w oddzielnych lokalizacjach i wybór jawny, który ma być używany przez aplikację.
