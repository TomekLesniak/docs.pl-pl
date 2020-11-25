---
title: Usuwanie środowiska uruchomieniowego i zestawu SDK platformy .NET
description: W tym artykule opisano sposób ustalania, które wersje środowiska uruchomieniowego .NET i zestawu SDK są obecnie zainstalowane, a następnie sposobu ich usuwania w systemach Windows, Mac i Linux.
author: adegeo
ms.author: adegeo
ms.date: 11/20/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: f07a9acdc5be310d38da18602dde2ebf678e9a1b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031725"
---
# <a name="how-to-remove-the-net-runtime-and-sdk"></a>Jak usunąć środowisko uruchomieniowe .NET i zestaw SDK

Wraz z upływem czasu podczas instalowania zaktualizowanych wersji środowiska uruchomieniowego i zestawu SDK platformy .NET możesz chcieć usunąć nieaktualne wersje platformy .NET z komputera. Usunięcie starszych wersji środowiska uruchomieniowego może zmienić środowisko uruchomieniowe wybrane do uruchamiania aplikacji platformy udostępnionej, zgodnie z opisem w artykule na temat [wyboru wersji platformy .NET](../versions/selection.md).

## <a name="should-i-remove-a-version"></a>Czy należy usunąć wersję?

Zachowania [wyboru wersji platformy .NET](../versions/selection.md) i zgodność środowiska uruchomieniowego platformy .NET między aktualizacjami umożliwiają bezpieczne usunięcie poprzednich wersji. Aktualizacje środowiska uruchomieniowego platformy .NET są zgodne w ramach głównych **grup** wersji, takich jak 1. x i 2. x. Ponadto nowsze wersje zestawu .NET SDK zwykle utrzymują możliwość tworzenia aplikacji przeznaczonych dla wcześniejszych wersji środowiska uruchomieniowego w sposób zgodny.

Ogólnie rzecz biorąc potrzebny jest tylko najnowszy zestaw SDK i Najnowsza wersja poprawki środowiska uruchomieniowego, które są wymagane dla danej aplikacji. Wystąpienia, w których można przechowywać starsze wersje zestawu SDK lub środowiska uruchomieniowego, obejmują obsługęproject.jsaplikacji opartych *na systemie*. Jeśli aplikacja nie ma określonych powodów dla wcześniejszych zestawów SDK lub środowisk uruchomieniowych, możesz bezpiecznie usunąć starsze wersje.

## <a name="determine-what-is-installed"></a>Określ, co jest zainstalowane

Interfejs wiersza polecenia platformy .NET zawiera opcje, których można użyć, aby wyświetlić listę wersji zestawu SDK i środowiska uruchomieniowego, które są zainstalowane na komputerze.  Użyj, [`dotnet --list-sdks`](../tools/dotnet.md#options) Aby wyświetlić listę zestawów SDK zainstalowanych na komputerze. Użyj, [`dotnet --list-runtimes`](../tools/dotnet.md#options) Aby wyświetlić listę środowisk uruchomieniowych zainstalowanych na maszynie. Aby uzyskać więcej informacji, zobacz [Jak sprawdzić, czy program .NET jest już zainstalowany](how-to-detect-installed-versions.md).

## <a name="uninstall-net"></a>Odinstaluj platformę .NET

::: zone pivot="os-windows"

Platforma .NET używa okna dialogowego **funkcji & aplikacji** systemu Windows do usuwania wersji środowiska uruchomieniowego i zestawu SDK platformy .NET. Na poniższej ilustracji przedstawiono okno dialogowe **aplikacje & funkcje** . Można wyszukać **zestaw Core SDK** lub **zestaw SDK platformy .NET** , aby filtrować i wyświetlać zainstalowane wersje platformy .NET.

![Dodaj/Usuń programy, aby usunąć platformę .NET](./media/remove-runtime-sdk-versions/programs-and-features.png)

Wybierz wszystkie wersje, które chcesz usunąć z komputera, a następnie kliknij przycisk **Odinstaluj**.

::: zone-end

::: zone pivot="os-linux"

Istnieje więcej opcji odinstalowywania platformy .NET (zestawu SDK lub środowiska uruchomieniowego) w systemie Linux. Najlepszym sposobem odinstalowania programu .NET jest dublowanie akcji użytej do zainstalowania platformy .NET. Informacje te zależą od wybranej dystrybucji i metody instalacji.

> [!IMPORTANT]
> W przypadku instalacji Red Hat zapoznaj się z [dokumentacją produktu Red Hat dla platformy .NET](https://access.redhat.com/documentation/en-us/net/5.0/).

Nie ma potrzeby odinstalowywania zestawu .NET SDK podczas uaktualniania go przy użyciu Menedżera pakietów, chyba że uaktualniasz wersję zapoznawczą. Menedżer pakietów `update` lub `refresh` polecenia automatycznie usuwają starszą wersję po pomyślnej instalacji nowszej wersji. Jeśli masz zainstalowaną wersję zapoznawczą, odinstaluj ją.

Jeśli zainstalowano program .NET przy użyciu Menedżera pakietów, należy użyć tego samego Menedżera pakietów do odinstalowania zestawu .NET SDK lub środowiska uruchomieniowego. Instalacje platformy .NET obsługują najpopularniejszych menedżerów pakietów. Zapoznaj się z dokumentacją Menedżera pakietów dystrybucji, aby uzyskać dokładną składnię w Twoim środowisku:

- [apt-get (8)](https://linux.die.net/man/8/apt-get) jest używany przez systemy oparte na Debian, w tym Ubuntu.
- [yum (8)](https://linux.die.net/man/8/yum) jest używany na Fedora, CentOS i Oracle Linux.
- [użyciu narzędzia zypper (8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) jest używany w systemach OPENSUSE i SUSE Linux Enterprise System (SLES).
- [DNF (8)](https://dnf.readthedocs.io/en/latest/command_ref.html) jest używany w Fedora.

Niemal we wszystkich przypadkach polecenie usunięcia pakietu ma wartość `remove` .

Nazwa pakietu dla instalacji zestawu .NET SDK dla większości menedżerów pakietów ma `dotnet-sdk` numer wersji. Począwszy od wersji 2.1.300 zestawu .NET SDK i wersji `2.1` środowiska uruchomieniowego, wymagane są tylko główne i pomocnicze numery wersji: na przykład zestaw SDK .NET w wersji 2.1.300 może być przywoływany jako pakiet `dotnet-sdk-2.1` . Wcześniejsze wersje wymagają całego ciągu wersji: na przykład, `dotnet-sdk-2.1.200` będzie wymagane w przypadku wersji 2.1.200 zestawu .NET SDK.

W przypadku maszyn, na których zainstalowano tylko środowisko uruchomieniowe, a nie zestawu SDK, nazwa pakietu jest `dotnet-runtime-<version>` dla środowiska uruchomieniowego .NET i `aspnetcore-runtime-<version>` dla całego stosu środowiska uruchomieniowego.

> [!TIP]
> Instalacje .NET Core starsze niż 2,0 nie odinstalowały aplikacji hosta podczas odinstalowywania zestawu SDK przy użyciu Menedżera pakietów. Za pomocą `apt-get` polecenia jest:
>
> ```bash
> apt-get remove dotnet-host
> ```
>
> Brak dołączonej wersji programu `dotnet-host` .

Jeśli zainstalowano program przy użyciu plik tar, należy usunąć platformę .NET przy użyciu metody ręcznej.

W systemie Linux należy osobno usunąć zestawy SDK i środowiska uruchomieniowe, usuwając katalogi z wersjami. Usunięcie ich spowoduje usunięcie zestawu SDK i środowiska uruchomieniowego z dysku. Na przykład aby usunąć zestaw 1.0.1 SDK i środowisko uruchomieniowe, należy użyć następujących poleceń bash:

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

Katalogi nadrzędne dla zestawu SDK i środowiska uruchomieniowego są wymienione w danych wyjściowych `dotnet --list-sdks` `dotnet --list-runtimes` polecenia i, jak pokazano w wcześniejszej tabeli.

::: zone-end

::: zone pivot="os-macos"

Na komputerach Mac należy osobno usunąć zestawy SDK i środowiska uruchomieniowe, usuwając katalogi z wersjami. Usunięcie ich spowoduje usunięcie zestawu SDK i środowiska uruchomieniowego z dysku. Na przykład aby usunąć zestaw 1.0.1 SDK i środowisko uruchomieniowe, należy użyć następujących poleceń bash:

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

Katalogi nadrzędne dla zestawu SDK i środowiska uruchomieniowego są wymienione w danych wyjściowych `dotnet --list-sdks` `dotnet --list-runtimes` polecenia i, jak pokazano w wcześniejszej tabeli.

::: zone-end

## <a name="net-uninstall-tool"></a>Narzędzie do dezinstalacji platformy .NET

[Narzędzie do dezinstalacji .NET](../additional-tools/uninstall-tool.md) ( `dotnet-core-uninstall` ) umożliwia usuwanie zestawów .NET SDK i środowisk uruchomieniowych z systemu. Dostępna jest kolekcja opcji, aby określić, które wersje mają być odinstalowane.

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a>Zależność programu Visual Studio od wersji zestaw .NET Core SDK

Przed dodaniem programu Visual Studio 2019 w wersji 16,3, instalatorzy programu Visual Studio o nazwie autonomiczne zestaw .NET Core SDK Instalatora. W związku z tym wersje zestawu SDK pojawiają się w oknie dialogowym aplikacje systemu Windows **& funkcje** . Usunięcie zestawów SDK platformy .NET Core zainstalowanych przez program Visual Studio za pomocą autonomicznego Instalatora może spowodować przerwanie programu Visual Studio. Jeśli program Visual Studio ma problemy po odinstalowaniu zestawów SDK, należy uruchomić polecenie Repair dla tej konkretnej wersji programu Visual Studio. W poniższej tabeli przedstawiono niektóre zależności programu Visual Studio na zestaw .NET Core SDK wersje:

| Wersja programu Visual Studio           | Wersja zestaw .NET Core SDK          |
|---------------------------------|--------------------------------|
|  Program Visual Studio 2019 w wersji 16.2  | Zestaw .NET Core SDK 2.2.4 XX, 2.1.8 XX |
| Visual Studio 2019 w wersji 16.1 | Zestaw .NET Core SDK 2.2.3 XX, 2.1.7 XX |
| Visual Studio 2019 w wersji 16,0 | Zestaw .NET Core SDK 2.2.2 XX, 2.1.6 XX |
| Visual Studio 2017 w wersji 15,9 | Zestaw .NET Core SDK 2.2.1 XX, 2.1.5 XX |
| Visual Studio 2017 w wersji 15,8 | Zestaw .NET Core SDK 2.1.4 XX          |

Począwszy od programu Visual Studio 2019 w wersji 16,3, program Visual Studio jest odpowiedzialny za własną kopię zestawu .NET SDK. Z tego powodu te wersje zestawu SDK nie są już widoczne w oknie dialogowym **aplikacje & funkcje** .

## <a name="remove-the-nuget-fallback-folder"></a>Usuń folder rezerwowy NuGet

Przed zestawem SDK platformy .NET Core 3,0, Instalatory zestaw .NET Core SDK używały folderu o nazwie *NuGetFallbackFolder* do przechowywania pamięci podręcznej pakietów NuGet. Ta pamięć podręczna została użyta podczas operacji takich jak `dotnet restore` lub `dotnet build /t:Restore` . *NuGetFallbackFolder* znajduje się w *katalogu C:\Program Files\dotnet\sdk* w systemie Windows i na */usr/local/share/dotnet/SDK* na macOS.

Możesz chcieć usunąć ten folder, jeśli:

- Jest to możliwe tylko przy użyciu zestawu SDK platformy .NET Core 3,0 lub programu .NET 5,0 lub jego nowszych wersji.
- Opracowujesz przy użyciu wersji zestaw .NET Core SDK wcześniejszej niż 3,0, ale możesz korzystać z trybu online.

Jeśli chcesz usunąć folder rezerwowy NuGet, możesz go usunąć, ale musisz mieć uprawnienia administratora.

Nie zaleca się usuwania folderu *dotnet* . Spowoduje to usunięcie wszystkich wcześniej zainstalowanych narzędzi globalnych. Ponadto w systemie Windows:

- Spowoduje to przerwanie programu Visual Studio 2019 w wersji 16,3 i nowszych. Aby odzyskać, możesz wykonać **naprawę** .
- Jeśli w oknie dialogowym **aplikacje & funkcji** znajdują się wpisy zestaw .NET Core SDK, zostaną one oddzielone.
