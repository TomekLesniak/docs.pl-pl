---
ms.openlocfilehash: 83808f2f3a05333ed5d9e3809cbc2fd6e230d02c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031784"
---

[Program .NET Core jest dostępny w magazynie Snap.](https://snapcraft.io/dotnet-sdk)

Przyciąganie to pakiet aplikacji i jej zależności, które działają bez modyfikacji dla wielu różnych dystrybucji systemu Linux. Przyciąganie jest wykrywalne i instalowane z magazynu Snap. Aby uzyskać więcej informacji na temat przyciągania, zobacz [wprowadzenie do przyciągania](https://snapcraft.io/docs/getting-started).

Tylko obsługiwane wersje programu .NET Core są dostępne za poorednictwem przyciągania.

### <a name="install-the-sdk"></a>Instalacja zestawu SDK

Pakiety przyciągania dla zestawu .NET SDK są publikowane w ramach tego samego identyfikatora: `dotnet-sdk` . Określoną wersję zestawu SDK można zainstalować, określając kanał. Zestaw SDK zawiera odpowiednie środowisko uruchomieniowe. Poniższa tabela zawiera listę kanałów:

| Wersja platformy .NET | Pakiet przyciągania             |
|--------------|--------------------------|
| 5,0          | `5.0` lub `latest/stable` |
| 3,1 (LTS)    | `3.1` lub `lts/stable`    |
| 2,1 (LTS)    | `2.1`                    |

Użyj `snap install` polecenia, aby zainstalować pakiet przyciągania zestawu .NET SDK. Użyj `--channel` parametru, aby wskazać wersję do zainstalowania. Jeśli ten parametr zostanie pominięty, `latest/stable` jest używany. W tym przykładzie `5.0` określono:

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

Następnie zarejestruj `dotnet` polecenie dla systemu przy użyciu `snap alias` polecenia:

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

To polecenie jest sformatowane jako: `sudo snap alias {package}.{command} {alias}` . Możesz wybrać dowolną `{alias}` nazwę. Można na przykład nazwać polecenie po zainstalowaniu określonej wersji przez przyciąganie: `sudo snap alias dotnet-sdk.dotnet dotnet50` . Korzystając z polecenia `dotnet50` , należy wywołać tę konkretną wersję platformy .NET. Ale jest to niezgodne z większością samouczków i przykładów, ponieważ oczekuje, że `dotnet` polecenie jest dostępne.

### <a name="install-the-runtime"></a>Instalowanie środowiska uruchomieniowego

Pakiety przyciągania dla środowiska uruchomieniowego .NET Core są publikowane w ramach własnego identyfikatora pakietu. W poniższej tabeli wymieniono identyfikatory pakietów:

| Wersja platformy .NET      | Pakiet przyciągania        |
|-------------------|---------------------|
| 5,0               | `dotnet-runtime-50` |
| 3,1 (LTS)         | `dotnet-runtime-31` |
| 3.0               | `dotnet-runtime-30` |
| 2.2               | `dotnet-runtime-22` |
| 2,1 (LTS)         | `dotnet-runtime-21` |

Użyj `snap install` polecenia, aby zainstalować pakiet przyciągania środowiska uruchomieniowego platformy .NET. W tym przykładzie jest zainstalowany program .NET 5,0:

```bash
sudo snap install dotnet-runtime-50 --classic
```

Następnie zarejestruj `dotnet` polecenie dla systemu przy użyciu `snap alias` polecenia:

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

To polecenie jest sformatowane jako: `sudo snap alias {package}.{command} {alias}` . Możesz wybrać dowolną `{alias}` nazwę. Można na przykład nazwać polecenie po zainstalowaniu określonej wersji przez przyciąganie: `sudo snap alias dotnet-runtime-50.dotnet dotnet50` . Korzystając z polecenia `dotnet50` , należy wywołać tę konkretną wersję platformy .NET. Ale jest to niezgodne z większością samouczków i przykładów, ponieważ oczekuje, że `dotnet` polecenie jest dostępne.

### <a name="ssl-certificate-errors"></a>Błędy certyfikatów SSL

Po zainstalowaniu programu .NET za pośrednictwem przyciągania możliwe jest, że na niektórych dystrybucje nie można odnaleźć certyfikatów protokołu SSL platformy .NET i może zostać wyświetlony błąd podobny do poniższego `restore` :

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

Aby rozwiązać ten problem, ustaw kilka zmiennych środowiskowych:

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

Lokalizacja certyfikatu zależy od dystrybucji. Poniżej znajdują się lokalizacje dystrybucje, w których wystąpił problem.

* Fedora `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`
* OpenSUSE `/etc/ssl/ca-bundle.pem`
* Solus - `/etc/ssl/certs/ca-certificates.crt`
