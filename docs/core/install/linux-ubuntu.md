---
title: Instalowanie platformy .NET w systemie Ubuntu — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie Ubuntu.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 419bcf3ccd011cadba8f8c64e195d7dbdbf7e241
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507029"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-ubuntu"></a>Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie Ubuntu

Platforma .NET jest obsługiwana w systemie Ubuntu. W tym artykule opisano sposób instalowania programu .NET w systemie Ubuntu. Gdy wersja Ubuntu nie jest objęta wsparciem, platforma .NET nie jest już obsługiwana w tej wersji. Jednak te instrukcje mogą pomóc w uzyskaniu środowiska .NET działającego w tych wersjach, nawet jeśli nie jest to obsługiwane.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Obsługiwane dystrybucje

Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Ubuntu, w których są obsługiwane. Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca wsparcia](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Ubuntu osiągnie koniec cyklu życia](https://wiki.ubuntu.com/Releases).

- ✔️ wskazuje, że wersja programu Ubuntu lub .NET jest nadal obsługiwana.
- ❌Wskazuje, że wersja programu Ubuntu lub .NET nie jest obsługiwana w tej wersji Ubuntu.
- Gdy wersja programu Ubuntu i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.

| Ubuntu                   | .NET Core 2.1 | .NET Core 3,1 | .NET 5,0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [20,10](#2010-)       | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ [20,04 (LTS)](#2004-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ❌[19,10](#1910-)       | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ❌[19,04](#1904-)       | ✔️ 2,1        | ✔️ 3,1        | ❌ 5,0 |
| ❌[18,10](#1810-)       | ✔️ 2,1        | ❌ 3,1        | ❌ 5,0 |
| ✔️ [18,04 (LTS)](#1804-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ❌[17,10](#1710-)       | ✔️ 2,1        | ❌ 3,1        | ❌ 5,0 |
| ❌[17,04](#1704-)       | ✔️ 2,1        | ❌ 3,1        | ❌ 5,0 |
| ❌[16,10](#1610-)       | ❌ 2,1        | ❌ 3,1        | ❌ 5,0 |
| ✔️ [16,04 (LTS)](#1604-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |

Następujące wersje platformy .NET nie są już obsługiwane. Pliki do pobrania dla tych nadal są publikowane:

- 3.0
- 2.2
- 2,0

## <a name="how-to-install-other-versions"></a>Jak zainstalować inne wersje

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2010-"></a>20,10 ✔️

W programie .NET 5 i źródłach danych pakietu .NET Core 3,1 dla Ubuntu 20,10 obecnie występuje problem. Aby uzyskać więcej informacji o tym problemie, zobacz sekcję dotyczącą usługi [GitHub wydaj/Core # 5549](https://github.com/dotnet/core/issues/5549). Ten artykuł zostanie zaktualizowany po rozwiązaniu problemu.

Aby zainstalować platformę .NET 5 lub .NET Core 3,1 w systemie Ubuntu 20,10, postępuj zgodnie z instrukcjami dotyczącymi [20,04](#2004-).

## <a name="2004-"></a>20,04 ✔️

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1910-"></a>19,10 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a>19,04 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a>18,10 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a>18,04 ✔️

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1710-"></a>17,10 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a>17,04 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a>16,10 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a>16,04 ✔️

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

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
wget https://packages.microsoft.com/config/ubuntu/{os-version}/prod.list
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

Po zainstalowaniu programu przy użyciu Menedżera pakietów te biblioteki są instalowane dla Ciebie. Jeśli jednak ręcznie zainstalujesz program .NET lub opublikujesz aplikację, należy upewnić się, że te biblioteki są zainstalowane:

- libc6
- libgcc1
- libgssapi-krb5-2
- libicu52 (dla 14. x)
- libicu55 (dla 16. x)
- libicu60 (dla 18. x)
- libicu66 (dla 20. x)
- libssl 1.0.0 (dla 14. x, 16. x)
- libssl 1.1 (dla 18. x, 20. x)
- libstdc + + 6
- zlib1g

W przypadku aplikacji .NET, które używają zestawu *System. Drawing. Common* , wymagana jest również następująca zależność:

- libgdiplus (wersja 6.0.1 lub nowsza)

  > [!WARNING]
  > Aby zainstalować najnowszą wersję programu *libgdiplus* , można dodać do systemu repozytorium mono. Aby uzyskać więcej informacji, zobacz <https://www.mono-project.com/download/stable/>.

## <a name="scripted-install"></a>Instalacja z skryptami

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Instalacja ręczna

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Następne kroki

- [Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code](../tutorials/with-visual-studio-code.md)
