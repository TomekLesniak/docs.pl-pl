---
title: Instalowanie platformy .NET w systemie RHEL — .NET
description: Przedstawiono różne sposoby instalowania zestawu .NET SDK i środowiska uruchomieniowego .NET w systemie RHEL.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: a742497bba3459a4d8772f5c9e3d915b5b18e62e
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506930"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a>Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe .NET w systemie RHEL

Platforma .NET jest obsługiwana w systemie RHEL. W tym artykule opisano sposób instalowania programu .NET w systemie RHEL.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a>Zarejestruj swoją subskrypcję Red Hat

Aby zainstalować platformę .NET z systemu Red Hat na RHEL, musisz najpierw zarejestrować się przy użyciu Menedżera subskrypcji Red Hat. Jeśli nie zostało to zrobione w systemie lub nie masz pewności, zobacz [dokumentację produktu Red Hat dla platformy .NET](https://access.redhat.com/documentation/net/5.0/).

## <a name="supported-distributions"></a>Obsługiwane dystrybucje

Poniższa tabela zawiera listę obecnie obsługiwanych wersji platformy .NET w systemach RHEL 7 i RHEL 8. Te wersje pozostają obsługiwane, dopóki wersja [platformy .NET nie osiągnie końca obsługi](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) lub wersja RHEL nie jest już obsługiwana.

- ✔️ wskazuje, że wersja programu RHEL lub .NET jest nadal obsługiwana.
- ❌Wskazuje, że wersja programu RHEL lub .NET nie jest obsługiwana w tej wersji RHEL.
- Gdy wersja programu RHEL i wersja platformy .NET mają ✔️, obsługiwane są kombinacje systemów operacyjnych i .NET.

| RHEL                   | .NET Core 2.1 | .NET Core 3,1 | .NET 5,0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](#rhel-8-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |
| ✔️ [7](#rhel-7-) | ✔️ 2,1        | ✔️ 3,1        | ✔️ 5,0 |

Następujące wersje platformy .NET nie są już obsługiwane. Pliki do pobrania dla tych nadal są publikowane:

- 3.0
- 2.2
- 2,0

## <a name="how-to-install-other-versions"></a>Jak zainstalować inne wersje

Zapoznaj się z [dokumentacją firmy Red Hat dla platformy .NET](https://access.redhat.com/documentation/net/5.0/) , wykonując kroki wymagane do zainstalowania innych wersji platformy .NET.

## <a name="rhel-8-"></a>RHEL 8 ✔️

Platforma .NET jest uwzględniona w repozytoriach AppStream dla RHEL 8.

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7-"></a>RHEL ✔️ 7

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

Następujące polecenie instaluje `scl-utils` pakiet:

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a>Instalacja zestawu SDK

Zestaw SDK platformy .NET umożliwia tworzenie aplikacji przy użyciu platformy .NET. W przypadku instalowania zestawu .NET SDK nie trzeba instalować odpowiedniego środowiska uruchomieniowego. Aby zainstalować zestaw SDK dla platformy .NET, uruchom następujące polecenia:

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50 -y
scl enable rh-dotnet50 bash
```

Red Hat nie zaleca trwałego włączania `rh-dotnet50` , ponieważ może to mieć wpływ na inne programy. Program zawiera na przykład `rh-dotnet50` wersję `libcurl` , która różni się od bazowej wersji RHEL. Może to prowadzić do problemów z programami, które nie oczekują innej wersji programu `libcurl` . Jeśli chcesz `rh-dotnet` trwale włączyć, Dodaj następujący wiersz do pliku _~/.bashrc._ .

```bash
source scl_source enable rh-dotnet50
```

### <a name="install-the-runtime"></a>Instalowanie środowiska uruchomieniowego

Środowisko uruchomieniowe ASP.NET Core pozwala uruchamiać aplikacje wykonane przy użyciu platformy .NET, które nie zapewniały środowiska uruchomieniowego. Następujące polecenia instalują środowisko uruchomieniowe ASP.NET Core, które jest najbardziej zgodnym środowiskiem uruchomieniowym dla platformy .NET. W terminalu uruchom następujące polecenia:

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50-aspnetcore-runtime-5.0 -y
scl enable rh-dotnet50-aspnetcore-runtime-5.0 bash
```

Red Hat nie zaleca trwałego włączania `rh-dotnet50-aspnetcore-runtime-5.0` , ponieważ może to mieć wpływ na inne programy. Program zawiera na przykład `rh-dotnet50-aspnetcore-runtime-5.0` wersję `libcurl` , która różni się od bazowej wersji RHEL. Może to prowadzić do problemów z programami, które nie oczekują innej wersji programu `libcurl` . Jeśli chcesz `rh-dotnet50-aspnetcore-runtime-5.0` trwale włączyć, Dodaj następujący wiersz do pliku _~/.bashrc._ .

```bash
source scl_source enable rh-dotnet50-aspnetcore-runtime-5.0
```

Jako alternatywę dla środowiska uruchomieniowego ASP.NET Core można zainstalować środowisko uruchomieniowe platformy .NET, które nie obejmuje ASP.NET Core obsługi: Zastąp `rh-dotnet50-aspnetcore-runtime-5.0` w poprzednich poleceniach poleceniem `rh-dotnet50-dotnet-runtime-5.0` .

## <a name="snap"></a>Przystawki

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a>Zależności

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a>Instalacja z skryptami

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Instalacja ręczna

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Następne kroki

- [Samouczek: Tworzenie aplikacji konsolowej za pomocą zestawu .NET SDK przy użyciu Visual Studio Code](../tutorials/with-visual-studio-code.md)
