---
ms.openlocfilehash: 3932cf51b5194dba7956cd62ced3985a2e6311f0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506826"
---

<!-- Note, this content is copied in ../macos.md. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="370e0-101">Jako alternatywę dla menedżerów pakietów można pobrać i ręcznie zainstalować zestaw SDK i środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="370e0-101">As an alternative to the package managers, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="370e0-102">Instalacja ręczna jest zwykle wykonywana w ramach testowania ciągłej integracji lub nieobsługiwanej dystrybucji systemu Linux.</span><span class="sxs-lookup"><span data-stu-id="370e0-102">Manual install is usually performed as part of continuous integration testing or on an unsupported Linux distribution.</span></span> <span data-ttu-id="370e0-103">W przypadku deweloperów lub użytkowników zazwyczaj lepiej jest używać Menedżera pakietów.</span><span class="sxs-lookup"><span data-stu-id="370e0-103">For a developer or user, it's generally better to use a package manager.</span></span>

<span data-ttu-id="370e0-104">W przypadku instalowania zestawu .NET SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="370e0-104">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="370e0-105">Najpierw pobierz wydanie **binarne** dla zestawu SDK lub środowiska uruchomieniowego z jednej z następujących lokacji:</span><span class="sxs-lookup"><span data-stu-id="370e0-105">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="370e0-106">✔️ [pliki do pobrania w programie .net 5,0](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="370e0-106">✔️ [.NET 5.0 downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="370e0-107">[pliki do pobrania ✔️ .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="370e0-107">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="370e0-108">[pliki do pobrania ✔️ .NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="370e0-108">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="370e0-109">Wszystkie pliki do pobrania z platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="370e0-109">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="370e0-110">Następnie wyodrębnij pobrany plik i użyj polecenia, `export` Aby ustawić zmienne używane przez platformę .NET, a następnie upewnij się, że platforma .NET znajduje się w ścieżce.</span><span class="sxs-lookup"><span data-stu-id="370e0-110">Next, extract the downloaded file and use the `export` command to set variables used by .NET and then ensure .NET is in PATH.</span></span>

<span data-ttu-id="370e0-111">Aby wyodrębnić środowisko uruchomieniowe i udostępnić polecenie interfejsu wiersza polecenia platformy .NET w terminalu, najpierw Pobierz wydanie binarne platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="370e0-111">To extract the runtime and make the .NET CLI commands available at the terminal, first download a .NET binary release.</span></span> <span data-ttu-id="370e0-112">Następnie otwórz Terminal i uruchom następujące polecenia z katalogu, w którym zapisano plik.</span><span class="sxs-lookup"><span data-stu-id="370e0-112">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="370e0-113">Nazwa pliku archiwum może się różnić w zależności od pobranych informacji.</span><span class="sxs-lookup"><span data-stu-id="370e0-113">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="370e0-114">**Aby wyodrębnić środowisko uruchomieniowe, użyj następującego polecenia** :</span><span class="sxs-lookup"><span data-stu-id="370e0-114">**Use the following command to extract the runtime** :</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="370e0-115">**Użyj następującego polecenia, aby wyodrębnić zestaw SDK** :</span><span class="sxs-lookup"><span data-stu-id="370e0-115">**Use the following command to extract the SDK** :</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="370e0-116">Powyższe `export` polecenia sprawiają, że dla sesji terminala, w której został uruchomiony, są dostępne tylko polecenia interfejsu CLI platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="370e0-116">The preceding `export` commands only make the .NET CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="370e0-117">Możesz edytować profil powłoki, aby trwale dodać polecenia.</span><span class="sxs-lookup"><span data-stu-id="370e0-117">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="370e0-118">Istnieje wiele różnych powłok dostępnych dla systemu Linux, a każdy z nich ma inny profil.</span><span class="sxs-lookup"><span data-stu-id="370e0-118">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="370e0-119">Przykład:</span><span class="sxs-lookup"><span data-stu-id="370e0-119">For example:</span></span>
>
> - <span data-ttu-id="370e0-120">**Bash Shell** : *~/.bash_profile* , *~/.bashrc.*</span><span class="sxs-lookup"><span data-stu-id="370e0-120">**Bash Shell** : *~/.bash_profile* , *~/.bashrc*</span></span>
> - <span data-ttu-id="370e0-121">**Powłoka Korn** : *~/.KSHRC* lub *. profile*</span><span class="sxs-lookup"><span data-stu-id="370e0-121">**Korn Shell** : *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="370e0-122">**Powłoka Z** : *~/.zshrc* lub *. zprofile*</span><span class="sxs-lookup"><span data-stu-id="370e0-122">**Z Shell** : *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="370e0-123">Edytuj odpowiedni plik źródłowy dla powłoki i Dodaj `:$HOME/dotnet` na końcu istniejącej `PATH` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="370e0-123">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="370e0-124">Jeśli `PATH` instrukcja nie jest uwzględniona, Dodaj nowy wiersz za pomocą `export PATH=$PATH:$HOME/dotnet` .</span><span class="sxs-lookup"><span data-stu-id="370e0-124">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="370e0-125">Ponadto Dodaj `export DOTNET_ROOT=$HOME/dotnet` na końcu pliku.</span><span class="sxs-lookup"><span data-stu-id="370e0-125">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="370e0-126">Takie podejście umożliwia zainstalowanie różnych wersji w oddzielnych lokalizacjach i wybór jawny, który ma być używany przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="370e0-126">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>
