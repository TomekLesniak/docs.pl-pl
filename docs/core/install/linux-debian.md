---
title: Instalowanie platformy .NET w systemie Debian — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie Debian.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 6dad4e1779600b22b8301e03ffb8fb2c16786ead
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506997"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-debian"></a>Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie Debian

W tym artykule opisano sposób instalowania programu .NET w systemie Debian. Gdy wersja Debian nie jest obsługiwana, program .NET nie jest już obsługiwany w tej wersji. Jednak te instrukcje mogą pomóc w uzyskaniu środowiska .NET działającego w tych wersjach, nawet jeśli nie jest to obsługiwane.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Obsługiwane dystrybucje

Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Debian, w których są obsługiwane. Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca wsparcia](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Debian osiągnie koniec cyklu życia](https://wiki.debian.org/DebianReleases).

- ✔️ wskazuje, że wersja programu debian lub .NET jest nadal obsługiwana.
- ❌Wskazuje, że wersja programu debian lub .NET nie jest obsługiwana w tej wersji Debian.
- Gdy wersja programu Debian i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.

| Debian                   | .NET Core 2.1 | .NET Core 3,1 | .NET 5,0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [10](#debian-10-)     | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ [9](#debian-9-)       | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ❌ [8](#debian-8-)       | ✔️ 2,1        | ❌ 3,1        | ❌ 5,0 |

Następujące wersje platformy .NET nie są już obsługiwane. Pliki do pobrania dla tych nadal są publikowane:

- 3.0
- 2.2
- 2,0

## <a name="how-to-install-other-versions"></a>Jak zainstalować inne wersje

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a>Debian 10 ✔️

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="debian-9-"></a>Debian ✔️ 9

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="debian-8-"></a>Debian 8 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-debian.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/8/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a>APT Update — zestaw SDK lub środowisko uruchomieniowe

Gdy jest dostępna nowa wersja poprawek dla programu .NET, można po prostu uaktualnić ją za pomocą APT przy użyciu następujących poleceń:

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a>Rozwiązywanie problemów z APT

Ta sekcja zawiera informacje o typowych błędach, które mogą wystąpić podczas korzystania z programu APT w celu zainstalowania platformy .NET.

### <a name="unable-to-find-package"></a>Nie można znaleźć pakietu

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a>Nie można zlokalizować niektórych pakietów, których nie można \\ zainstalować

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a>Nie można pobrać

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a>Przystawki

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a>Zależności

Po zainstalowaniu programu przy użyciu Menedżera pakietów te biblioteki są instalowane dla Ciebie. Jeśli jednak ręcznie zainstalujesz platformę .NET Core lub opublikujesz aplikację, musisz upewnić się, że te biblioteki są zainstalowane:

- libc6
- libgcc1
- libgssapi-krb5-2
- libicu52 (dla 8. x)
- libicu57 (dla 9. x)
- libicu63 (dla 10. x)
- libicu67 (dla 11. x)
- libssl 1.0.0 (dla 8. x)
- libssl 1.1 (dla 9. x-11. x)
- libstdc + + 6
- zlib1g

W przypadku aplikacji .NET Core, które używają zestawu *System. Drawing. Common* , wymagana jest również następująca zależność:

- libgdiplus (wersja 6.0.1 lub nowsza)

  > [!WARNING]
  > Aby zainstalować najnowszą wersję programu *libgdiplus* , można dodać do systemu repozytorium mono. Aby uzyskać więcej informacji, zobacz <https://www.mono-project.com/download/stable/>.

## <a name="scripted-install"></a>Instalacja z skryptami

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Instalacja ręczna

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Następne kroki

- [Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code](../tutorials/with-visual-studio-code.md)
