---
title: Instalowanie programu .NET w dystrybucji systemu Linux
description: Dowiedz się więcej o tym, jakie dystrybucje systemu Linux obsługują instalowanie programu .NET w systemie Linux.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 6354ef6f0f9af2126312683893d6705b3b4c70f4
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594523"
---
# <a name="install-net-on-linux"></a>Instalowanie programu .NET w systemie Linux

> [!div class="op_single_selector"]
>
> - [Instalowanie w systemie Windows](windows.md)
> - [Instalowanie w systemie macOS](macos.md)
> - [Instalowanie w systemie Linux](linux.md)

Platforma .NET jest dostępna dla różnych dystrybucji systemu Linux. Większość platform i dystrybucji systemu Linux jest ważna w każdym roku i w większości przedstawia Menedżera pakietów, który jest używany do instalowania platformy .NET. W tym artykule opisano, co jest obecnie obsługiwane i który jest używany przez Menedżera pakietów.

Pozostała część tego artykułu stanowi podział każdej głównej dystrybucji systemu Linux obsługiwanej przez platformę .NET. Wszystkie wersje platformy .NET pozostają obsługiwane, dopóki wersja [platformy .NET osiągnie koniec okresu obsłudze](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub dystrybucja systemu Linux osiągnie koniec cyklu życia.

Aby uzyskać najlepszą zgodność, wybierz wersję długoterminową (LTS).

## <a name="unsupported-releases"></a>Nieobsługiwane wersje

Następujące wersje platformy .NET nie są ❌ już obsługiwane. Pliki do pobrania dla tych nadal są publikowane:

- 3.0
- 2.2
- 2,0

Te nieobsługiwane wersje nie są szczegółowo opisane w poniższych sekcjach, a przebieg może się różnić w przypadku próby ich zainstalowania.

## <a name="alpine"></a>Alpine

Brak instalatorów dla Alpine. Musisz użyć [skryptu instalacji](linux-alpine.md#scripted-install) lub instrukcji [instalacji ręcznej](linux-alpine.md#manual-install) .

Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Alpine, w których są obsługiwane. Te wersje pozostają obsługiwane do momentu, aż wersja [platformy .NET osiągnie koniec okresu obsłudze](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Alp osiągnie koniec cyklu życia](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).

- ✔️ wskazuje, że wersja Alpine lub .NET jest nadal obsługiwana.
- ❌Wskazuje, że wersja Alpine lub .NET nie jest obsługiwana w tej wersji Alpine.
- Gdy zarówno wersja Alpine, jak i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.

| Alpine                      | .NET Core 2.1 | .NET Core 3,1 | .NET 5,0 |
|-----------------------------|---------------|---------------|----------------|
| ✔️ [3,12](linux-alpine.md)  | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ [3,11](linux-alpine.md)  | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ [3,10](linux-alpine.md)  | ✔️ 2,1        | ✔️ 3,1        | ❌ 5,0 |
| ❌ [3.9](linux-alpine.md)   | ✔️ 2,1        | ✔️ 3,1        | ❌ 5,0 |
| ❌[3,8](linux-alpine.md)   | ✔️ 2,1        | ✔️ 3,1        | ❌ 5,0 |

Aby uzyskać więcej informacji, zobacz [install .NET on Alpine](linux-alpine.md).

## <a name="centos"></a>CentOS

CentOS 7 używa yum jako Menedżera pakietów i CentOS 8 używa DNF.

Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET w systemach CentOS 7 i CentOS 8. Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca obsługi](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja CentOS nie jest już obsługiwana.

| CentOS                   | .NET Core 2.1 | .NET Core 3,1 | .NET 5,0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](linux-centos.md#centos-8-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ [7](linux-centos.md#centos-7-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |

Aby uzyskać więcej informacji, zobacz [install .NET on CentOS](linux-centos.md).

## <a name="debian"></a>Debian

Debian używa narzędzia APT (zaawansowanego pakietu) jako Menedżera pakietów.

Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Debian, w których są obsługiwane. Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca wsparcia](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Debian osiągnie koniec cyklu życia](https://wiki.debian.org/DebianReleases).

- ✔️ wskazuje, że wersja programu debian lub .NET jest nadal obsługiwana.
- ❌Wskazuje, że wersja programu debian lub .NET nie jest obsługiwana w tej wersji Debian.
- Gdy wersja programu Debian i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.

| Debian                   | .NET Core 2.1 | .NET Core 3,1 | .NET 5,0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [10](linux-debian.md#debian-10-)     | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ [9](linux-debian.md#debian-9-)       | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ❌ [8](linux-debian.md#debian-8-)       | ✔️ 2,1        | ❌ 3,1        | ❌ 5,0 |

Aby uzyskać więcej informacji, zobacz [install .NET on Debian](linux-debian.md).

## <a name="fedora"></a>Fedora

Fedora używa DNF jako Menedżera pakietów.

Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET i wersje Fedora, w których są obsługiwane. Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca wsparcia](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja [Fedora osiągnie koniec cyklu życia](https://fedoraproject.org/wiki/End_of_life).

- ✔️ wskazuje, że wersja programu Fedora lub .NET jest nadal obsługiwana.
- ❌Wskazuje, że wersja programu Fedora lub .NET nie jest obsługiwana w tej wersji Fedora.
- Gdy wersja programu Fedora i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.

| Fedora                   | .NET Core 2.1 | .NET Core 3,1 | .NET 5,0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [33](linux-fedora.md#fedora-33-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ [32](linux-fedora.md#fedora-32-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ❌[31](linux-fedora.md#fedora-31-) | ✔️ 2,1        | ✔️ 3,1        | ❌ 5,0 |
| ❌ [30](linux-fedora.md#fedora-30-) | ✔️ 2,1        | ✔️ 3,1        | ❌ 5,0 |
| ❌[29](linux-fedora.md#fedora-29-) | ✔️ 2,1        | ✔️ 3,1        | ❌ 5,0 |
| ❌[28](linux-fedora.md#fedora-28-) | ✔️ 2,1        | ❌ 3,1        | ❌ 5,0 |
| ❌[27](linux-fedora.md#fedora-27-) | ✔️ 2,1        | ❌ 3,1        | ❌ 5,0 |

Aby uzyskać więcej informacji, zobacz [install .NET on Fedora](linux-fedora.md).

## <a name="opensuse"></a>openSUSE

openSUSE używa użyciu narzędzia zypper jako Menedżera pakietów.

Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET w systemie openSUSE 15. Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca obsługi](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja openSUSE nie jest już obsługiwana.

| openSUSE                   | .NET Core 2.1 | .NET Core 3,1 | .NET 5,0 |
|----------------------------|---------------|---------------|----------------|
| ✔️ [15](linux-opensuse.md#opensuse-15-)     | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |

Aby uzyskać więcej informacji, zobacz [install .NET on openSUSE](linux-opensuse.md).

## <a name="red-hat"></a>Red Hat

Red Hat Enterprise Linux (RHEL) używa yum (RHEL 7) i DNF (RHEL 8) jako Menedżera pakietów.

Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET w systemach RHEL 7 i RHEL 8. Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca obsługi](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja RHEL nie jest już obsługiwana.

- ✔️ wskazuje, że wersja programu RHEL lub .NET jest nadal obsługiwana.
- ❌Wskazuje, że wersja programu RHEL lub .NET nie jest obsługiwana w tej wersji RHEL.
- Gdy wersja programu RHEL i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.

| RHEL                   | .NET Core 2.1 | .NET Core 3,1 | .NET 5,0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](linux-rhel.md#rhel-8-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ [7](linux-rhel.md#rhel-7--net-50) | ✔️ 2,1        | ✔️ [3,1](linux-rhel.md#rhel-7--net-core-31)        | ✔️ [5,0](linux-rhel.md#rhel-7--net-50) |

Aby uzyskać więcej informacji, zobacz [install .NET on RHEL](linux-rhel.md).

## <a name="sles"></a>SLES

SLES używa użyciu narzędzia zypper jako Menedżera pakietów.

Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET na platformie SLES 12 z dodatkiem SP2 i SLES 15. Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca obsługi](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja SLES nie jest już obsługiwana.

- ✔️ wskazuje, że wersja programu SLES lub .NET jest nadal obsługiwana.
- ❌Wskazuje, że wersja programu SLES lub .NET nie jest obsługiwana w tej wersji SLES.
- Gdy wersja programu SLES i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.

| SLES                   | .NET Core 2.1 | .NET Core 3,1 | .NET 5,0 |
|------------------------|---------------|---------------|----------------|
| ✔️ [15](linux-sles.md#sles-15-)     | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ [12 z dodatkiem SP2](linux-sles.md#sles-12-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |

Aby uzyskać więcej informacji, zobacz [install .NET on SLES](linux-sles.md).

## <a name="ubuntu"></a>Ubuntu

Ubuntu używa narzędzia APT (zaawansowanego pakietu) jako Menedżera pakietów.

Poniższa tabela przedstawia stan pomocy technicznej Ubuntu i .NET.

- ✔️ wskazuje, że wersja programu Ubuntu lub .NET jest nadal obsługiwana.
- ❌Wskazuje, że wersja programu Ubuntu lub .NET nie jest obsługiwana w tej wersji Ubuntu.
- Gdy wersja programu Ubuntu i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.

| Ubuntu                   | .NET Core 2.1 | .NET Core 3,1 | .NET 5,0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [20,10](linux-ubuntu.md#2010-)       | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ [20,04 (LTS)](linux-ubuntu.md#2004-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ❌[19,10](linux-ubuntu.md#1910-)       | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ❌[19,04](linux-ubuntu.md#1904-)       | ✔️ 2,1        | ✔️ 3,1        | ❌ 5,0 |
| ❌[18,10](linux-ubuntu.md#1810-)       | ✔️ 2,1        | ❌ 3,1        | ❌ 5,0 |
| ✔️ [18,04 (LTS)](linux-ubuntu.md#1804-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ❌[17,10](linux-ubuntu.md#1710-)       | ✔️ 2,1        | ❌ 3,1        | ❌ 5,0 |
| ❌[17,04](linux-ubuntu.md#1704-)       | ✔️ 2,1        | ❌ 3,1        | ❌ 5,0 |
| ❌[16,10](linux-ubuntu.md#1610-)       | ❌ 2,1        | ❌ 3,1        | ❌ 5,0 |
| ✔️ [16,04 (LTS)](linux-ubuntu.md#1604-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |

Aby uzyskać więcej informacji, zobacz [install .NET on Ubuntu](linux-ubuntu.md).

## <a name="next-steps"></a>Następne kroki

- [Jak sprawdzić, czy program .NET jest już zainstalowany](how-to-detect-installed-versions.md?pivots=os-linux).
- [Samouczek: Tworzenie nowej aplikacji przy użyciu Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Samouczek: konteneryzowanie aplikacji .NET](../docker/build-container.md).
